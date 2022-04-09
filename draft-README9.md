
## ` $ date `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
Fri Jan 14 07:06:58 PM -03 2022
```
Docker Engine is supported on x86_64 (or amd64), armhf, arm64, and s390x architectures.

Uninstall old versions
Older versions of Docker were called docker, docker.io, or docker-engine. If these are installed, uninstall them:

### `$ sudo apt-get remove docker docker-engine docker.io containerd runc`
It’s OK if apt-get reports that none of these packages are installed.

The contents of /var/lib/docker/, including images, containers, volumes, and networks, are preserved. If you do not need to save your existing data, and want to start with a clean installation, refer to the uninstall Docker Engine section at the bottom of this page.

# Uninstall Docker Engine🔗
1. Uninstall the Docker Engine, CLI, and Containerd packages:

### `$ sudo apt-get purge docker-ce docker-ce-cli containerd.io`

2. Images, containers, volumes, or customized configuration files on your host are not automatically removed. To delete all images, containers, and volumes:

### `$ sudo rm -rf /var/lib/docker`
### `$ sudo rm -rf /var/lib/containerd`

You must delete any edited configuration files manually.


# Supported storage drivers
Docker Engine on Ubuntu supports overlay2, aufs and btrfs storage drivers.\
Docker Engine uses the overlay2 storage driver by default. If you need to use aufs instead, you need to configure it manually. See [use the AUFS storage driver](https://docs.docker.com/storage/storagedriver/aufs-driver/).

# Installation methods
You can install Docker Engine in different ways, depending on your needs:
- Most users set up Docker’s repositories and install from them, for ease of installation and upgrade tasks. This is the recommended approach.
- Some users download the DEB package and install it manually and manage upgrades completely manually. This is useful in situations such as installing Docker on air-gapped systems with no access to the internet.
- In testing and development environments, some users choose to use automated convenience scripts to install Docker.

# Install using the repository
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

### Set up the repository
Update the apt package index and install packages to allow apt to use a repository over HTTPS:
```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg lsb-release
 ```
### Add Docker’s official GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
# Install Docker Engine
1. Update the apt package index, and install the latest version of Docker Engine and containerd, or go to the next step to install a specific version:
```
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
2. To install a specific version of Docker Engine, list the available versions in the repo, then select and install:

a. List the versions available in your repo:
```
apt-cache madison docker-ce
```
b. Install a specific version using the version string from the second column, for example, 5:18.09.1~3-0~ubuntu-xenial.
```
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```
3. Verify that Docker Engine is installed correctly by running the hello-world image.
```
sudo docker run hello-world
```
This command downloads a test image and runs it in a container. When the container runs, it prints a message and exits.\
Docker Engine is installed and running.\
The docker group is created but no users are added to it.\
You need to use sudo to run Docker commands.\
Continue to Linux postinstall to allow non-privileged users to run Docker commands and for other optional configuration steps.



# Manage Docker as a non-root user
The Docker daemon binds to a Unix socket instead of a TCP port. By default that Unix socket is owned by the user root and other users can only access it using sudo. The Docker daemon always runs as the root user.

If you don’t want to preface the docker command with sudo, create a Unix group called docker and add users to it. When the Docker daemon starts, it creates a Unix socket accessible by members of the docker group.

Warning

The docker group grants privileges equivalent to the root user. For details on how this impacts security in your system, see Docker Daemon Attack Surface.

Note:

To run Docker without root privileges, see Run the Docker daemon as a non-root user (Rootless mode).

To create the docker group and add your user:

Create the docker group.
```
sudo groupadd docker
```
Add your user to the docker group.
```
sudo usermod -aG docker $USER
```
Log out and log back in so that your group membership is re-evaluated.

If testing on a virtual machine, it may be necessary to restart the virtual machine for changes to take effect.

On a desktop Linux environment such as X Windows, log out of your session completely and then log back in.

On Linux, you can also run the following command to activate the changes to groups:
```
newgrp docker
```
Verify that you can run docker commands without sudo.
```
docker run hello-world
```
This command downloads a test image and runs it in a container. When the container runs, it prints a message and exits.

If you initially ran Docker CLI commands using sudo before adding your user to the docker group, you may see the following error, which indicates that your ~/.docker/ directory was created with incorrect permissions due to the sudo commands.

WARNING: Error loading config file: /home/user/.docker/config.json -
stat /home/user/.docker/config.json: permission denied
To fix this problem, either remove the ~/.docker/ directory (it is recreated automatically, but any custom settings are lost), or change its ownership and permissions using the following commands:
```
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R
```
Configure Docker to start on boot
Most current Linux distributions (RHEL, CentOS, Fedora, Debian, Ubuntu 16.04 and higher) use systemd to manage which services start when the system boots. On Debian and Ubuntu, the Docker service is configured to start on boot by default. To automatically start Docker and Containerd on boot for other distros, use the commands below:
```
sudo systemctl enable docker.service
sudo systemctl enable containerd.service
```
To disable this behavior, use disable instead.
```
sudo systemctl disable docker.service
sudo systemctl disable containerd.service
```
If you need to add an HTTP Proxy, set a different directory or partition for the Docker runtime files, or make other customizations, see [customize your systemd Docker daemon options](https://docs.docker.com/config/daemon/systemd/).
