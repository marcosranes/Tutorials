# ` $ date `
```
seg 18 out 2021 08:26:14 -03
```
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
 
## Seeing a tree structure of directories from the terminal

Let's get started by getting and installing this powerful tool for Debian / Mint / Ubuntu Linux Systems.

For other systems, see below...

### ` $ yum install tree `
For RHEL / CentOS / Fedora Linux that uses the `yum` command, or...
### ` $ dnf install tree `
For CentOS/RHEL 8.x and Fedora that uses the `dnf`.
### ` $ brew install tree `
For Apple OS X/macOS, through brew command. Note, Homebrew is required...

## So, for sudoers based systems...

## ` $ sudo apt install tree `
```
Reading package lists...
Building dependency tree...
Reading state information...
The following packages were automatically installed and are no longer required:
  chromium-codecs-ffmpeg-extra gstreamer1.0-vaapi i965-va-driver
  intel-media-va-driver libaacs0 libaom0 libass9 libavcodec58 libavformat58
  libavutil56 libbdplus0 libblas3 libbluray2 libbs2b0 libchromaprint1
  libcodec2-0.9 libdav1d4 libfftw3-double3 libflite1 libgme0 libgsm1
  libgstreamer-plugins-bad1.0-0 libigdgmm11 liblilv-0-0 libllvm11 libmfx1
  libmysofa1 libnorm1 libopenmpt0 libpgm-5.3-0 libpostproc55 librabbitmq4
  librubberband2 libserd-0-0 libshine3 libsnappy1v5 libsord-0-0 libsratom-0-0
  libsrt1.4-gnutls libssh-gcrypt-4 libswresample3 libswscale5 libudfread0
  libva-drm2 libva-wayland2 libva-x11-2 libva2 libvdpau1 libvidstab1.1
  libx265-192 libxvidcore4 libzmq5 libzvbi-common libzvbi0 mesa-va-drivers
  mesa-vdpau-drivers net-tools pocketsphinx-en-us va-driver-all
  vdpau-driver-all
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
  tree
0 upgraded, 1 newly installed, 0 to remove and 1 not upgraded.
Need to get 43,0 kB of archives.
After this operation, 115 kB of additional disk space will be used.
Get:1 http://us.archive.ubuntu.com/ubuntu hirsute/universe amd64 tree amd64 1.8.0-1 [43,0 kB]
Fetched 43,0 kB in 1s (32,6 kB/s)
Selecting previously unselected package tree.
(Reading database ... 
(Reading database ... 5%
(Reading database ... 10%
(Reading database ... 15%
(Reading database ... 20%
(Reading database ... 25%
(Reading database ... 30%
(Reading database ... 35%
(Reading database ... 40%
(Reading database ... 45%
(Reading database ... 50%
(Reading database ... 55%
(Reading database ... 60%
(Reading database ... 65%
(Reading database ... 70%
(Reading database ... 75%
(Reading database ... 80%
(Reading database ... 85%
(Reading database ... 90%
(Reading database ... 95%
(Reading database ... 100%
(Reading database ... 270159 files and directories currently installed.)
Preparing to unpack .../tree_1.8.0-1_amd64.deb ...
Unpacking tree (1.8.0-1) ...
Setting up tree (1.8.0-1) ...
Processing triggers for man-db (2.9.4-2) ...
```

## ` $ tree `
```
.
├── draft-README1.md
├── draft-README3.md
├── draft-README4.md
├── draft-README5.md
├── draft-README6.md
├── draft-README7.md
├── draft-README8.md
├── draft-README.md
├── Pipfile
└── Pipfile.lock

0 directories, 10 files
```

### Single Usage:
> tree\
tree /path/to/directory\
tree [options]\
tree [options] /path/to/directory

### Some usage example bellow:

But, firstly my location for a better understanding to the commands we're about to see\
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>

As I don't like having too many lines to populate on that tutorial, I decided to have a small file located in my Desktop aka Hi as an example.

### So, here we go...

## ` $ tree ../Hi `
```
../Hi
├── db.sqlite3
├── djangoapp
│   ├── asgi.py
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-39.pyc
│   │   ├── settings.cpython-39.pyc
│   │   ├── urls.cpython-39.pyc
│   │   └── wsgi.cpython-39.pyc
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── draft.bashrc
├── draftLTS.bashrc
├── draft-README1.md
├── draft-README2.md
├── hi
├── LICENSE
├── manage.py
├── Pipfile
└── Pipfile.lock

2 directories, 19 files
```

## ` $ tree ../Hi | grep .py `
```
│   ├── asgi.py
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-39.pyc
│   │   ├── settings.cpython-39.pyc
│   │   ├── urls.cpython-39.pyc
│   │   └── wsgi.cpython-39.pyc
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
```
Sample outputs and specific searching...
 
### Showing all files including the hidden files with `-a` parameter

## ` $ tree -a ../Hi/ | grep env `
```shell
└── .venv
    │   ├── python -> /home/marcosranes/.pyenv/versions/3.9.7/bin/python3.9
    │           │   │   │   │   ├── envelope.py
    │           │   │   │   │   │   ├── envelope.cpython-39.pyc
    │           │   │   ├── build_env.py
    │           │   │   │   ├── build_env.cpython-39.pyc
    │           │   │   │   │   ├── virtualenv.cpython-39.pyc
    │           │   │   │   ├── virtualenv.py
    │           │       │   ├── envbuild.py
    │           │       │   │   ├── _appengine_environ.py
    │           │       │   │   │   ├── _appengine_environ.cpython-39.pyc
    │           ├── pip-21.2.4.virtualenv
    │           │   └── _virtualenv.cpython-39.pyc
    │           │       │   ├── Denver
    │           ├── setuptools-58.1.0.virtualenv
    │           ├── _virtualenv.pth
    │           ├── _virtualenv.py
    │           └── wheel-0.37.0.virtualenv
    ├── pyvenv.cfg
```
###
## hum... so let's get a look at something here...

## ` $ tree ~/ | grep gitignore `
> Okay, as expected nothing to show...



## ` $ tree ~/ -a | grep gitignore `
```
│   │       │   │   ├── mobi_hsz_idea_gitignore_dark.svg
│   │       │   │   ├── mobi_hsz_idea_gitignore.svg
│   │   │   │   ├── .gitignore
│   │   │       ├── .gitignore
│   │       │   ├── .gitignore
│   │           ├── .gitignore
│   │   │   ├── .gitignore
│   │       ├── .gitignore
│   │   │   ├── .gitignore
│   │   ├── .gitignore
│   │   │   ├── .gitignore
│   │       ├── .gitignore
│   │   ├── .gitignore
│   │   │   ├── .gitignore
│   │       ├── .gitignore
│   │   │   │   ├── .gitignore
│   │   │       ├── .gitignore
│   │       ├── .gitignore
│   │   ├── .gitignore
│   │   │   ├── .gitignore
│   │   │   ├── .gitignore
│   │       ├── .gitignore
│       │   ├── .gitignore
├── .gitignore
│   ├── .gitignore
│   │   ├── .gitignore
│   │   │   ├── .gitignore
│   │   │   ├── .gitignore
│   │   │   ├── .gitignore
│   │   │   ├── .gitignore
│   │   │   │   │   └── .gitignore
│   │   │   ├── .gitignore
│   │           │   └── .gitignore
│   │       │   └── .gitignore
│   │           └── .gitignore
```
###
### Listing directories only

## ` $ tree -d `
```
.

0 directories
```
As you can see there's nothing to show here. However, I could use that command along with the `-a` parameter to show the hidden files, once I'm sure that the Tutorials folder is added to a Git version control that includes hidden directories.

I won't do that for now as we've ever seen several examples here, and in order to avoid too many rows being populated here in this tutorial, but you can try it. 

You also can use pipe less `| less` to scrolling its displaying. Example: `$ tree -d -a | less`.

### So just to finalize, when you're in doubt you should try `tree --help` as soon as you need.
## ` $ tree --help `
```
usage: tree [-acdfghilnpqrstuvxACDFJQNSUX] [-H baseHREF] [-T title ]
	[-L level [-R]] [-P pattern] [-I pattern] [-o filename] [--version]
	[--help] [--inodes] [--device] [--noreport] [--nolinks] [--dirsfirst]
	[--charset charset] [--filelimit[=]#] [--si] [--timefmt[=]<f>]
	[--sort[=]<name>] [--matchdirs] [--ignore-case] [--fromfile] [--]
	[<directory list>]
  ------- Listing options -------
  -a            All files are listed.
  -d            List directories only.
  -l            Follow symbolic links like directories.
  -f            Print the full path prefix for each file.
  -x            Stay on current filesystem only.
  -L level      Descend only level directories deep.
  -R            Rerun tree when max dir level reached.
  -P pattern    List only those files that match the pattern given.
  -I pattern    Do not list files that match the given pattern.
  --ignore-case Ignore case when pattern matching.
  --matchdirs   Include directory names in -P pattern matching.
  --noreport    Turn off file/directory count at end of tree listing.
  --charset X   Use charset X for terminal/HTML and indentation line output.
  --filelimit # Do not descend dirs with more than # files in them.
  --timefmt <f> Print and format time according to the format <f>.
  -o filename   Output to file instead of stdout.
  ------- File options -------
  -q            Print non-printable characters as '?'.
  -N            Print non-printable characters as is.
  -Q            Quote filenames with double quotes.
  -p            Print the protections for each file.
  -u            Displays file owner or UID number.
  -g            Displays file group owner or GID number.
  -s            Print the size in bytes of each file.
  -h            Print the size in a more human readable way.
  --si          Like -h, but use in SI units (powers of 1000).
  -D            Print the date of last modification or (-c) status change.
  -F            Appends '/', '=', '*', '@', '|' or '>' as per ls -F.
  --inodes      Print inode number of each file.
  --device      Print device ID number to which each file belongs.
  ------- Sorting options -------
  -v            Sort files alphanumerically by version.
  -t            Sort files by last modification time.
  -c            Sort files by last status change time.
  -U            Leave files unsorted.
  -r            Reverse the order of the sort.
  --dirsfirst   List directories before files (-U disables).
  --sort X      Select sort: name,version,size,mtime,ctime.
  ------- Graphics options -------
  -i            Don't print indentation lines.
  -A            Print ANSI lines graphic indentation lines.
  -S            Print with CP437 (console) graphics indentation lines.
  -n            Turn colorization off always (-C overrides).
  -C            Turn colorization on always.
  ------- XML/HTML/JSON options -------
  -X            Prints out an XML representation of the tree.
  -J            Prints out an JSON representation of the tree.
  -H baseHREF   Prints out HTML format with baseHREF as top directory.
  -T string     Replace the default HTML title and H1 header with string.
  --nolinks     Turn off hyperlinks in HTML output.
  ------- Input options -------
  --fromfile    Reads paths from files (.=stdin)
  ------- Miscellaneous options -------
  --version     Print version and exit.
  --help        Print usage and this help message and exit.
  --            Options processing terminator.
```

### Thank you guys for reading this tutorial. See you all next time!
