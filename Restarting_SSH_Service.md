
## ` $ date `
```
Sat Dec 18 12:10:48 PM -03 2021
```
 
# How to Restart SSH Service under Linux / UNIX
 
### SSH is an acronym for Secure Shell. It is an Internet communication protocol that allows log into Linux or Unix bases systems and runs commands. One can exchange files using a secure channel over an insecure network such as the Internet. OpenSSH is developed as part of the OpenBSD project and by default installed on modern Linux and *BSD family of operating systems including macOS. This page shows how to restart ssh service.
 
## CentOS / RHEL / Fedora / Redhat Linux Restart SSH
 
### How to restart the SSH in Debian / Ubuntu Linux
 
SSH is an acronym for Secure Shell. It is an Internet communication protocol that allows log into Linux or Unix bases systems and runs commands. One can exchange files using a secure channel over an insecure network such as the Internet. OpenSSH is developed as part of the OpenBSD project and by default installed on modern Linux and *BSD family of operating systems including macOS. This page shows how to restart ssh service.
ADVERTISEMENT

Restart SSH Service Command
The command to restart sshd are as follows (you must login as root user). You must run command as per your Linux distribution or Unix variant.

# Restart ssh service in Linux or Unix

CentOS / RHEL / Fedora / Redhat Linux Restart SSH
Type the following command:
# ` # /etc/init.d/sshd restart `

One can use the service command:
# ` # service sshd restart `
#

## If you are using __RHEL/CentOS/Fedora__ Linux with systemd (e.g. RHEL or CentOS v7/8), enter:
# ` $ sudo systemctl restart sshd `
#
##
# How to restart the SSH in __Debian / Ubuntu Linux__
Restarting ssh is simple job, execute:
# ` $ /etc/init.d/ssh restart `

OR
# ` $ service ssh restart `

OR
# ` $ sudo service ssh restart `
If you experiencing problems with ssh services, maybe you should execute the following command before.
# ` $ sudo apt install openssh-server -y `

# If you are using __Debian/Ubuntu/Mint Linux__ with __systemd__, use the __systemctl__ command:
# ` $ sudo systemctl restart ssh `


### FreeBSD Restart SSH
# ` $ /etc/rc.d/sshd restart `

OR
# ` $ sudo service sshd restart `

# __OpenBSD__ Restart SSH service
# ` $ /etc/rc.d/sshd restart `

OR
# ` $ doas /etc/rc.d/sshd restart `
#
#
# __UNIX__ Restart SSH
# ` # kill -HUP cat /var/run/sshd.pid ` 

OR
# ` # kill -HUP $(cat /var/run/sshd.pid) ` 

Please note that the location of /var/run/sshd.pid may change. So just search a bit through /var/run/ directory.
#
#
# OpenSUSE/SUSE Enterprise Linux restart sshd
Type the following command:
# ` $ sudo systemctl restart sshd `

# Arch Linux restart sshd server
Execute the following command:
# ` $ sudo systemctl restart sshd.service`
#
#
# Command line SSH restart for Apple macOS
Open the terminal application and type the following two commands:
## ` $ sudo launchctl unload /System/Library/LaunchDaemons/ssh.plist `
## ` $ sudo launchctl load -w /System/Library/LaunchDaemons/ssh.plist `

OR
## ` $ sudo launchctl stop com.openssh.sshd `
## ` $ sudo launchctl start com.openssh.sshd `
#
#
#
# __Slackware Linux__ restart the SSH server
Restarting ssh is pretty easy on __Slackware__, just run the following command as root user:
# ` # /etc/rc.d/rc.sshd restart `

### Conclusion
This page explained how to restart ssh service on Linux or Unix-like operating systems using various options. For more information see the official OpenSSH documents here. Another option is to read more about ssh client and sshd server by typing the following man command:
man ssh
man sshd

Patreon supporters only guides 🤓
No ads and tracking
In-depth guides for developers and sysadmins at Opensourceflare✨
Join my Patreon to support independent content creators and start reading latest guides:
How to set up Redis sentinel cluster on Ubuntu or Debian Linux
How To Set Up SSH Keys With YubiKey as two-factor authentication (U2F/FIDO2)
How to set up Mariadb Galera cluster on Ubuntu or Debian Linux
A podman tutorial for beginners – part I (run Linux containers without Docker and in daemonless mode)
How to protect Linux against rogue USB devices using USBGuard
If your domain is not sending email, set these DNS settings to avoid spoofing and phishing
Join Patreon ➔