
## ` $ date `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
Tue Dec 14 08:47:52 PM -03 2021
```
 
# What we can do with git log
## Let's see some commands lines which will provide us a new perspective...

## ` $ git log `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
commit 9bb35947b9770bfb6a0e4bbe2610a44fe159b18c
Author: marcosranes <marcosranes@gmail.com>
Date:   Sun Dec 12 08:16:32 2021 -0300

    added file

commit d985c354b1f1eaa2cb83ba6e37fb36424e4a5af8
Author: Marcos Ranes <marcosranes@gmail.com>
Date:   Tue Dec 7 22:18:15 2021 -0800

    Update Git.md
    
    just proofreading the text

commit 852239f2c54493d944997ce2997da4064a9fc86a
Author: marcosranes <marcosranes@gmail.com>
Date:   Sun Nov 28 23:27:44 2021 -0300

    files updated

commit d6fc4d3f15ab671c87a070b10f717b586321dcf1
Author: marcosranes <marcosranes@gmail.com>
Date:   Mon Nov 1 14:03:40 2021 -0300

    added pytest tutorial

commit a190f614aef326f8d0be68b5f84828512e02d5c6
Author: Marcos Ranes <marcosranes@gmail.com>
Date:   Sun Oct 31 20:12:08 2021 -0300

    Update Git.md
    
    Just proofreading the text...

commit 16ec053b9c348ab877d69346b76bb91a86fb658c
Author: Marcos Ranes <marcosranes@gmail.com>
Date:   Sun Oct 31 19:59:02 2021 -0300

    Update README.md
    
    Just proofreading the text

commit e19923de386faee50e98beaccda4b3c54d885800
Author: Marcos Ranes <marcosranes@gmail.com>
Date:   Sun Oct 31 19:51:13 2021 -0300

    Create README.md

commit 36f712d8302d00031bb06dcc990f770aa776b463
Author: Marcos Ranes <marcosranes@gmail.com>
Date:   Sun Oct 31 19:20:58 2021 -0300

    Update Pipenv.md
    
    Just proofreading the text...

commit 1dd9116293ba5b8593f2093feb0756a1b5e0aa52
Author: Marcos Ranes <marcosranes@gmail.com>
Date:   Sun Oct 31 19:12:59 2021 -0300

    Update Pipenv.md
    
    Just proofreading the text...

commit dd8f08311a976c293a216a092ef22f79b35abeb0
Author: marcosranes <marcosranes@gmail.com>
Date:   Sun Oct 31 19:00:05 2021 -0300

    file updated

commit c2f5a7dbb34903472fb2eeab243bf413c8013965
Author: Marcos Ranes <marcosranes@gmail.com>
Date:   Sun Oct 31 17:55:20 2021 -0300

    Update Git.md
    
    Just proofreading the text...

commit e0be795ae14bfc5e84247bc9674a6d0c9c6c312d
Author: marcosranes <marcosranes@gmail.com>
Date:   Sun Oct 31 17:40:10 2021 -0300

    complement to Git.md

commit 6df60adbb0c558cc6e36a46b972565d2d742bde5
Author: marcosranes <marcosranes@gmail.com>
Date:   Sun Oct 31 17:27:29 2021 -0300

    initial commit
```

## ` $ git log --format=fuller `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
commit 9bb35947b9770bfb6a0e4bbe2610a44fe159b18c
Author:     marcosranes <marcosranes@gmail.com>
AuthorDate: Sun Dec 12 08:16:32 2021 -0300
Commit:     marcosranes <marcosranes@gmail.com>
CommitDate: Sun Dec 12 08:16:32 2021 -0300

    added file

commit d985c354b1f1eaa2cb83ba6e37fb36424e4a5af8
Author:     Marcos Ranes <marcosranes@gmail.com>
AuthorDate: Tue Dec 7 22:18:15 2021 -0800
Commit:     GitHub <noreply@github.com>
CommitDate: Tue Dec 7 22:18:15 2021 -0800

    Update Git.md
    
    just proofreading the text

commit 852239f2c54493d944997ce2997da4064a9fc86a
Author:     marcosranes <marcosranes@gmail.com>
AuthorDate: Sun Nov 28 23:27:44 2021 -0300
Commit:     marcosranes <marcosranes@gmail.com>
CommitDate: Sun Nov 28 23:27:44 2021 -0300

    files updated

commit d6fc4d3f15ab671c87a070b10f717b586321dcf1
Author:     marcosranes <marcosranes@gmail.com>
AuthorDate: Mon Nov 1 14:03:40 2021 -0300
Commit:     marcosranes <marcosranes@gmail.com>
CommitDate: Mon Nov 1 14:03:40 2021 -0300

    added pytest tutorial

commit a190f614aef326f8d0be68b5f84828512e02d5c6
Author:     Marcos Ranes <marcosranes@gmail.com>
AuthorDate: Sun Oct 31 20:12:08 2021 -0300
Commit:     GitHub <noreply@github.com>
CommitDate: Sun Oct 31 20:12:08 2021 -0300

    Update Git.md
    
    Just proofreading the text...

commit 16ec053b9c348ab877d69346b76bb91a86fb658c
Author:     Marcos Ranes <marcosranes@gmail.com>
AuthorDate: Sun Oct 31 19:59:02 2021 -0300
Commit:     GitHub <noreply@github.com>
CommitDate: Sun Oct 31 19:59:02 2021 -0300

    Update README.md
    
    Just proofreading the text

commit e19923de386faee50e98beaccda4b3c54d885800
Author:     Marcos Ranes <marcosranes@gmail.com>
AuthorDate: Sun Oct 31 19:51:13 2021 -0300
Commit:     GitHub <noreply@github.com>
CommitDate: Sun Oct 31 19:51:13 2021 -0300

    Create README.md

commit 36f712d8302d00031bb06dcc990f770aa776b463
Author:     Marcos Ranes <marcosranes@gmail.com>
AuthorDate: Sun Oct 31 19:20:58 2021 -0300
Commit:     GitHub <noreply@github.com>
CommitDate: Sun Oct 31 19:20:58 2021 -0300

    Update Pipenv.md
    
    Just proofreading the text...

commit 1dd9116293ba5b8593f2093feb0756a1b5e0aa52
Author:     Marcos Ranes <marcosranes@gmail.com>
AuthorDate: Sun Oct 31 19:12:59 2021 -0300
Commit:     GitHub <noreply@github.com>
CommitDate: Sun Oct 31 19:12:59 2021 -0300

    Update Pipenv.md
    
    Just proofreading the text...

commit dd8f08311a976c293a216a092ef22f79b35abeb0
Author:     marcosranes <marcosranes@gmail.com>
AuthorDate: Sun Oct 31 19:00:05 2021 -0300
Commit:     marcosranes <marcosranes@gmail.com>
CommitDate: Sun Oct 31 19:00:05 2021 -0300

    file updated

commit c2f5a7dbb34903472fb2eeab243bf413c8013965
Author:     Marcos Ranes <marcosranes@gmail.com>
AuthorDate: Sun Oct 31 17:55:20 2021 -0300
Commit:     GitHub <noreply@github.com>
CommitDate: Sun Oct 31 17:55:20 2021 -0300

    Update Git.md
    
    Just proofreading the text...

commit e0be795ae14bfc5e84247bc9674a6d0c9c6c312d
Author:     marcosranes <marcosranes@gmail.com>
AuthorDate: Sun Oct 31 17:40:10 2021 -0300
Commit:     marcosranes <marcosranes@gmail.com>
CommitDate: Sun Oct 31 17:40:10 2021 -0300

    complement to Git.md

commit 6df60adbb0c558cc6e36a46b972565d2d742bde5
Author:     marcosranes <marcosranes@gmail.com>
AuthorDate: Sun Oct 31 17:27:29 2021 -0300
Commit:     marcosranes <marcosranes@gmail.com>
CommitDate: Sun Oct 31 17:27:29 2021 -0300

    initial commit
```
 
### Let's see how to change a commit date
 
We go ahead and create a test folder just as an example

### ` $ mkdir test_folder `

### ` $ cd test_folder/ `

### ` $ pwd `
```
/home/marcosranes/Desktop/Tutorials/test_folder
```

### ` $ git init `
```
Initialized existing Git repository in /home/marcosranes/Desktop/Tutorials/test_folder/.git/
```

### ` $ ls -a `
```
.
..
.git
```

### ` $ touch dummy_file.md `

### ` $ ls -a `
```
.
..
dummy_file.md
.git
```

### ` $ git status `
```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	dummy_file.md

nothing added to commit but untracked files present (use "git add" to track)
```

### ` $ git add dummy_file.md `

### ` $ git status `
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   dummy_file.md

```

### ` $ git commit -m "added file" `
```
[master (root-commit) da8fde1] added file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 dummy_file.md
```

### ` $ git log `
```
commit da8fde17f9aeac926016a125d8cf5f1e02c315a2
Author: marcosranes <marcosranes@gmail.com>
Date:   Tue Dec 14 21:21:26 2021 -0300

    added file
```

### ` $ git commit --amend --date="Wed Feb 16 14:00 2011 +0100" --no-edit `
```
[master 25a871a] added file
 Date: Wed Feb 16 14:00:00 2011 +0100
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 dummy_file.md
```

### ` $ git log `
```
commit 25a871a8acd97c66e913f9a779fb38b691f7bbf0
Author: marcosranes <marcosranes@gmail.com>
Date:   Wed Feb 16 14:00:00 2011 +0100

    added file
```
 
As we can see the date was changed..
 
### Other git log commnds

### ` $ git log -p -2 `
```
commit 25a871a8acd97c66e913f9a779fb38b691f7bbf0 (HEAD -> master)
Author: marcosranes <marcosranes@gmail.com>
Date:   Wed Feb 16 14:00:00 2011 +0100

    added file

diff --git a/dummy_file.md b/dummy_file.md
new file mode 100644
index 0000000..e69de29
```

### ` $ git log --stat `
```
commit 25a871a8acd97c66e913f9a779fb38b691f7bbf0 (HEAD -> master)
Author: marcosranes <marcosranes@gmail.com>
Date:   Wed Feb 16 14:00:00 2011 +0100

    added file

 dummy_file.md | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
```

### ` $ git log --pretty=oneline `
```
25a871a8acd97c66e913f9a779fb38b691f7bbf0 (HEAD -> master) added file
```

### ` $ git log --pretty=format:"%h - %an, %ar : %s" `
```
25a871a - marcosranes, 11 years ago : added file
```
