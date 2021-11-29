## ` $ date `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
seg 01 nov 2021 12:09:06 -03
```
  
# Getting started with the Pytest library
 
Proceeding to install Pytest as a dev dependency

### ` $ cat Pipfile `
```
[[source]]
url = "https://pypi.org/simple"
verify_ssl = true
name = "pypi"

[packages]

[dev-packages]

[requires]
python_version = "3.9"
```

### ` $ pipenv install -d pytest `
```
-Succeeded!
pipenv install -d pytest
✔ Installation Succeeded 
Pipfile.lock (16c839) out of date, updating to (249526)...
Locking [dev-packages] dependencies...
Building requirements...
✔ Success! 
Locking [packages] dependencies...
Updated Pipfile.lock (249526)!
  🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 0/0 — 00:00:00
```

### ` $ cat Pipfile `
```
[[source]]
url = "https://pypi.org/simple"
verify_ssl = true
name = "pypi"

[packages]

[dev-packages]
pytest = "*"

[requires]
python_version = "3.9"
```
 
As you can see in Pipfile dev-packages section, Pytest was successfully installed.

### ` $ pipenv graph `
```
pytest==6.2.5
  - attrs [required: >=19.2.0, installed: 21.2.0]
  - iniconfig [required: Any, installed: 1.1.1]
  - packaging [required: Any, installed: 21.2]
    - pyparsing [required: >=2.0.2,<3, installed: 2.4.7]
  - pluggy [required: >=0.12,<2.0, installed: 1.0.0]
  - py [required: >=1.8.2, installed: 1.10.0]
  - toml [required: Any, installed: 0.10.2]
```
### Virtual environments (i.e. .venv, env, and family) don't climb repositories. So, let's simulate we're about getting a project in which we want to run it.
### ` rm -rf .venv/ `
Removing the virtual environment

### ` pipenv sync -d `
This command will create the .venv folder and install the dev dependencies within it, also no matter you are into the environment.
```shell
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ pipenv sync -d
Creating a virtualenv for this project...
Pipfile: /home/marcosranes/Desktop/Tutorials/Pipfile
Using /home/marcosranes/.pyenv/versions/3.9.7/bin/python3.9 (3.9.7) to create virtualenv...
⠴ Creating virtual environment...created virtual environment CPython3.9.7.final.0-64 in 307ms
  creator CPython3Posix(dest=/home/marcosranes/Desktop/Tutorials/.venv, clear=False, no_vcs_ignore=False, global=False)
  seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=/home/marcosranes/.local/share/virtualenv)
    added seed packages: pip==21.3.1, setuptools==58.3.0, wheel==0.37.0
  activators BashActivator,CShellActivator,FishActivator,NushellActivator,PowerShellActivator,PythonActivator
✔ Successfully created virtual environment! 
Virtualenv location: /home/marcosranes/Desktop/Tutorials/.venv
Installing dependencies from Pipfile.lock (249526)...
  🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 8/8 — 00:00:15
To activate this project's virtualenv, run pipenv shell.
Alternatively, run a command inside the virtualenv with pipenv run.
All dependencies are now up-to-date!
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ 
```
This command will create the .venv folder and install the dev dependencies within it, also no matter you are into the environment.
### ` ls -la | grep .ve `
```shell
drwxrwxr-x  5 marcosranes marcosranes  4096 nov  1 12:46 .venv
```
As you can see, it was created.
### ` pipenv shell `
```shell
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ pipenv shell
Launching subshell in virtual environment...
 . /home/marcosranes/Desktop/Tutorials/.venv/bin/activate
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$  . /home/marcosranes/Desktop/Tutorials/.venv/bin/activate
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ 
```
### Running Pytest for inconsistencies in our code:
## ` $ pytest `
```shell
============================= test session starts ==============================
platform linux -- Python 3.9.7, pytest-6.2.5, py-1.10.0, pluggy-1.0.0
rootdir: /home/marcosranes/Desktop/Tutorials
collected 0 items

============================ no tests ran in 0.01s =============================
```
Into the virtual environment

## ` pipenv run pytest . `
```shell
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ exit
exit
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ pipenv run pytest .
============================= test session starts ==============================
platform linux -- Python 3.9.7, pytest-6.2.5, py-1.10.0, pluggy-1.0.0
rootdir: /home/marcosranes/Desktop/Tutorials
collected 0 items                                                                                                                                                    

============================ no tests ran in 0.01s =============================
```
Out of the virtual environment