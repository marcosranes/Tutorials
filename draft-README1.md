## ` $ date `
> sáb 16 out 2021 00:00:28 -03

## Git

> Let's get a look at some cases of usage to both Git and .gitignore in your favor.

Supposing you want to get the total control of a specific directory, sub-directory and files.
 
So, let's get our HOME aka `~`, which can be called by running `cd ~` in the terminal, and no matter where you are, this command will take you straight to your HOME, which we'll set for our version control.
 
So, firstly I'll show you my current path:

### ` $ pwd `
```shell
/home/marcosranes/Desktop/Tutorials/
```
However, once on your desktop screen, just press ctrl+alt+t, to call the terminal that will be initialized standing to your home.

### ` $ cd ~ `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes</span>
 
> So once into the target directory, follow these command lines below:

### ` $ git init `

### ` $ ls -la | grep gi `
```shell
drwxrwxr-x  7 marcosranes marcosranes  4096 out 16 04:27 .git
-rw-rw-r--  1 marcosranes marcosranes    98 out  1 18:05 .gitconfig
```
> As you can see, a `.git` directory has been initialized into your home successfully. So, let's go to investigate its status...

### ` $ git status | less `
```shell
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.bash_history
	.bash_logout
	.bashrc
	.cache/
	.config/
	.cups/
	.dbus/
	.fontconfig/
	.gitconfig
	.gnupg/
	.java/
	.local/
	.mozilla/
	.netrc
	.pki/
	.profile
	.pyenv/
	.ssh/
	.sudo_as_admin_successful
	.thunderbird/
	.vboxclient-clipboard.pid
	.vboxclient-display-svga-x11.pid
	.vboxclient-draganddrop.pid
	.vboxclient-seamless.pid
	.zcompdump
	Desktop/
	Documents/
	Downloads/
	Pictures/
	snap/

nothing added to commit but untracked files present (use "git add" to track)
```
 
> Let's set the branch to have the same directory name

### ` $ git branch -m home `
 
> If we run the git add command we would be adding the whole list for tracking, along with some bytes too, that'd result in some loss of pretty storage capacity for us. So, let's just get the current state and only track specific files, starting with creating the .gitignore file to ignore some of them.

### ` $ ls -a >> .gitignore `

### ` $ ls -la | grep git `

```shell
drwxrwxr-x  7 marcosranes marcosranes  4096 out 16 05:00 .git
-rw-rw-r--  1 marcosranes marcosranes    98 out  1 18:05 .gitconfig
-rw-rw-r--  1 marcosranes marcosranes   412 out 16 05:57 .gitignore
```
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes</span>

### ` $ git status `

```shell
On branch home

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```
 
> As you can see an entire list of both directories and files were ignored Lets set the files or directories we want to exclude from the .gitignore list in order to track them
> so let's go to open and edit the file, adding an `!` before each one them

### ` $ nano .gitignore `

### ` $ cat .gitignore `
```shell
.
..
.cache
.config
.cups
.dbus
Desktop
Documents
Downloads
.fontconfig
.git
.gnupg
.hardinfo
.java
.local
.mozilla
Music
.netrc
Pictures
.pki
Public
snap
.sudo_as_admin_successful
Templates
.thunderbird
.vboxclient-clipboard.pid
.vboxclient-display-svga-x11.pid
.vboxclient-draganddrop.pid
.vboxclient-seamless.pid
Videos
.zcompdump

# Git exclude files
!.bash_logout
!.gitignore
!.bashrc
!.ssh
!.pyenv
!.bash_history
!.gitconfig
!.profile
```

### ` $ git status `
```shell
On branch home

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.bash_history
	.bash_logout
	.bashrc
	.gitconfig
	.gitignore
	.profile
	.pyenv/
	.ssh/

nothing added to commit but untracked files present (use "git add" to track)
```

### ` $ git add . `
```shell
warning: adding embedded git repository: .pyenv
hint: You've added another git repository inside your current repository.
hint: Clones of the outer repository will not contain the contents of
hint: the embedded repository and will not know how to obtain it.
hint: If you meant to add a submodule, use:
hint: 
hint:   git submodule add <url> .pyenv
hint: 
hint: If you added this path by mistake, you can remove it from the
hint: index with:
hint: 
hint:   git rm --cached .pyenv
hint: 
hint: See "git help submodule" for more information.
```

### ` $ git status `
```shell
On branch home

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .bash_history
	new file:   .bash_logout
	new file:   .bashrc
	new file:   .gitconfig
	new file:   .gitignore
	new file:   .profile
	new file:   .pyenv
	new file:   .ssh/id_ed25519
	new file:   .ssh/id_ed25519.pub
	new file:   .ssh/id_rsa_old
	new file:   .ssh/id_rsa_old.pub
	new file:   .ssh/known_hosts
```

### ` $ git commit -m "files to be tracked" `
```shell
[home (root-commit) 037eb00] files to be tracked
 12 files changed, 2371 insertions(+)
 create mode 100644 .bash_history
 create mode 100644 .bash_logout
 create mode 100644 .bashrc
 create mode 100644 .gitconfig
 create mode 100644 .gitignore
 create mode 100644 .profile
 create mode 160000 .pyenv
 create mode 100644 .ssh/id_ed25519
 create mode 100644 .ssh/id_ed25519.pub
 create mode 100644 .ssh/id_rsa_old
 create mode 100644 .ssh/id_rsa_old.pub
 create mode 100644 .ssh/known_hosts
```

 
## So, just to finalize...

### ` $ git status `
```shell
On branch home
nothing to commit, working tree clean
```

### ` $ git branch `
```shell
* home
```

### ` $ git branch -v `
```shell
* home 037eb00 files to be tracked
```

### ` $ git log `
```shell
commit 037eb00a3c769264c93f841ce878edc4a4ab8557
Author: marcosranes <marcosranes@gmail.com>
Date:   Sat Oct 16 07:03:29 2021 -0300

    files to be tracked
```
 
> Now we're going to make three things:
> 1. Changing a tracked file
> 2. Add another one
> 3. Making changes to .gitignore

### ` $ echo "  `
```shell
> # Just a bind to a Git command
> alias group='git remote update --prune' " >> .bashrc
```

### ` $ alias group `

```shell
alias group
bash: alias: group: not found
```

### ` $ source .bashrc `

### ` $ alias group `
```shell
alias group='git remote update --prune'
```

### ` $ git status `
```shell
On branch home
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   .bashrc

no changes added to commit (use "git add" and/or "git commit -a")
```

### ` $ mkdir package_py && touch package_py/__init__.py `

### ` $ ls -a package_py/ `
```
.
..
__init__.py
```

### ` $ git status `
```shell
On branch home
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   .bashrc

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	package_py/

no changes added to commit (use "git add" and/or "git commit -a")
```

### ` $ echo " # added to ignore package_py" >> .gitignore `
```shell
marcosranes@ubuntu21-vbox:~$ echo "
> # added to ignore
> package_py" >> .gitignore
```
git status

### ` $ git status `
```shell
On branch home
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   .bashrc
	modified:   .gitignore

no changes added to commit (use "git add" and/or "git commit -a")
```

### ` $ git diff `
```shell
diff --git a/.bashrc b/.bashrc
index eba2b85..168ee1f 100644
--- a/.bashrc
+++ b/.bashrc
@@ -236,3 +236,6 @@ alias share="sudo mount -t vboxsf WinShare ~/Desktop/WinShare/"
 #alias mng='python /home/marcosranes/Desktop/django-app/.venv/../manage.py'
 #alias mng="python $VIRTUAL_ENV/../manage.py"
 alias mng='python $VIRTUAL_ENV/../manage.py'
+
+# Just a bind to a Git command
+alias group='git remote update --prune'
diff --git a/.gitignore b/.gitignore
index 15bc2a2..bcdd547 100644
--- a/.gitignore
+++ b/.gitignore
@@ -40,3 +40,5 @@ Videos
 !.gitconfig
 !.profile
 
+# added to ignore
+package_py
```
 
## Let's create a PRIVATE remote repository to make safe these important files in a backup.

### ` $ git remote add upstream git@github.com:PortalNetZone/backup_home.git `

### ` $ git remote -v `
```shell
upstream	git@github.com:PortalNetZone/backup_home.git (fetch)
upstream	git@github.com:PortalNetZone/backup_home.git (push)
```

### ` $ git status `
```shell
On branch home
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   .bashrc
	modified:   .gitignore

no changes added to commit (use "git add" and/or "git commit -a")
```

### ` $ git add . `

### ` $ git commit -m "added new files" `
```shell
[home a07a5ee] added new files
 2 files changed, 5 insertions(+)
```

### ` $ git status `
```shell
On branch home
nothing to commit, working tree clean
```

### ` $ git branch -v `
```shell
* home a07a5ee added new files
```

### ` $ git push -u upstream home `
```shell
-Succeeded!
git push -u upstream home
Enumerating objects: 18, done.
Counting objects: 100% (18/18), done.
Delta compression using up to 4 threads
Compressing objects: 100% (18/18), done.
Writing objects: 100% (18/18), 15.69 KiB | 5.23 MiB/s, done.
Total 18 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), done.
To github.com:PortalNetZone/backup_home.git
 * [new branch]      home -> home
```

### ` $ git log `
```shell
commit a07a5eec2d9ec7e33bae11436244d2c195589381 (HEAD -> home, upstream/home)
Author: marcosranes <marcosranes@gmail.com>
Date:   Sat Oct 16 08:57:39 2021 -0300

    added new files

commit 037eb00a3c769264c93f841ce878edc4a4ab8557
Author: marcosranes <marcosranes@gmail.com>
Date:   Sat Oct 16 07:03:29 2021 -0300

    files to be tracked
```

### ` $ git branch -a `
```shell
* home
  remotes/upstream/home
```
 
### Oops! I almost forgot about that alias we've created for running the `git remote update --prune` command which we've defined as `group`. So, once we have a link with the remote repository, we should use it for fetching the newest remote updates

### ` $ group `
```shell
Fetching upstream
```
 
### So, both our local branch and remote are synced. But I use to make some changes in the README.md file by there, lets see...



### ` $ group `
```shell
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 666 bytes | 666.00 KiB/s, done.
From github.com:PortalNetZone/backup_home
   a07a5ee..6a7ff3a  home       -> upstream/home
```

 
### Taking the git status, we propably see that our local branch is behind the remote

### ` $ git status `
```shell
On branch home
Your branch is behind 'upstream/home' by 1 commit, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
```

### ` $ git pull `
```shell
Updating a07a5ee..6a7ff3a
Fast-forward
 README.md | 2 ++
 1 file changed, 2 insertions(+)
 create mode 100644 README.md
```

## ` $ git status `
```shell
On branch home
Your branch is up to date with 'upstream/home'.

nothing to commit, working tree clean
```















