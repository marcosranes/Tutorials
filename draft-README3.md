
#` hi `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Hi</span>
```
lr -add a blank line row
sh -output history
bs -add back template string
rrt|s -recall and record
rt -get command line only, with MD as title styled
rs -get command line only, using $ in title styled
```


#` ifconfig `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Hi</span>
```
enp0s3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.0.2.15  netmask 255.255.255.0  broadcast 10.0.2.255
        inet6 fe80::f4de:b987:4f10:94e7  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:6f:38:9a  txqueuelen 1000  (Ethernet)
        RX packets 16291  bytes 13622045 (13.6 MB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 10665  bytes 2125393 (2.1 MB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 1835  bytes 234286 (234.2 KB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1835  bytes 234286 (234.2 KB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```

#` source ~/.bashrc `

#` ping 127.0.0.1 -c 10 -a `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Hi</span>
```
PING 127.0.0.1 (127.0.0.1) 56(84) bytes of data.
64 bytes from 127.0.0.1: icmp_seq=1 ttl=64 time=0.029 ms
64 bytes from 127.0.0.1: icmp_seq=2 ttl=64 time=0.052 ms
64 bytes from 127.0.0.1: icmp_seq=3 ttl=64 time=0.031 ms
64 bytes from 127.0.0.1: icmp_seq=4 ttl=64 time=0.051 ms
64 bytes from 127.0.0.1: icmp_seq=5 ttl=64 time=0.034 ms
64 bytes from 127.0.0.1: icmp_seq=6 ttl=64 time=0.029 ms
64 bytes from 127.0.0.1: icmp_seq=7 ttl=64 time=0.050 ms
64 bytes from 127.0.0.1: icmp_seq=8 ttl=64 time=0.032 ms

--- 127.0.0.1 ping statistics ---
8 packets transmitted, 8 received, 0% packet loss, time 7162ms
rtt min/avg/max/mdev = 0.029/0.038/0.052/0.009 ms
```


#` ls -la `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes</span>
```
total 232
drwxr-x--- 25 marcosranes marcosranes  4096 out 12 10:15 .
drwxr-xr-x  5 root        root         4096 set 22 03:24 ..
-rw-------  1 marcosranes marcosranes 34486 out 12 10:15 .bash_history
-rw-r--r--  1 marcosranes marcosranes   220 set 20 07:50 .bash_logout
-rw-r--r--  1 marcosranes marcosranes  5847 out 12 10:15 .bashrc
drwx------ 32 marcosranes marcosranes  4096 out 11 03:47 .cache
drwxr-xr-x 21 marcosranes marcosranes  4096 out 11 02:05 .config
drwx------  2 marcosranes marcosranes  4096 set 21 22:34 .cups
drwx------  3 marcosranes marcosranes  4096 set 20 08:02 .dbus
drwxr-xr-x 11 marcosranes marcosranes  4096 out 12 09:24 Desktop
drwxr-xr-x  2 marcosranes marcosranes  4096 set 23 09:02 Documents
drwxr-xr-x  2 marcosranes marcosranes  4096 set 20 08:20 Downloads
drwxr-xr-x  2 marcosranes marcosranes  4096 set 20 08:03 .fontconfig
-rw-rw-r--  1 marcosranes marcosranes    98 out  1 18:05 .gitconfig
drwx------  2 marcosranes marcosranes  4096 out 10 14:42 .gnupg
drwxr--r--  2 marcosranes marcosranes  4096 set 21 21:44 .hardinfo
-rw-rw-r--  1 marcosranes marcosranes   963 out 12 09:05 hi2.txt
drwxrwxr-x  4 marcosranes marcosranes  4096 set 21 06:35 .java
drwxr-xr-x  3 marcosranes marcosranes  4096 set 20 07:55 .local
drwx------  5 marcosranes marcosranes  4096 set 20 08:15 .mozilla
drwxr-xr-x  2 marcosranes marcosranes  4096 set 20 07:55 Music
-rw-------  1 marcosranes marcosranes   202 out  9 04:04 .netrc
drwxr-xr-x  2 marcosranes marcosranes  4096 out 11 03:54 Pictures
drwx------  3 marcosranes marcosranes  4096 set 20 08:21 .pki
-rw-r--r--  1 marcosranes marcosranes   807 set 20 07:50 .profile
drwxr-xr-x  2 marcosranes marcosranes  4096 set 20 07:55 Public
drwxrwxr-x 14 marcosranes marcosranes  4096 out  6 09:47 .pyenv
drwx------  3 marcosranes marcosranes  4096 out 10 09:17 snap
drwx------  2 marcosranes marcosranes  4096 out  1 18:36 .ssh
-rw-r--r--  1 marcosranes marcosranes     0 set 20 08:11 .sudo_as_admin_successful
drwxr-xr-x  2 marcosranes marcosranes  4096 set 20 07:55 Templates
drwx------  6 marcosranes marcosranes  4096 out  7 04:55 .thunderbird
-rw-r-----  1 marcosranes marcosranes     5 out 12 08:26 .vboxclient-clipboard.pid
-rw-r-----  1 marcosranes marcosranes     6 out 12 08:26 .vboxclient-display-svga-x11.pid
-rw-r-----  1 marcosranes marcosranes     5 out 12 08:26 .vboxclient-draganddrop.pid
-rw-r-----  1 marcosranes marcosranes     5 out 12 08:26 .vboxclient-seamless.pid
drwxr-xr-x  2 marcosranes marcosranes  4096 set 20 07:55 Videos
-rw-rw-r--  1 marcosranes marcosranes 49404 set 27 20:23 .zcompdump
```


#` pyenv versions `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes</span>
```
  system
  2.7.18
* 3.9.7 (set by PYENV_VERSION environment variable)
```


#` git status `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes</span>
```
```
#` git status `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Hi</span>
```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.idea/
	Pipfile
	draft-README.md

nothing added to commit but untracked files present (use "git add" to track)
```


#` git config --list `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Hi</span>
```
user.email=marcosranes@gmail.com
user.name=marcosranes
pull.ff=only
core.editor=nano
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
```


#` ls -a ~ `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Hi</span>
```
.
..
.bash_history
.bash_logout
.bashrc
.cache
.config
.cups
.dbus
Desktop
Documents
Downloads
.fontconfig
.gitconfig
.gnupg
.hardinfo
hi2.txt
.java
.local
.mozilla
Music
.netrc
Pictures
.pki
.profile
Public
.pyenv
snap
.ssh
.sudo_as_admin_successful
Templates
.thunderbird
.vboxclient-clipboard.pid
.vboxclient-display-svga-x11.pid
.vboxclient-draganddrop.pid
.vboxclient-seamless.pid
Videos
.zcompdump
```


#` ls -a ~/.ssh `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Hi</span>
```
.
..
id_ed25519
id_ed25519.pub
id_rsa_maso
id_rsa_maso.pub
known_hosts
```


##$ mv ~/.ssh/id_rsa_maso ~/.ssh/id_rsa_old

##$ mv ~/.ssh/id_rsa_maso.pub ~/.ssh/id_rsa_old.pub

##$ ls -a ~/.ssh
```
.
..
id_ed25519
id_ed25519.pub
id_rsa_old
id_rsa_old.pub
known_hosts
```

## You're loving it, aren't you?
### I guess you're loving wrapping your draft up such as The Flash, aren't you?
### so.. how did you do it?

##$ echo "### so.. how did you do it?!">>draft-README.md

#` rs `
Easy! Just typing these two keys `r + s`
```
$ echo "Easy! Just typing these two keys "'`r + s`'"">>draft-README.md
```
#` rt `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Hi</span>
```
-Succeeded!
#` rt `
```

```
Easy! Just typing these two keys `r + s`
```

##$ bs && echo "Easy! Just typing these two keys "'`r + s`'"">>draft-README.md && bs
```
Easy! Just typing these two keys `r + s`
```


### When writing also we can do it in such a nested way...
Once the line had been properly typed, and no longer you want this line for typing anymore, just pressing the ENTER key\ 
to skip to the next line.\
Note:
- If you get realized missing adding something, you can't get back for editing the previous line, but don't be concerned,\
you can make it later as soon as you have finished here;
- Once you have achieved your results and decided it's time to get out of here, don't miss pointing the file you want \
these lines to ECHO into, and also don't miss closing the line with a double string like as you've begun.\
So, there we go!\
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Hi</span>
```
### When writing also we can do it in such a nested way...
Once the line had been properly typed, and no longer you want this linefor typing anymore, just pressing the ENTER key to skip to the next line.Note:
- If you get realized missing to add something, you can't get back forediting the previous line, but don't be concerned, you can make it lateras soon as you have finished here;
- Once you have achieved your results and decided it's time to get out ofhere, don't miss pointing the file you want these lines to ECHO into, andalso don't miss closing the line with a double string like as you've begun.\  
So, there we go!
```
