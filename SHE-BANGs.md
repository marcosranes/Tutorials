# ` $ date `
```
sex 22 out 2021 14:11:47 -03
```
# Today let's see about She-Bang (#!)
  
### Interpreter Settings Usability:
### ` $ #!/bin/bash `

### ` $ #!/bin/csh `

### ` $ #!/bin/zsh `

### ` $ #!/bin/perl `

### ` $ #!/usr/bin/python `

### ` $ #!/bin/ruby `

### ` $ #!/bin/awk `

### ` $ #!/bin/sed `
###
Buts, to ensure that your script will be compiled by most of the systems (Linux distro), prefer declaring the she-bang like this:

### ` $ #!/usr/bin/env <interpreter> `
###
### So, first you need to open an editor, no extension is needed, it doesn't matter to Linux, butsss it isn't a good practice. 
### ` $ nano myscript `
Ever starting with `#!` in the first line, then paste the relative path...
Use `which` command + `interpreter` to locate it.

### If you're under a virtual environment, you should see something like the following...
### ` $ which python `
```
/home/marcosranes/Desktop/Tutorials/.venv/bin/python
```

### ` $ echo $VIRTUAL_ENV `
```
/home/marcosranes/Desktop/Tutorials/.venv
```
So, we can make it shortened

### ` $ echo $VIRTUAL_ENV/bin/python `
```
/home/marcosranes/Desktop/Tutorials/.venv/bin/python
```
### To show all of your environment variables, just type `env` or `printenv`
I'm not going to show that here, there's a too much populated list of that living in my system, but you should try.
 
However, I use to set it up by searching for something more specific.

### ` $ env | grep PIP `
```shell
PIPENV_VENV_IN_PROJECT=1
PIPENV_ACTIVE=1
PIP_PYTHON_PATH=/home/marcosranes/.pyenv/versions/3.9.7/bin/python3.9
PIP_DISABLE_PIP_VERSION_CHECK=1
```
### ` $ env | grep VIRTUAL && env | grep PIP `
```shell
VIRTUAL_ENV=/home/marcosranes/Desktop/Tutorials/.venv
PIPENV_VENV_IN_PROJECT=1
PIPENV_ACTIVE=1
PIP_PYTHON_PATH=/home/marcosranes/.pyenv/versions/3.9.7/bin/python3.9
PIP_DISABLE_PIP_VERSION_CHECK=1
```
### ` $ env | less `
Also, using `pipe less` for a viewing in chunks. Once opened, use `arrow-up/arrow-down` for scrolling and typing `q` to quit.

## Bash
**Showing the path:**
### ` $ type -P bash `
```
/usr/bin/bash
```
### ` $ which bash `
```
/usr/bin/bash
```

### ` $ ls -la /usr/bin/bash `
```
-rwxr-xr-x 1 root root 1404744 mar 19  2021 /usr/bin/bash
```

### ` $ ls -la /bin/bash `
```
-rwxr-xr-x 1 root root 1404744 mar 19  2021 /bin/bash
```
###
Creating a script for Python language... 
### ` $ nano myscript.py `

### ` $ cat myscript.py `
```
#!/usr/bin/python

print("Hello, Python!")
```
###
Also, we can make that in another way, and it's the correct manner, as we've earlier seen.

### ` $ cat myscript.py `
```
#!/usr/bin/env python

print("Hello, Python!")
```

### ` $ python myscript.py `
```
Hello, Python!
```
###
*__So, let's give it an executable...__*

` $ ls -l myscript.py `
```
-rw-rw-r-- 1 marcosranes marcosranes 47 out 22 22:03 myscript.py
```
###
Here is the command that tuns any script into an executable program.

` $ chmod +x myscript.py `
###
Let's see the changes we've just done...

` $ ls -l myscript.py `
```
-rwxrwxr-x 1 marcosranes marcosranes 47 out 22 22:03 myscript.py
```
###
Now executing...

### ` $ ./myscript.py `
```
Hello, Python!
```
###
Now, let's proceed to create a script for Bash...
### ` $ nano myscript.sh `

### ` $ cat myscript.sh `
```
#!/usr/bin/env bash

clear
echo "That's all cleared!"
```
###
Ways of pre executing, yet without recording, for pilot tests.

` $ source script.sh `

```
That's all cleared!
```

` $ bash ./script.sh `
```
That's all cleared!
```
###
**Also, you can override its internal interpreter**

### ` $ zsh ./myscript.sh `
```
That's all cleared!
```
## Executing Permission
*__Before giving permission...__*

` $ ./myscript.sh `
```
bash: ./myscript.sh: Permission denied
```

` $ ls -l myscript.sh `
```
-rw-rw-r-- 1 marcosranes marcosranes 54 out 22 22:21 myscript.sh
```
###
*__Giving permission --making an executable file...__*

` $ chmod +775 myscript.sh `  or ` $ chmod +x myscript.sh `

` $ ls -l myscript.sh `
```
-rwxrwxr-x 1 marcosranes marcosranes 54 out 22 22:21 myscript.sh
```
###
*__Running...__*

### ` $ ./myscript.sh `
```
That's all cleared!
```
Note: 
By the time you make it an executable program, it's saved to your root directory... So, that `./` indicates you want to call anything living within this folder.

Now your script is wrapped up for distribution. Take additional care of running and coding malicious command lines.
