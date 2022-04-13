# Climbimb VM's with Hashicorp Vagrant
```shell
devops3559@ubuntu-labs:~/Desktop/vagrant$ ls -a
.  ..  Automated_provisioning  Provisioned_VMs
devops3559@ubuntu-labs:~/Desktop/vagrant$ cd Provisioned_VMs/
devops3559@ubuntu-labs:~/Desktop/vagrant/Provisioned_VMs$ vagrant ssh web01
VM must be running to open SSH connection. Run `vagrant up`
to start the virtual machine.
devops3559@ubuntu-labs:~/Desktop/vagrant/Provisioned_VMs$ vagrant up web01
Bringing machine 'web01' up with 'virtualbox' provider...
==> web01: Checking if box 'ubuntu/xenial64' version '20211001.0.0' is up to date...
==> web01: Clearing any previously set forwarded ports...
==> web01: Clearing any previously set network interfaces...
==> web01: Preparing network interfaces based on configuration...
    web01: Adapter 1: nat
    web01: Adapter 2: hostonly
==> web01: Forwarding ports...
    web01: 22 (guest) => 2222 (host) (adapter 1)
==> web01: Running 'pre-boot' VM customizations...
==> web01: Booting VM...
==> web01: Waiting for machine to boot. This may take a few minutes...
    web01: SSH address: 127.0.0.1:2222
    web01: SSH username: vagrant
    web01: SSH auth method: private key
==> web01: Machine booted and ready!
[web01] GuestAdditions 6.1.32 running --- OK.
==> web01: Checking for guest additions in VM...
==> web01: Setting hostname...
==> web01: Configuring and enabling network interfaces...
==> web01: Mounting shared folders...
    web01: /vagrant => /home/devops3559/Desktop/vagrant/Provisioned_VMs
==> web01: [vagrant-hostmanager:guests] Updating hosts file on active guest virtual machines...
==> web01: [vagrant-hostmanager:host] Updating hosts file on your workstation (password may be required)...
==> web01: Machine already provisioned. Run `vagrant provision` or use the `--provision`
==> web01: flag to force provisioning. Provisioners marked to run always will still run.
devops3559@ubuntu-labs:~/Desktop/vagrant/Provisioned_VMs$
```
## `$ vagrant ssh web01`
```shell
devops3559@ubuntu-labs:~/Desktop/vagrant/Provisioned_VMs$ vagrant ssh web01
Welcome to Ubuntu 16.04.7 LTS (GNU/Linux 4.4.0-210-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

UA Infra: Extended Security Maintenance (ESM) is not enabled.

1 update can be applied immediately.
To see these additional updates run: apt list --upgradable

97 additional security updates can be applied with UA Infra: ESM
Learn more about enabling UA Infra: ESM service for Ubuntu 16.04 at
https://ubuntu.com/16-04

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

New release '18.04.6 LTS' available.
Run 'do-release-upgrade' to upgrade to it.


Last login: Sat Apr  9 11:15:18 2022 from 10.0.2.2
vagrant@web01:~$ 
```
