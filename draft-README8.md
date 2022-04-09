 
# UPDATE-ALTERNATIVES
```
devops3559@ubuntu-labs:~$ ls -a /usr/bin | grep update-alt
update-alternatives
```
devops3559@ubuntu-labs:/usr/bin$ update-alternatives
```
update-alternatives: need --display, --query, --list, --get-selections, --config, --set, --set-selections, --install, --remove, --all, --remove-all or --auto

Use 'update-alternatives --help' for program usage information.
```
devops3559@ubuntu-labs:/usr/bin$ update-alternatives --help
```
Usage: update-alternatives [<option> ...] <command>

Commands:
  --install <link> <name> <path> <priority>
    [--slave <link> <name> <path>] ...
                           add a group of alternatives to the system.
  --remove <name> <path>   remove <path> from the <name> group alternative.
  --remove-all <name>      remove <name> group from the alternatives system.
  --auto <name>            switch the master link <name> to automatic mode.
  --display <name>         display information about the <name> group.
  --query <name>           machine parseable version of --display <name>.
  --list <name>            display all targets of the <name> group.
  --get-selections         list master alternative names and their status.
  --set-selections         read alternative status from standard input.
  --config <name>          show alternatives for the <name> group and ask the
                           user to select which one to use.
  --set <name> <path>      set <path> as alternative for <name>.
  --all                    call --config on all alternatives.

<link> is the symlink pointing to /etc/alternatives/<name>.
  (e.g. /usr/bin/pager)
<name> is the master name for this link group.
  (e.g. pager)
<path> is the location of one of the alternative target files.
  (e.g. /usr/bin/less)
<priority> is an integer; options with higher numbers have higher priority in
  automatic mode.

Options:
  --altdir <directory>     change the alternatives directory.
  --admindir <directory>   change the administrative directory.
  --log <file>             change the log file.
  --force                  allow replacing files with alternative links.
  --skip-auto              skip prompt for alternatives correctly configured
                           in automatic mode (relevant for --config only)
  --quiet                  quiet operation, minimal output.
  --verbose                verbose operation, more output.
  --debug                  debug output, way more output.
  --help                   show this help message.
  --version                show the version.
```

# CONFIGURATION - Seeting up alternatives
```
$ update-alternatives --display docker-compose
update-alternatives: error: no alternatives for docker-compose
```
```
$ update-alternatives --config docker-compose
update-alternatives: error: no alternatives for docker-compose
```
```
devops3559@ubuntu-labs:~$ update-alternatives --display docker-compose
update-alternatives: error: no alternatives for docker-compose
devops3559@ubuntu-labs:~$ sudo update-alternatives --install /usr/local/bin/docker-compose docker-compose /usr/local/bin/docker-compose-v1 1
[sudo] password for devops3559: 
Sorry, try again.
[sudo] password for devops3559: 
update-alternatives: using /usr/local/bin/docker-compose-v1 to provide /usr/local/bin/docker-compose (docker-compose) in auto mode
devops3559@ubuntu-labs:~$ update-alternatives --display docker-compose
docker-compose - auto mode
  link best version is /usr/local/bin/docker-compose-v1
  link currently points to /usr/local/bin/docker-compose-v1
  link docker-compose is /usr/local/bin/docker-compose
/usr/local/bin/docker-compose-v1 - priority 1
devops3559@ubuntu-labs:~$ sudo update-alternatives --install /usr/local/bin/docker-compose docker-compose /usr/local/bin/compose-switch 99
update-alternatives: using /usr/local/bin/compose-switch to provide /usr/local/bin/docker-compose (docker-compose) in auto mode
devops3559@ubuntu-labs:~$ update-alternatives --display docker-compose
docker-compose - auto mode
  link best version is /usr/local/bin/compose-switch
  link currently points to /usr/local/bin/compose-switch
  link docker-compose is /usr/local/bin/docker-compose
/usr/local/bin/compose-switch - priority 99
/usr/local/bin/docker-compose-v1 - priority 1
devops3559@ubuntu-labs:~$ update-alternatives --config docker-compose
There are 2 choices for the alternative docker-compose (providing /usr/local/bin/docker-compose).

  Selection    Path                              Priority   Status
------------------------------------------------------------
* 0            /usr/local/bin/compose-switch      99        auto mode
  1            /usr/local/bin/compose-switch      99        manual mode
  2            /usr/local/bin/docker-compose-v1   1         manual mode

Press <enter> to keep the current choice[*], or type selection number: 2
update-alternatives: using /usr/local/bin/docker-compose-v1 to provide /usr/local/bin/docker-compose (docker-compose) in manual mode
update-alternatives: error: error creating symbolic link '/etc/alternatives/docker-compose.dpkg-tmp': Permission denied
devops3559@ubuntu-labs:~$ sudo update-alternatives --config docker-compose
There are 2 choices for the alternative docker-compose (providing /usr/local/bin/docker-compose).

  Selection    Path                              Priority   Status
------------------------------------------------------------
* 0            /usr/local/bin/compose-switch      99        auto mode
  1            /usr/local/bin/compose-switch      99        manual mode
  2            /usr/local/bin/docker-compose-v1   1         manual mode

Press <enter> to keep the current choice[*], or type selection number: 2
update-alternatives: using /usr/local/bin/docker-compose-v1 to provide /usr/local/bin/docker-compose (docker-compose) in manual mode
devops3559@ubuntu-labs:~$ update-alternatives --display docker-compose
docker-compose - manual mode
  link best version is /usr/local/bin/compose-switch
  link currently points to /usr/local/bin/docker-compose-v1
  link docker-compose is /usr/local/bin/docker-compose
/usr/local/bin/compose-switch - priority 99
/usr/local/bin/docker-compose-v1 - priority 1
devops3559@ubuntu-labs:~$ sudo update-alternatives --config docker-compose
There are 2 choices for the alternative docker-compose (providing /usr/local/bin/docker-compose).

  Selection    Path                              Priority   Status
------------------------------------------------------------
  0            /usr/local/bin/compose-switch      99        auto mode
  1            /usr/local/bin/compose-switch      99        manual mode
* 2            /usr/local/bin/docker-compose-v1   1         manual mode

Press <enter> to keep the current choice[*], or type selection number: ^C
devops3559@ubuntu-labs:~$ docker compose version
Docker Compose version v2.2.3
devops3559@ubuntu-labs:~$ docker-compose version
docker-compose version 1.29.2, build 5becea4c
docker-py version: 5.0.0
CPython version: 3.7.10
OpenSSL version: OpenSSL 1.1.0l  10 Sep 2019
devops3559@ubuntu-labs:~$ docker-compose-v1 version
docker-compose version 1.29.2, build 5becea4c
docker-py version: 5.0.0
CPython version: 3.7.10
OpenSSL version: OpenSSL 1.1.0l  10 Sep 2019
devops3559@ubuntu-labs:~$ compose-switch version
Docker Compose version v2.2.3
devops3559@ubuntu-labs:~$ 
```
