
## ` $ date `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
dom 31 out 2021 12:17:43 -03
```
## ` $ git init project1 `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint:   git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint:   git branch -m <name>
Initialized empty Git repository in /home/marcosranes/Desktop/Tutorials/project1/.git/
```
## ` $ cd project1 `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials/project1</span>

### ` $ ls -la `
```
total 12
drwxrwxr-x 3 marcosranes marcosranes 4096 out 31 12:16 .
drwxrwxr-x 6 marcosranes marcosranes 4096 out 31 12:21 ..
drwxrwxr-x 7 marcosranes marcosranes 4096 out 31 12:16 .git
```
 
Now let's see some commands. Just to keep in this tutorial. Also, I'm going to leave a breaf description of some of them

### ` $ git branch -a `

### ` $ git remote -v `

### ` $ git remote update --prune `

### ` $ git checkout -b developer `
```
Switched to a new branch 'developer'
```

### ` $ git status `
```
On branch developer

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

### ` $ git log `
```
fatal: your current branch 'developer' does not have any commits yet
```
### ` $ git branch -d developer `
```shell
fatal: Couldn't look up commit object for HEAD
```
### ` $ git branch -D developer `
```shell
error: Cannot delete branch 'developer' checked out at '/home/marcosranes/Desktop/Tutorials/project1'
```
 
### As you can see, for having things working fine on Git, you'll need at least, 1 file do add here, and a first commit.. so, let's make it.
 
I'm going to delete the project1 and create a new one

<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials/project1</span>
### ` rm -rf ../project1/ ` and ` cd .. `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>

### ` $ git init project1 && cd project1 `
```
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint:   git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint:   git branch -m <name>
Initialized empty Git repository in /home/marcosranes/Desktop/Tutorials/project1/.git/
```
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials/project1</span>
 
Git init left some tips, so let's change the branch master to main...

### ` $ git status | grep ma `
```
On branch master
```

### ` $ git branch -m main `

### ` $ git status | grep ma `
```
On branch main
```
Let's give at least one file to this project1, then add it to staged area, and make the first commit...

### ` $ touch README.md `

### ` $ ls -la `
```
total 12
drwxrwxr-x 3 marcosranes marcosranes 4096 out 31 13:35 .
drwxrwxr-x 6 marcosranes marcosranes 4096 out 31 13:33 ..
drwxrwxr-x 7 marcosranes marcosranes 4096 out 31 13:27 .git
-rw-rw-r-- 1 marcosranes marcosranes    0 out 31 13:35 README.md
```

### ` $ echo "# This is a tutorial to learn about Git" >> README.md `

### ` $ cat README.md `
```
# This is a tutorial to learn about Git
```

### ` $ ls -la `
```
total 16
drwxrwxr-x 3 marcosranes marcosranes 4096 out 31 13:35 .
drwxrwxr-x 6 marcosranes marcosranes 4096 out 31 13:33 ..
drwxrwxr-x 7 marcosranes marcosranes 4096 out 31 13:27 .git
-rw-rw-r-- 1 marcosranes marcosranes   40 out 31 13:42 README.md
```

### ` $ git status `
```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	README.md

nothing added to commit but untracked files present (use "git add" to track)
```

### ` $ git add README.md `

### ` $ git status `
```
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   README.md

```

### ` $ git commit -m "added readme file" `
```
[main (root-commit) 00df5ba] added readme file
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
```

### ` $ git status `
```
On branch main
nothing to commit, working tree clean
```
 
### So, after that Git keeps recorded all changes we made under this branch. Let's investigate this...

### ` $ git log `
```
commit 00df5ba6373e42e8992c66be52280672d86a85f3
Author: marcosranes <marcosranes@gmail.com>
Date:   Sun Oct 31 13:46:04 2021 -0300

    added readme file
```

### ` $ git branch -a `
```
* main
```

### ` $ tree -a ../project1/ `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials/project1</span>
```
../project1/
├── .git
│   ├── branches
│   ├── COMMIT_EDITMSG
│   ├── config
│   ├── description
│   ├── HEAD
│   ├── hooks
│   │   ├── applypatch-msg.sample
│   │   ├── commit-msg.sample
│   │   ├── fsmonitor-watchman.sample
│   │   ├── post-update.sample
│   │   ├── pre-applypatch.sample
│   │   ├── pre-commit.sample
│   │   ├── pre-merge-commit.sample
│   │   ├── prepare-commit-msg.sample
│   │   ├── pre-push.sample
│   │   ├── pre-rebase.sample
│   │   ├── pre-receive.sample
│   │   ├── push-to-checkout.sample
│   │   └── update.sample
│   ├── index
│   ├── info
│   │   └── exclude
│   ├── logs
│   │   ├── HEAD
│   │   └── refs
│   │       └── heads
│   │           └── main
│   ├── objects
│   │   ├── 00
│   │   │   └── df5ba6373e42e8992c66be52280672d86a85f3
│   │   ├── 7a
│   │   │   └── fbd3e9f575651293fe40f764d472f1b836da3f
│   │   ├── a4
│   │   │   └── b2ce68b1202a06eac0c3208c4f945868f09645
│   │   ├── info
│   │   └── pack
│   └── refs
│       ├── heads
│       │   └── main
│       └── tags
└── README.md

16 directories, 26 files
```
 
## Toggling between branches
 
By the time you create a new branch, it takes the Git current state by heritage, in which you can introduce the newest features for coming, This also keeps one of these branches untouchable, which allows you can even get back to an earlier state.

### ` $ git branch backup `

### ` $ git branch -a `
```
  backup
* main
```

### ` $ git checkout backup `
```
Switched to branch 'backup'
```
### ` $ git branch -a `
```
* backup
  main
``` 
But we can make it shortened. The command below will create and checkout at the same time..

### ` $ git checkout -b backup `
```
Switched to a new branch 'backup'
```
### Deleting branches
Actually there are two ways...
### ` $ git branch -d backup ` and ` $ git branch -D backup `
```
Deleted branch backup (was 00df5ba).
```
###
After you made changes to it...
### ` $ git branch -D backup `
### For remote branches
Associating to a remote void repository..\
` $ git remote add origin git@github.com:marcosranes/Tutorials.git `

How to disassociate a remote repository..\
` $ git remote remove origin `
```shell
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials/project1$ git remote add origin git@github.com:marcosranes/Tutorials.git
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials/project1$ git remote -v
origin  git@github.com:marcosranes/Tutorials.git (fetch)
origin  git@github.com:marcosranes/Tutorials.git (push)
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials/project1$ git remote remove origin
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials/project1$ git remote -v
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials/project1$ 
```
Leading with remote branches... See [here](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes).
### ` $ touch .gitignore `
```shell
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ echo ".idea/
> .venv/" >> .gitignore
```

### ` $ cat .gitignore `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
.idea/
.venv/
```

### ` $ git status `
```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore
	Git.md
	Pipenv.md
	Pipfile
	Pipfile.lock
	Pyenv.md
	SHE-BANGs.md
	Tree_Command.md
	draft-README-pipenv.md
	draft-README.md
	draft-README1.md
	draft-README3.md
	draft-README4.md
	draft-README5.md
	draft-README6.md
	draft-README7.md
	draft-README8.md
	myscript.py
	myscript.sh
	project1/

nothing added to commit but untracked files present (use "git add" to track)
```

### ` $ git add . `
```
warning: adding embedded git repository: project1
hint: You've added another git repository inside your current repository.
hint: Clones of the outer repository will not contain the contents of
hint: the embedded repository and will not know how to obtain it.
hint: If you meant to add a submodule, use:
hint: 
hint:   git submodule add <url> project1
hint: 
hint: If you added this path by mistake, you can remove it from the
hint: index with:
hint: 
hint:   git rm --cached project1
hint: 
hint: See "git help submodule" for more information.
```
Above Git complains of a folder with .git within too. As we won't need let's just ignore it by adding to git ignore, but 
I think it went to stage when running `git add .`

### ` $ git status `
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .gitignore
	new file:   Git.md
	new file:   Pipenv.md
	new file:   Pipfile
	new file:   Pipfile.lock
	new file:   Pyenv.md
	new file:   SHE-BANGs.md
	new file:   Tree_Command.md
	new file:   draft-README-pipenv.md
	new file:   draft-README.md
	new file:   draft-README1.md
	new file:   draft-README3.md
	new file:   draft-README4.md
	new file:   draft-README5.md
	new file:   draft-README6.md
	new file:   draft-README7.md
	new file:   draft-README8.md
	new file:   myscript.py
	new file:   myscript.sh
	new file:   project1

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   Git.md

```
### ` $ git reset project1/ `
```
Unstaged changes after reset:
M       Git.md
```

### ` $ echo "project1/" >> .gitignore `

### ` $ cat .gitignore `
```
.idea/
.venv/
project1/
```

### ` $ git status `
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   .gitignore
	new file:   Git.md
	new file:   Pipenv.md
	new file:   Pipfile
	new file:   Pipfile.lock
	new file:   Pyenv.md
	new file:   SHE-BANGs.md
	new file:   Tree_Command.md
	new file:   draft-README-pipenv.md
	new file:   draft-README.md
	new file:   draft-README1.md
	new file:   draft-README3.md
	new file:   draft-README4.md
	new file:   draft-README5.md
	new file:   draft-README6.md
	new file:   draft-README7.md
	new file:   draft-README8.md
	new file:   myscript.py
	new file:   myscript.sh

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   .gitignore
	modified:   Git.md

```

### ` $ git add . `

### ` $ git status `
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   .gitignore
        new file:   Git.md
        new file:   Pipenv.md
        new file:   Pipfile
        new file:   Pipfile.lock
        new file:   Pyenv.md
        new file:   SHE-BANGs.md
        new file:   Tree_Command.md
        new file:   draft-README-pipenv.md
        new file:   draft-README.md
        new file:   draft-README1.md
        new file:   draft-README3.md
        new file:   draft-README4.md
        new file:   draft-README5.md
        new file:   draft-README6.md
        new file:   draft-README7.md
        new file:   draft-README8.md
        new file:   myscript.py
        new file:   myscript.sh
```
