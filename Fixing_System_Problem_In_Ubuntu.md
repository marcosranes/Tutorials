# ` $ date `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
Sat 26 Mar 2022 02:49:39 PM -03
```
# How To Fix System Program Problem Detected In Ubuntu
## Solution...
Open your system with your user root (sudo), go to var/crash.. within that directory is where you'll find out more about the system crashes.. there we go...


## ` $ cd /var `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /var</span>
```
```

## ` $ ls -a `
```
.
..
backups
cache
crash
lib
local
lock
log
mail
metrics
opt
run
snap
spool
tmp
```

## ` $ ls -a crash/ `
```
.
..
_opt_google_chrome_chrome.1000.crash
_usr_libexec_evolution-calendar-factory.1000.crash
_usr_lib_systemd_systemd-logind.0.crash
_usr_lib_systemd_systemd-resolved.101.crash
_usr_lib_systemd_systemd-timesyncd.102.crash
_usr_lib_systemd_systemd-udevd.0.crash
_usr_share_apport_apport-gtk.1000.crash
```
 
## So, we need to clear this folder and delete all of .crash files..

# ` $ sudo rm /var/crash/* `


## ` $ ls -a /var/crash/ `
```
.
..
```
 
### Now, that's cleared. Restart your system.
