## Giving permissions to use Docker without sudo:

Docker creates a user group called docker, your user needs to be into the group for managing docker. If you want it to see, just $ echo $USER. 

In order to see the dozen enabled variables for your environment $ set | less. So, lets go...

$ sudo usermod -aG docker $USER

Restart your linux system

$ sudo reboot

Now, testing your last settings:

$ docker run hello-world

# Postgres

The bellow command downloads the most recent docker image from the dockerhub repository

$ docker pull postgres

Now we have to create a external repository to store postgres database, log-files, etc.. when running postgres through docker:

$ mkdir -p $HOME/docker/volumes/postgres

$ docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres

If you experience a proxy error, you need to stop or disable the running postgres from your local system machine. Three ways to see it:\
$ sudo systemctl status postgresql\
$ sudo service postgresql status\
$ sudo /etc/init.d/postgresql status\
usage: start, stop, restart, reload, force-reload, status\
In order to disable postgresql auto initializing service, usage: disable, otherwise: enable.. use systemctl, after that $ sudo reboot the system.\
To see all auto initializing services when booting the system type $ ls /etc/init.d

After that, rerun the docker rum command for postgres you've earlier tried\
$ docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres



