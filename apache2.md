```shell
devops3559@ubuntu-labs:~$ sudo apt install apache2
Reading package lists... Done
Building dependency tree       
Reading state information... Done
apache2 is already the newest version (2.4.41-4ubuntu3.10).
apache2 set to manually installed.
The following packages were automatically installed and are no longer required:
  i965-va-driver intel-media-va-driver javascript-common libaacs0 libaom0 libass9 libavcodec58 libavformat58 libavutil56
  libbdplus0 libbluray2 libbs2b0 libchromaprint1 libcodec2-0.9 libflite1 libgme0 libgsm1 libigdgmm11 libjs-jquery
  libjs-underscore liblilv-0-0 libmysofa1 libnorm1 libopenmpt0 libpostproc55 librubberband2 libserd-0-0 libshine3
  libsnappy1v5 libsord-0-0 libsratom-0-0 libssh-gcrypt-4 libswresample3 libswscale5 libva-drm2 libva-x11-2 libva2
  libvdpau1 libvidstab1.1 libwxbase3.0-0v5 libwxgtk3.0-gtk3-0v5 libx265-179 libxvidcore4 libzvbi-common libzvbi0
  mesa-va-drivers mesa-vdpau-drivers pgadmin3-data va-driver-all vdpau-driver-all
Use 'sudo apt autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 1 not upgraded.
```


```shell
devops3559@ubuntu-labs:~$ sudo systemctl status apache2
[sudo] password for devops3559: 
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor pres>
     Active: active (running) since Wed 2022-04-13 11:48:53 CDT; 7h ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 910 ExecStart=/usr/sbin/apachectl start (code=exited, status=0/SU>
   Main PID: 1015 (apache2)
      Tasks: 83 (limit: 9132)
     Memory: 22.2M
     CGroup: /system.slice/apache2.service
             ├─1015 /usr/sbin/apache2 -k start
             ├─1016 /usr/sbin/apache2 -k start
             ├─1017 /usr/sbin/apache2 -k start
             └─1018 /usr/sbin/apache2 -k start

Apr 13 11:48:52 ubuntu-labs systemd[1]: Starting The Apache HTTP Server...
Apr 13 11:48:53 ubuntu-labs apachectl[952]: AH00558: apache2: Could not reliab>
Apr 13 11:48:53 ubuntu-labs systemd[1]: Started The Apache HTTP Server.
devops3559@ubuntu-labs:~$ 
```

## Make sure apache2 is starting on boot
```shell
devops3559@ubuntu-labs:~$ sudo systemctl is-enabled apache2.service
enabled
```
Otherwise...
```shell
devops3559@ubuntu-labs:~$ sudo systemctl enable apache2.service
```
## Make sure ufw is starting on boot
```
devops3559@ubuntu-labs:~$ sudo ufw allow 80/tcp comment 'accept Apache'
Rules updated
Rules updated (v6)
devops3559@ubuntu-labs:~$ sudo ufw allow 443/tcp comment 'accept HTTPS connections'
Rules updated
Rules updated (v6)
devops3559@ubuntu-labs:~$ sudo ufw status
Status: inactive
devops3559@ubuntu-labs:~$ sudo service ufw status
● ufw.service - Uncomplicated firewall
     Loaded: loaded (/lib/systemd/system/ufw.service; enabled; vendor preset: enabled)
     Active: active (exited) since Wed 2022-04-13 11:48:49 CDT; 7h ago
       Docs: man:ufw(8)
    Process: 332 ExecStart=/lib/ufw/ufw-init start quiet (code=exited, status=0/SUCCESS)
   Main PID: 332 (code=exited, status=0/SUCCESS)

Warning: journal has been rotated since unit was started, output may be incomplete.
devops3559@ubuntu-labs:~$ sudo service ufw restart
devops3559@ubuntu-labs:~$ sudo service ufw status
● ufw.service - Uncomplicated firewall
     Loaded: loaded (/lib/systemd/system/ufw.service; enabled; vendor preset: enabled)
     Active: active (exited) since Wed 2022-04-13 19:22:08 CDT; 3s ago
       Docs: man:ufw(8)
    Process: 27841 ExecStart=/lib/ufw/ufw-init start quiet (code=exited, status=0/SUCCESS)
   Main PID: 27841 (code=exited, status=0/SUCCESS)

Apr 13 19:22:08 ubuntu-labs systemd[1]: Starting Uncomplicated firewall...
Apr 13 19:22:08 ubuntu-labs systemd[1]: Finished Uncomplicated firewall.
devops3559@ubuntu-labs:~$ sudo ufw status
Status: inactive

devops3559@ubuntu-labs:~$ sudo ufw enable
Firewall is active and enabled on system startup
devops3559@ubuntu-labs:~$ sudo ufw status
Status: active

To                         Action      From
--                         ------      ----
80/tcp                     ALLOW       Anywhere                   # accept Apache
443/tcp                    ALLOW       Anywhere                   # accept HTTPS connections
80/tcp (v6)                ALLOW       Anywhere (v6)              # accept Apache
443/tcp (v6)               ALLOW       Anywhere (v6)              # accept HTTPS connections

devops3559@ubuntu-labs:~$ 
```

## Finding your Ubuntu 20.04 LTS IP address

```shell
devops3559@ubuntu-labs:~$ hostname -i
127.0.1.1
```
```shell
devops3559@ubuntu-labs:~$ ip a s lo
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
```
```shell
devops3559@ubuntu-labs:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp2s0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
    link/ether d0:94:66:cb:c0:3f brd ff:ff:ff:ff:ff:ff
3: wlp0s20f3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether 5c:cd:5b:e8:b1:e2 brd ff:ff:ff:ff:ff:ff
    inet 192.168.0.106/24 brd 192.168.0.255 scope global dynamic noprefixroute wlp0s20f3
       valid_lft 4643sec preferred_lft 4643sec
    inet6 fe80::e991:fd75:48f8:14b7/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
4: docker0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default 
    link/ether 02:42:dc:46:bd:a3 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
    inet6 fe80::42:dcff:fe46:bda3/64 scope link 
       valid_lft forever preferred_lft forever
5: br-8bb2524ee84c: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 02:42:b3:3a:fa:e4 brd ff:ff:ff:ff:ff:ff
    inet 172.27.0.1/16 brd 172.27.255.255 scope global br-8bb2524ee84c
       valid_lft forever preferred_lft forever
7: veth186b6dd@if6: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master docker0 state UP group default 
    link/ether 6e:8d:d5:9e:f7:ef brd ff:ff:ff:ff:ff:ff link-netnsid 0
    inet6 fe80::6c8d:d5ff:fe9e:f7ef/64 scope link 
       valid_lft forever preferred_lft forever
8: vboxnet0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 0a:00:27:00:00:00 brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.1/24 brd 192.168.56.255 scope global vboxnet0
       valid_lft forever preferred_lft forever
    inet6 fe80::800:27ff:fe00:0/64 scope link 
       valid_lft forever preferred_lft forever
```
If you are missing the popular ifconfig command for listing ip interfaces, be free to install it
```shell
devops3559@ubuntu-labs:~$ ifconfig

Command 'ifconfig' not found, but can be installed with:

sudo apt install net-tools
```
