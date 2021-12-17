
## ` $ date `
```
Thu Dec 16 03:03:47 PM -03 2021
```
 
### Step by step - How many ways can I create a SSH key?

# ` $ git config -l `
```
-l stands for --list, in that case you ask git to list all their configuration, set for ~/gitconfig file that in turns is stored within your local home machine. Also `$ git config --list` means the same and outputs the same result.
user.email=marcosranes@gmail.com
user.name=marcosranes
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
remote.origin.url=git@github.com:marcosranes/Tutorials.git
remote.origin.fetch=+refs/heads/*:refs/remotes`/origin/*
branch.master.remote=origin
branch.master.merge=refs/heads/master
```

# ` $ ssh -T git@github.com `
```
Hi marcosranes! You've successfully authenticated, but GitHub does not provide shell access.
```
## ` $ git config --global user.name "marcosranes" `
## ` $ git config --global user.email "marcosranes@gmail.com" `

# ` $ git status `
```
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	typechange: draft-README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git_log.md
	test_folder/

no changes added to commit (use "git add" and/or "git commit -a")
```

# ` $ date `
```
Fri Dec 17 06:00:30 AM -03 2021
```
 
this is just an example
 
# teste teste teste teste teste
 
# today let's talk about Docker...

# ` $ docker image hello-world `

# ` $ cat dockerfile `
 
### the totorial was finished.. see you guys later.....
