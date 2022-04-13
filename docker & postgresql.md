## Giving permissions to use Docker without sudo:
Depending on the configuration of your Docker installation, you may need to type docker commands with sudo. So, Docker also creates a user called docker, its user needs to be into the group $USER for managing docker without sudo permissions, then avoiding to have to type sudo along with docker commands.
Otherwise if it doesn't already exist, you can create a docker group.
```
$ sudo groupadd docker
```
If you want it to see more, there are several maners for verifying members group, try these commands:
```
$ echo $USER
$ groups $USER
$ cat /etc/group
```
Also you can use grep filter to be more specific.
```
$ cat /etc/group | grep docker
```
Note: In order to see the dozen enabled variables for your environment
```
$ set | less.
```
So, finally lets go to add docker to $USER group. 
```
$ sudo usermod -aG docker $USER
```
Restart your linux system
```
$ sudo reboot
```
Now, verify your last settings, try running docker without sudo
```
$ docker run hello-world
```
The above command will bring you a built hello-world docker image from the docker repository.

# Postgres

Download the most recent docker image from the dockerhub repository
```
$ docker pull postgres
```

Now we have to create a external repository to store postgres database, log-files, etc.. when running postgres through docker:
```
$ mkdir -p $HOME/docker/dbdata/postgres
```
For executing the Postgres docker image you've just downlaod, run
```shell
docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/dbdata/postgres:/var/lib/postgresql/data postgres
```
Note:

If you experience a proxy error, you need to stop or disable the running postgres from your local system machine. Three ways to see it:\
$ sudo systemctl status postgresql\
$ sudo service postgresql status\
$ sudo /etc/init.d/postgresql status\
usage: start, stop, restart, reload, force-reload, status\
In order to disable postgresql auto initializing service, usage: disable, otherwise: enable.. use systemctl, after that $ sudo reboot the system.\
To see all auto initializing services when booting the system type $ ls /etc/init.d\
So, as you can see several ways to handle with postgresql, but lets chose to use $ sudo service postgresql stop 

After that, rerun the docker rum command for postgres you've earlier tried
```
docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres
```
To see it running "docker ps" will show you all docker containers list running for you in your system 
```
$ docker ps
```
The postgres service from the docker yet comes with the native postgres client known as psql previously activated under the default credentials, user: postgres and "docker" as password. To call a postgres shell section type
```
$ psql -h localhost -U "postgres"
```
After that postgres shell section should open for you that seems like this postgres=# then you are into the interactive psql shell client. commands to use:

```
\l 
\q - to quit
```
note: if your project already have a docker-compose.yaml file properly set, you can containerize your application as a docker container, and not depending on your machine to run it. docker-compose creates mini container clusters for running your application litely\
Docker isn't a virtual machine, it utilizes the kernel from your system. see it\
$ ps aux    - look for postgres, second colunm look for its PID process, so in my case 3618 then\
$ cat /proc/3618/cgroup\
$ ps        - take a look at the bash PID, in my case 2537\
$ cat /proc/2537/cgroup\
As you can see, Docker runs side by side with your system

### Stoping docker containers
Type $ docker ps, look at the container ID, type

$ docker stop 4t21ac53d682
