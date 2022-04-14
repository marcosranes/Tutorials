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
# `$ ip a s docker0`
```
4: docker0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default 
    link/ether 02:42:dc:46:bd:a3 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
    inet6 fe80::42:dcff:fe46:bda3/64 scope link 
       valid_lft forever preferred_lft forever
```
The above command will bring you a built hello-world docker image from the docker repository.

# Docker running Postgres 

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

After that, rerun the docker run command for postgres you've earlier tried
```
docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres
```
To see it running "docker ps" will show you all docker containers list running for you in your system 
```
$ docker ps
```
OTHERWISE modify the client postgresql port if it's already in use, i. e. -p 5432:5432, change to -p 5434:5432 for instance, however don't forget specifying the new port by adding -p 5434 as a parameter when logging i.e. (psql -h localhost -U "postgres" -p 5434).

If you want handle with the postgres default localhost listening port and other configurations try 
cat /etc/postgresql/12/main/postgresql.conf | less, so go scrolling until you find the properly line to change it.

Note: 12 is the my postgresql version, so investigate through the path by typing 'ls /etc/postgresql' and replace to yours.
In order to make changes to postgresql.conf file you'll need sudo permissions and open it under an editor. i.e 'sudo nano /etc/postgresql/12/main/postgresql.conf', otherwise just add the -p parameter specifying the port as I told earlier, it's more practice.

The postgres service from the docker yet comes with the native postgres client known as psql previously activated under the default credentials, user: postgres and "docker" as password. To call a postgres shell section type
```
$ psql -h localhost -U "postgres"
```
Once the postgres shell section is open for you, which should seem like this **postgres=#**, know that you are into the interactive psql shell client.\
So try these useful commands:
```
CREATE EXTENSION adminpack;             -adminpack brings for us insteresting tools for database management 
\password postgres                      -to change the password for the user postgres --in our case, our default password is "docker"
\l 
\q                                      -to quit
```
Note: if your project already have a docker-compose.yaml file properly set, you can containerize your application as a docker container, and not depending on your machine to run it. docker-compose creates mini container clusters for running your application litely\
Docker isn't a virtual machine, it utilizes the kernel from your system. see it\
$ ps aux    - look for postgres, second colunm look for its PID process, so in my case 3618 then\
$ cat /proc/3618/cgroup\
$ ps        - take a look at the bash PID, in my case 2537\
$ cat /proc/2537/cgroup\
As you can see, Docker runs side by side with your system

### Stoping docker containers
Type $ docker ps, look at the container ID, type

$ docker stop 4t21ac53d682

# Linux running Postgres
The commands themself seem like the same, but they differ in some aspects, once here sudo is essential, for instance the following command is used for creating a user for the database.
```
sudo -u postgres createuser -D -A -P newusersql 
```
Creating a DataBase **dbtest** for the user **newusersql** we've just created 
```
sudo -u postgres createdb -O newusersql dbTest
```
To enter
```
sudo -u postgres psql dbTest
```
For excluding...
```
dbTest=# DROP DATABASE dbTest
dbTest-# DROP USER marcosranes
dbTest-# \q
```



```
sudo nano /etc/postgresql/12/main/postgresql.conf
```
```shell
# - Connection Settings -

#listen_addresses = 'localhost'         # what IP address(es) to listen on;
```
```shell
# - Connection Settings -

listen_addresses = '*'         # what IP address(es) to listen on;
```
```
sudo service postgresql restart
```
```
sudo service postgresql status
```
take a look at the postgres Active session...
```shell
● postgresql.service - PostgreSQL RDBMS
     Loaded: loaded (/lib/systemd/system/postgresql.service; enabled; vendor preset: enabled)
     Active: active (exited) since Wed 2022-04-13 17:17:03 CDT; 19s ago
    Process: 14599 ExecStart=/bin/true (code=exited, status=0/SUCCESS)
   Main PID: 14599 (code=exited, status=0/SUCCESS)

Apr 13 17:17:03 ubuntu-labs systemd[1]: Starting PostgreSQL RDBMS...
Apr 13 17:17:03 ubuntu-labs systemd[1]: Finished PostgreSQL RDBMS.
```
As you can see the server was restarted successfuly.


## Now, get started by exploring your postgresql server with simple sql commands.

Logging into database in two ways
```shell
devops3559@ubuntu-labs:~$ sudo -u postgres psql postgres
psql (12.9 (Ubuntu 12.9-0ubuntu0.20.04.1))
Type "help" for help.

postgres=#
```
```shell
devops3559@ubuntu-labs:~$ sudo -u postgres psql
psql (12.9 (Ubuntu 12.9-0ubuntu0.20.04.1))
Type "help" for help.

postgres=#
```
Showing the list of roles
```shell
postgres=# \l
                                   List of databases
   Name    |    Owner    | Encoding |   Collate   |    Ctype    |   Access privileges   
-----------+-------------+----------+-------------+-------------+-----------------------
 dbTest    | newusersql  | UTF8     | en_US.UTF-8 | en_US.UTF-8 | 
 postgres  | postgres    | UTF8     | en_US.UTF-8 | en_US.UTF-8 | 
 template0 | postgres    | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |             |          |             |             | postgres=CTc/postgres
 template1 | postgres    | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |             |          |             |             | postgres=CTc/postgres
(4 rows)
```
Toggling between database
```shell
postgres=# \connect dbTest
You are now connected to database "dbTest" as user "postgres".
dbTest=# \connect template0
FATAL:  database "template0" is not currently accepting connections
Previous connection kept
dbTest=# \connect template1
You are now connected to database "template1" as user "postgres".
template1=# \connect postgres
You are now connected to database "postgres" as user "postgres".
postgres=# \connect postgres
```
Showing tables
```shell
postgres=# \dt
          List of relations
 Schema |   Name   | Type  |  Owner   
--------+----------+-------+----------
 public | clients | table | postgres
(1 row)
```
Changing the password
```shell
postgres=# \password
Enter new password: 123456
Enter it again: 123456
postgres=# 
```

