
## ` $ date `
```
Sat Dec 18 11:53:40 AM -03 2021
```
 
Let's see some of different ways to make you machine to rest while you aren't using it and you wish it to keep your current stuffs available for you later.

# ` $ sudo apt install molly-guard `
```
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  chromium-codecs-ffmpeg-extra gstreamer1.0-vaapi libgstreamer-plugins-bad1.0-0 libva-wayland2
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  molly-guard
0 upgraded, 1 newly installed, 0 to remove and 47 not upgraded.
Need to get 12.3 kB of archives.
After this operation, 57.3 kB of additional disk space will be used.
Get:1 http://us.archive.ubuntu.com/ubuntu impish/universe amd64 molly-guard all 0.7.2 [12.3 kB]
Fetched 12.3 kB in 1s (15.2 kB/s)                      
Selecting previously unselected package molly-guard.
(Reading database ... 203077 files and directories currently installed.)
Preparing to unpack .../molly-guard_0.7.2_all.deb ...
No diversion 'diversion of /sbin/pm-hibernate by molly-guard', none removed.
No diversion 'diversion of /sbin/pm-suspend by molly-guard', none removed.
No diversion 'diversion of /sbin/pm-suspend-hybrid by molly-guard', none removed.
Adding 'diversion of /sbin/halt to /lib/molly-guard/halt by molly-guard'
Adding 'diversion of /sbin/poweroff to /lib/molly-guard/poweroff by molly-guard'
Adding 'diversion of /sbin/reboot to /lib/molly-guard/reboot by molly-guard'
Adding 'diversion of /sbin/shutdown to /lib/molly-guard/shutdown by molly-guard'
Adding 'diversion of /sbin/coldreboot to /lib/molly-guard/coldreboot by molly-guard'
Adding 'diversion of /usr/sbin/pm-hibernate to /lib/molly-guard/pm-hibernate by molly-guard'
Adding 'diversion of /usr/sbin/pm-suspend to /lib/molly-guard/pm-suspend by molly-guard'
Adding 'diversion of /usr/sbin/pm-suspend-hybrid to /lib/molly-guard/pm-suspend-hybrid by molly-
guard'
Unpacking molly-guard (0.7.2) ...
Setting up molly-guard (0.7.2) ...
Processing triggers for man-db (2.9.4-2) ...
```
# ` $ sudo apt install pm-utils `
```
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages were automatically installed and are no longer required:
  chromium-codecs-ffmpeg-extra gstreamer1.0-vaapi libgstreamer-plugins-bad1.0-0 libva-wayland2
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  ethtool libx86-1 vbetool
Suggested packages:
  cpufrequtils radeontool
The following NEW packages will be installed:
  ethtool libx86-1 pm-utils vbetool
0 upgraded, 4 newly installed, 0 to remove and 47 not upgraded.
Need to get 332 kB of archives.
After this operation, 1,146 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us.archive.ubuntu.com/ubuntu impish/main amd64 ethtool amd64 1:5.9-1build1 [195 kB]
Get:2 http://us.archive.ubuntu.com/ubuntu impish/universe amd64 libx86-1 amd64 1.1+ds1-12 [77.3 kB]
Get:3 http://us.archive.ubuntu.com/ubuntu impish/universe amd64 pm-utils all 1.4.1-19 [48.1 kB]
Get:4 http://us.archive.ubuntu.com/ubuntu impish/universe amd64 vbetool amd64 1.1-5 [11.8 kB]
Fetched 332 kB in 1s (236 kB/s)    
Selecting previously unselected package ethtool.
(Reading database ... 203105 files and directories currently installed.)
Preparing to unpack .../ethtool_1%3a5.9-1build1_amd64.deb ...
Unpacking ethtool (1:5.9-1build1) ...
Selecting previously unselected package libx86-1:amd64.
Preparing to unpack .../libx86-1_1.1+ds1-12_amd64.deb ...
Unpacking libx86-1:amd64 (1.1+ds1-12) ...
Selecting previously unselected package pm-utils.
Preparing to unpack .../pm-utils_1.4.1-19_all.deb ...
Unpacking pm-utils (1.4.1-19) ...
Selecting previously unselected package vbetool.
Preparing to unpack .../vbetool_1.1-5_amd64.deb ...
Unpacking vbetool (1.1-5) ...
Setting up libx86-1:amd64 (1.1+ds1-12) ...
Setting up vbetool (1.1-5) ...
Setting up pm-utils (1.4.1-19) ...
Setting up ethtool (1:5.9-1build1) ...
Processing triggers for man-db (2.9.4-2) ...
Processing triggers for libc-bin (2.34-0ubuntu3) ...
```
# ` $ systemctl suspend `

