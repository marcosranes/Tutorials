
### ` $ date `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
sáb 30 out 2021 13:10:16 -03
```
# Getting started with PIPENV
Let's get a look at the following command lines:
### ` $ pip install pipenv `
```shell
Collecting pipenv
  Using cached pipenv-2021.5.29-py2.py3-none-any.whl (3.9 MB)
Collecting certifi
  Using cached certifi-2021.10.8-py2.py3-none-any.whl (149 kB)
Collecting virtualenv-clone>=0.2.5
  Using cached virtualenv_clone-0.5.7-py3-none-any.whl (6.6 kB)
Requirement already satisfied: setuptools>=36.2.1 in /home/marcosranes/.pyenv/versions/3.9.7/lib/python3.9/site-packages (from pipenv) (57.4.0)
Requirement already satisfied: pip>=18.0 in /home/marcosranes/.pyenv/versions/3.9.7/lib/python3.9/site-packages (from pipenv) (21.2.3)
Collecting virtualenv
  Using cached virtualenv-20.9.0-py2.py3-none-any.whl (5.6 MB)
Collecting six<2,>=1.9.0
  Using cached six-1.16.0-py2.py3-none-any.whl (11 kB)
Collecting distlib<1,>=0.3.1
  Using cached distlib-0.3.3-py2.py3-none-any.whl (496 kB)
Collecting platformdirs<3,>=2
  Using cached platformdirs-2.4.0-py3-none-any.whl (14 kB)
Collecting filelock<4,>=3.2
  Using cached filelock-3.3.2-py3-none-any.whl (9.7 kB)
Collecting backports.entry-points-selectable>=1.0.4
  Using cached backports.entry_points_selectable-1.1.0-py2.py3-none-any.whl (6.2 kB)
Installing collected packages: six, platformdirs, filelock, distlib, backports.entry-points-selectable, virtualenv-clone, virtualenv, certifi, pipenv
Successfully installed backports.entry-points-selectable-1.1.0 certifi-2021.10.8 distlib-0.3.3 filelock-3.3.2 pipenv-2021.5.29 platformdirs-2.4.0 six-1.16.0 virtualenv-20.9.0 virtualenv-clone-0.5.7
WARNING: You are using pip version 21.2.3; however, version 21.3.1 is available.
You should consider upgrading via the '/home/marcosranes/.pyenv/versions/3.9.7/bin/python3.9 -m pip install --upgrade pip' command.
```
```shell
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ pyenv which pipenv
/home/marcosranes/.pyenv/versions/3.9.7/bin/pipenv
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ which pipenv
/home/marcosranes/.pyenv/shims/pipenv
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ pipenv --version
pipenv, version 2021.5.29
```
```shell
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ pip freeze
backports.entry-points-selectable==1.1.0
certifi==2021.10.8
distlib==0.3.3
filelock==3.3.2
pipenv==2021.5.29
platformdirs==2.4.0
six==1.16.0
virtualenv==20.9.0
virtualenv-clone==0.5.7
```
```shell
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ pipenv graph
Warning: No virtualenv has been created for this project yet! Consider running `pipenv install` first to automatically generate one for you or see `pipenv install --help` for further instructions.
```

### ` $ pipenv --help `
```
Usage: pipenv [OPTIONS] COMMAND [ARGS]...

Options:
  --where                         Output project home information.
  --venv                          Output virtualenv information.
  --py                            Output Python interpreter information.
  --envs                          Output Environment Variable options.
  --rm                            Remove the virtualenv.
  --bare                          Minimal output.
  --completion                    Output completion (to be executed by the
                                  shell).

  --man                           Display manpage.
  --support                       Output diagnostic information for use in
                                  GitHub issues.

  --site-packages / --no-site-packages
                                  Enable site-packages for the virtualenv.
                                  [env var: PIPENV_SITE_PACKAGES]

  --python TEXT                   Specify which version of Python virtualenv
                                  should use.

  --three / --two                 Use Python 3/2 when creating virtualenv.
  --clear                         Clears caches (pipenv, pip, and pip-tools).
                                  [env var: PIPENV_CLEAR]

  -v, --verbose                   Verbose mode.
  --pypi-mirror TEXT              Specify a PyPI mirror.
  --version                       Show the version and exit.
  -h, --help                      Show this message and exit.


Usage Examples:
   Create a new project using Python 3.7, specifically:
   $ pipenv --python 3.7

   Remove project virtualenv (inferred from current directory):
   $ pipenv --rm

   Install all dependencies for a project (including dev):
   $ pipenv install --dev

   Create a lockfile containing pre-releases:
   $ pipenv lock --pre

   Show a graph of your installed dependencies:
   $ pipenv graph

   Check your installed dependencies for security vulnerabilities:
   $ pipenv check

   Install a local setup.py into your virtual environment/Pipfile:
   $ pipenv install -e .

   Use a lower-level pip command:
   $ pipenv run pip freeze

Commands:
  check      Checks for PyUp Safety security vulnerabilities and against PEP
             508 markers provided in Pipfile.

  clean      Uninstalls all packages not specified in Pipfile.lock.
  graph      Displays currently-installed dependency graph information.
  install    Installs provided packages and adds them to Pipfile, or (if no
             packages are given), installs all packages from Pipfile.

  lock       Generates Pipfile.lock.
  open       View a given module in your editor.
  run        Spawns a command installed into the virtualenv.
  scripts    Lists scripts in current environment config.
  shell      Spawns a shell within the virtualenv.
  sync       Installs all packages specified in Pipfile.lock.
  uninstall  Uninstalls a provided package and removes it from Pipfile.
  update     Runs lock, then sync.
```
### ` $ pipenv install `
```shell
Creating a virtualenv for this project...
Pipfile: /home/marcosranes/Desktop/Tutorials/Pipfile
Using /home/marcosranes/.pyenv/versions/3.9.7/bin/python3.9 (3.9.7) to create virtualenv...
⠹ Creating virtual environment...created virtual environment CPython3.9.7.final.0-64 in 100ms
  creator CPython3Posix(dest=/home/marcosranes/Desktop/Tutorials/.venv, clear=False, no_vcs_ignore=False, global=False)
  seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=/home/marcosranes/.local/share/virtualenv)
    added seed packages: pip==21.2.4, setuptools==58.2.0, wheel==0.37.0
  activators BashActivator,CShellActivator,FishActivator,NushellActivator,PowerShellActivator,PythonActivator
✔ Successfully created virtual environment! 
Virtualenv location: /home/marcosranes/Desktop/Tutorials/.venv
Creating a Pipfile for this project...
Pipfile.lock not found, creating...
Locking [dev-packages] dependencies...
Locking [packages] dependencies...
Updated Pipfile.lock (16c839)!
Installing dependencies from Pipfile.lock (16c839)...
  🎃   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 0/0 — 00:00:00
To activate this project's virtualenv, run pipenv shell.
Alternatively, run a command inside the virtualenv with pipenv run.
```
### ` echo "export PIPENV_VENV_IN_PROJECT=1" >> ~/.bashrc`

So, `pipenv install` comes up with three features for your project. They are: `.venv` folder, `Pipfile` text file, and `Pipfile.lock`  
### ` $ ls -a `
```
.
..
draft-README.md
.git
.idea
Pipfile
Pipfile.lock
.venv
``` 
Let's take a view at these features

### ` $ cat Pipfile `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
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

### ` $ cat Pipfile.lock `
```
{
    "_meta": {
        "hash": {
            "sha256": "a36a5392bb1e8bbc06bfaa0761e52593cf2d83b486696bf54667ba8da616c839"
        },
        "pipfile-spec": 6,
        "requires": {
            "python_version": "3.9"
        },
        "sources": [
            {
                "name": "pypi",
                "url": "https://pypi.org/simple",
                "verify_ssl": true
            }
        ]
    },
    "default": {},
    "develop": {}
}
```

### ` $ tree .venv `
<span style='color:#fff; font-family: Dejavu Sans Mono; font-size: 1.1em;'>- Path: /home/marcosranes/Desktop/Tutorials</span>
```
.venv
├── bin
│   ├── activate
│   ├── activate.csh
│   ├── activate.fish
│   ├── activate.nu
│   ├── activate.ps1
│   ├── activate_this.py
│   ├── deactivate.nu
│   ├── pip
│   ├── pip3
│   ├── pip-3.9
│   ├── pip3.9
│   ├── python -> /home/marcosranes/.pyenv/versions/3.9.7/bin/python3.9
│   ├── python3 -> python
│   ├── python3.9 -> python
│   ├── wheel
│   ├── wheel3
│   ├── wheel-3.9
│   └── wheel3.9
├── lib
│   └── python3.9
│       └── site-packages
│           ├── _distutils_hack
│           │   ├── __init__.py
│           │   └── override.py
│           ├── distutils-precedence.pth
│           ├── pip
│           │   ├── __init__.py
│           │   ├── _internal
│           │   │   ├── build_env.py
│           │   │   ├── cache.py
│           │   │   ├── cli
│           │   │   │   ├── autocompletion.py
│           │   │   │   ├── base_command.py
│           │   │   │   ├── cmdoptions.py
│           │   │   │   ├── command_context.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── main_parser.py
│           │   │   │   ├── main.py
│           │   │   │   ├── parser.py
│           │   │   │   ├── progress_bars.py
│           │   │   │   ├── req_command.py
│           │   │   │   ├── spinners.py
│           │   │   │   └── status_codes.py
│           │   │   ├── commands
│           │   │   │   ├── cache.py
│           │   │   │   ├── check.py
│           │   │   │   ├── completion.py
│           │   │   │   ├── configuration.py
│           │   │   │   ├── debug.py
│           │   │   │   ├── download.py
│           │   │   │   ├── freeze.py
│           │   │   │   ├── hash.py
│           │   │   │   ├── help.py
│           │   │   │   ├── index.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── install.py
│           │   │   │   ├── list.py
│           │   │   │   ├── search.py
│           │   │   │   ├── show.py
│           │   │   │   ├── uninstall.py
│           │   │   │   └── wheel.py
│           │   │   ├── configuration.py
│           │   │   ├── distributions
│           │   │   │   ├── base.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── installed.py
│           │   │   │   ├── sdist.py
│           │   │   │   └── wheel.py
│           │   │   ├── exceptions.py
│           │   │   ├── index
│           │   │   │   ├── collector.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── package_finder.py
│           │   │   │   └── sources.py
│           │   │   ├── __init__.py
│           │   │   ├── locations
│           │   │   │   ├── base.py
│           │   │   │   ├── _distutils.py
│           │   │   │   ├── __init__.py
│           │   │   │   └── _sysconfig.py
│           │   │   ├── main.py
│           │   │   ├── metadata
│           │   │   │   ├── base.py
│           │   │   │   ├── __init__.py
│           │   │   │   └── pkg_resources.py
│           │   │   ├── models
│           │   │   │   ├── candidate.py
│           │   │   │   ├── direct_url.py
│           │   │   │   ├── format_control.py
│           │   │   │   ├── index.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── link.py
│           │   │   │   ├── scheme.py
│           │   │   │   ├── search_scope.py
│           │   │   │   ├── selection_prefs.py
│           │   │   │   ├── target_python.py
│           │   │   │   └── wheel.py
│           │   │   ├── network
│           │   │   │   ├── auth.py
│           │   │   │   ├── cache.py
│           │   │   │   ├── download.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── lazy_wheel.py
│           │   │   │   ├── session.py
│           │   │   │   ├── utils.py
│           │   │   │   └── xmlrpc.py
│           │   │   ├── operations
│           │   │   │   ├── build
│           │   │   │   │   ├── __init__.py
│           │   │   │   │   ├── metadata_legacy.py
│           │   │   │   │   ├── metadata.py
│           │   │   │   │   ├── wheel_legacy.py
│           │   │   │   │   └── wheel.py
│           │   │   │   ├── check.py
│           │   │   │   ├── freeze.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── install
│           │   │   │   │   ├── editable_legacy.py
│           │   │   │   │   ├── __init__.py
│           │   │   │   │   ├── legacy.py
│           │   │   │   │   └── wheel.py
│           │   │   │   └── prepare.py
│           │   │   ├── pyproject.py
│           │   │   ├── req
│           │   │   │   ├── constructors.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── req_file.py
│           │   │   │   ├── req_install.py
│           │   │   │   ├── req_set.py
│           │   │   │   ├── req_tracker.py
│           │   │   │   └── req_uninstall.py
│           │   │   ├── resolution
│           │   │   │   ├── base.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── legacy
│           │   │   │   │   ├── __init__.py
│           │   │   │   │   └── resolver.py
│           │   │   │   └── resolvelib
│           │   │   │       ├── base.py
│           │   │   │       ├── candidates.py
│           │   │   │       ├── factory.py
│           │   │   │       ├── found_candidates.py
│           │   │   │       ├── __init__.py
│           │   │   │       ├── provider.py
│           │   │   │       ├── reporter.py
│           │   │   │       ├── requirements.py
│           │   │   │       └── resolver.py
│           │   │   ├── self_outdated_check.py
│           │   │   ├── utils
│           │   │   │   ├── appdirs.py
│           │   │   │   ├── compatibility_tags.py
│           │   │   │   ├── compat.py
│           │   │   │   ├── datetime.py
│           │   │   │   ├── deprecation.py
│           │   │   │   ├── direct_url_helpers.py
│           │   │   │   ├── distutils_args.py
│           │   │   │   ├── encoding.py
│           │   │   │   ├── entrypoints.py
│           │   │   │   ├── filesystem.py
│           │   │   │   ├── filetypes.py
│           │   │   │   ├── glibc.py
│           │   │   │   ├── hashes.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── inject_securetransport.py
│           │   │   │   ├── logging.py
│           │   │   │   ├── _log.py
│           │   │   │   ├── misc.py
│           │   │   │   ├── models.py
│           │   │   │   ├── packaging.py
│           │   │   │   ├── parallel.py
│           │   │   │   ├── pkg_resources.py
│           │   │   │   ├── setuptools_build.py
│           │   │   │   ├── subprocess.py
│           │   │   │   ├── temp_dir.py
│           │   │   │   ├── unpacking.py
│           │   │   │   ├── urls.py
│           │   │   │   ├── virtualenv.py
│           │   │   │   └── wheel.py
│           │   │   ├── vcs
│           │   │   │   ├── bazaar.py
│           │   │   │   ├── git.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── mercurial.py
│           │   │   │   ├── subversion.py
│           │   │   │   └── versioncontrol.py
│           │   │   └── wheel_builder.py
│           │   ├── __main__.py
│           │   ├── py.typed
│           │   └── _vendor
│           │       ├── appdirs.py
│           │       ├── cachecontrol
│           │       │   ├── adapter.py
│           │       │   ├── cache.py
│           │       │   ├── caches
│           │       │   │   ├── file_cache.py
│           │       │   │   ├── __init__.py
│           │       │   │   └── redis_cache.py
│           │       │   ├── _cmd.py
│           │       │   ├── compat.py
│           │       │   ├── controller.py
│           │       │   ├── filewrapper.py
│           │       │   ├── heuristics.py
│           │       │   ├── __init__.py
│           │       │   ├── serialize.py
│           │       │   └── wrapper.py
│           │       ├── certifi
│           │       │   ├── cacert.pem
│           │       │   ├── core.py
│           │       │   ├── __init__.py
│           │       │   └── __main__.py
│           │       ├── chardet
│           │       │   ├── big5freq.py
│           │       │   ├── big5prober.py
│           │       │   ├── chardistribution.py
│           │       │   ├── charsetgroupprober.py
│           │       │   ├── charsetprober.py
│           │       │   ├── cli
│           │       │   │   ├── chardetect.py
│           │       │   │   └── __init__.py
│           │       │   ├── codingstatemachine.py
│           │       │   ├── compat.py
│           │       │   ├── cp949prober.py
│           │       │   ├── enums.py
│           │       │   ├── escprober.py
│           │       │   ├── escsm.py
│           │       │   ├── eucjpprober.py
│           │       │   ├── euckrfreq.py
│           │       │   ├── euckrprober.py
│           │       │   ├── euctwfreq.py
│           │       │   ├── euctwprober.py
│           │       │   ├── gb2312freq.py
│           │       │   ├── gb2312prober.py
│           │       │   ├── hebrewprober.py
│           │       │   ├── __init__.py
│           │       │   ├── jisfreq.py
│           │       │   ├── jpcntx.py
│           │       │   ├── langbulgarianmodel.py
│           │       │   ├── langgreekmodel.py
│           │       │   ├── langhebrewmodel.py
│           │       │   ├── langhungarianmodel.py
│           │       │   ├── langrussianmodel.py
│           │       │   ├── langthaimodel.py
│           │       │   ├── langturkishmodel.py
│           │       │   ├── latin1prober.py
│           │       │   ├── mbcharsetprober.py
│           │       │   ├── mbcsgroupprober.py
│           │       │   ├── mbcssm.py
│           │       │   ├── metadata
│           │       │   │   ├── __init__.py
│           │       │   │   └── languages.py
│           │       │   ├── sbcharsetprober.py
│           │       │   ├── sbcsgroupprober.py
│           │       │   ├── sjisprober.py
│           │       │   ├── universaldetector.py
│           │       │   ├── utf8prober.py
│           │       │   └── version.py
│           │       ├── colorama
│           │       │   ├── ansi.py
│           │       │   ├── ansitowin32.py
│           │       │   ├── initialise.py
│           │       │   ├── __init__.py
│           │       │   ├── win32.py
│           │       │   └── winterm.py
│           │       ├── distlib
│           │       │   ├── _backport
│           │       │   │   ├── __init__.py
│           │       │   │   ├── misc.py
│           │       │   │   ├── shutil.py
│           │       │   │   ├── sysconfig.cfg
│           │       │   │   ├── sysconfig.py
│           │       │   │   └── tarfile.py
│           │       │   ├── compat.py
│           │       │   ├── database.py
│           │       │   ├── index.py
│           │       │   ├── __init__.py
│           │       │   ├── locators.py
│           │       │   ├── manifest.py
│           │       │   ├── markers.py
│           │       │   ├── metadata.py
│           │       │   ├── resources.py
│           │       │   ├── scripts.py
│           │       │   ├── t32.exe
│           │       │   ├── t64.exe
│           │       │   ├── util.py
│           │       │   ├── version.py
│           │       │   ├── w32.exe
│           │       │   ├── w64.exe
│           │       │   └── wheel.py
│           │       ├── distro.py
│           │       ├── html5lib
│           │       │   ├── constants.py
│           │       │   ├── filters
│           │       │   │   ├── alphabeticalattributes.py
│           │       │   │   ├── base.py
│           │       │   │   ├── __init__.py
│           │       │   │   ├── inject_meta_charset.py
│           │       │   │   ├── lint.py
│           │       │   │   ├── optionaltags.py
│           │       │   │   ├── sanitizer.py
│           │       │   │   └── whitespace.py
│           │       │   ├── html5parser.py
│           │       │   ├── _ihatexml.py
│           │       │   ├── __init__.py
│           │       │   ├── _inputstream.py
│           │       │   ├── serializer.py
│           │       │   ├── _tokenizer.py
│           │       │   ├── treeadapters
│           │       │   │   ├── genshi.py
│           │       │   │   ├── __init__.py
│           │       │   │   └── sax.py
│           │       │   ├── treebuilders
│           │       │   │   ├── base.py
│           │       │   │   ├── dom.py
│           │       │   │   ├── etree_lxml.py
│           │       │   │   ├── etree.py
│           │       │   │   └── __init__.py
│           │       │   ├── treewalkers
│           │       │   │   ├── base.py
│           │       │   │   ├── dom.py
│           │       │   │   ├── etree_lxml.py
│           │       │   │   ├── etree.py
│           │       │   │   ├── genshi.py
│           │       │   │   └── __init__.py
│           │       │   ├── _trie
│           │       │   │   ├── _base.py
│           │       │   │   ├── __init__.py
│           │       │   │   └── py.py
│           │       │   └── _utils.py
│           │       ├── idna
│           │       │   ├── codec.py
│           │       │   ├── compat.py
│           │       │   ├── core.py
│           │       │   ├── idnadata.py
│           │       │   ├── __init__.py
│           │       │   ├── intranges.py
│           │       │   ├── package_data.py
│           │       │   └── uts46data.py
│           │       ├── __init__.py
│           │       ├── msgpack
│           │       │   ├── exceptions.py
│           │       │   ├── ext.py
│           │       │   ├── fallback.py
│           │       │   ├── __init__.py
│           │       │   └── _version.py
│           │       ├── packaging
│           │       │   ├── __about__.py
│           │       │   ├── __init__.py
│           │       │   ├── _manylinux.py
│           │       │   ├── markers.py
│           │       │   ├── _musllinux.py
│           │       │   ├── requirements.py
│           │       │   ├── specifiers.py
│           │       │   ├── _structures.py
│           │       │   ├── tags.py
│           │       │   ├── utils.py
│           │       │   └── version.py
│           │       ├── pep517
│           │       │   ├── build.py
│           │       │   ├── check.py
│           │       │   ├── colorlog.py
│           │       │   ├── compat.py
│           │       │   ├── dirtools.py
│           │       │   ├── envbuild.py
│           │       │   ├── __init__.py
│           │       │   ├── in_process
│           │       │   │   ├── __init__.py
│           │       │   │   └── _in_process.py
│           │       │   ├── meta.py
│           │       │   └── wrappers.py
│           │       ├── pkg_resources
│           │       │   ├── __init__.py
│           │       │   └── py31compat.py
│           │       ├── progress
│           │       │   ├── bar.py
│           │       │   ├── counter.py
│           │       │   ├── __init__.py
│           │       │   └── spinner.py
│           │       ├── pyparsing.py
│           │       ├── requests
│           │       │   ├── adapters.py
│           │       │   ├── api.py
│           │       │   ├── auth.py
│           │       │   ├── certs.py
│           │       │   ├── compat.py
│           │       │   ├── cookies.py
│           │       │   ├── exceptions.py
│           │       │   ├── help.py
│           │       │   ├── hooks.py
│           │       │   ├── __init__.py
│           │       │   ├── _internal_utils.py
│           │       │   ├── models.py
│           │       │   ├── packages.py
│           │       │   ├── sessions.py
│           │       │   ├── status_codes.py
│           │       │   ├── structures.py
│           │       │   ├── utils.py
│           │       │   └── __version__.py
│           │       ├── resolvelib
│           │       │   ├── compat
│           │       │   │   ├── collections_abc.py
│           │       │   │   └── __init__.py
│           │       │   ├── __init__.py
│           │       │   ├── providers.py
│           │       │   ├── reporters.py
│           │       │   ├── resolvers.py
│           │       │   └── structs.py
│           │       ├── six.py
│           │       ├── tenacity
│           │       │   ├── after.py
│           │       │   ├── _asyncio.py
│           │       │   ├── before.py
│           │       │   ├── before_sleep.py
│           │       │   ├── __init__.py
│           │       │   ├── nap.py
│           │       │   ├── retry.py
│           │       │   ├── stop.py
│           │       │   ├── tornadoweb.py
│           │       │   ├── _utils.py
│           │       │   └── wait.py
│           │       ├── tomli
│           │       │   ├── __init__.py
│           │       │   ├── _parser.py
│           │       │   └── _re.py
│           │       ├── urllib3
│           │       │   ├── _collections.py
│           │       │   ├── connectionpool.py
│           │       │   ├── connection.py
│           │       │   ├── contrib
│           │       │   │   ├── _appengine_environ.py
│           │       │   │   ├── appengine.py
│           │       │   │   ├── __init__.py
│           │       │   │   ├── ntlmpool.py
│           │       │   │   ├── pyopenssl.py
│           │       │   │   ├── _securetransport
│           │       │   │   │   ├── bindings.py
│           │       │   │   │   ├── __init__.py
│           │       │   │   │   └── low_level.py
│           │       │   │   ├── securetransport.py
│           │       │   │   └── socks.py
│           │       │   ├── exceptions.py
│           │       │   ├── fields.py
│           │       │   ├── filepost.py
│           │       │   ├── __init__.py
│           │       │   ├── packages
│           │       │   │   ├── backports
│           │       │   │   │   ├── __init__.py
│           │       │   │   │   └── makefile.py
│           │       │   │   ├── __init__.py
│           │       │   │   ├── six.py
│           │       │   │   └── ssl_match_hostname
│           │       │   │       ├── _implementation.py
│           │       │   │       └── __init__.py
│           │       │   ├── poolmanager.py
│           │       │   ├── request.py
│           │       │   ├── response.py
│           │       │   ├── util
│           │       │   │   ├── connection.py
│           │       │   │   ├── __init__.py
│           │       │   │   ├── proxy.py
│           │       │   │   ├── queue.py
│           │       │   │   ├── request.py
│           │       │   │   ├── response.py
│           │       │   │   ├── retry.py
│           │       │   │   ├── ssl_.py
│           │       │   │   ├── ssltransport.py
│           │       │   │   ├── timeout.py
│           │       │   │   ├── url.py
│           │       │   │   └── wait.py
│           │       │   └── _version.py
│           │       ├── vendor.txt
│           │       └── webencodings
│           │           ├── __init__.py
│           │           ├── labels.py
│           │           ├── mklabels.py
│           │           ├── tests.py
│           │           └── x_user_defined.py
│           ├── pip-21.2.4.dist-info
│           │   ├── entry_points.txt
│           │   ├── INSTALLER
│           │   ├── LICENSE.txt
│           │   ├── METADATA
│           │   ├── RECORD
│           │   ├── top_level.txt
│           │   └── WHEEL
│           ├── pip-21.2.4.virtualenv
│           ├── pkg_resources
│           │   ├── extern
│           │   │   └── __init__.py
│           │   ├── __init__.py
│           │   ├── tests
│           │   │   └── data
│           │   │       └── my-test-package-source
│           │   │           └── setup.py
│           │   └── _vendor
│           │       ├── appdirs.py
│           │       ├── __init__.py
│           │       ├── packaging
│           │       │   ├── __about__.py
│           │       │   ├── _compat.py
│           │       │   ├── __init__.py
│           │       │   ├── markers.py
│           │       │   ├── requirements.py
│           │       │   ├── specifiers.py
│           │       │   ├── _structures.py
│           │       │   ├── tags.py
│           │       │   ├── _typing.py
│           │       │   ├── utils.py
│           │       │   └── version.py
│           │       └── pyparsing.py
│           ├── setuptools
│           │   ├── archive_util.py
│           │   ├── build_meta.py
│           │   ├── cli-32.exe
│           │   ├── cli-64.exe
│           │   ├── cli-arm64.exe
│           │   ├── cli.exe
│           │   ├── command
│           │   │   ├── alias.py
│           │   │   ├── bdist_egg.py
│           │   │   ├── bdist_rpm.py
│           │   │   ├── build_clib.py
│           │   │   ├── build_ext.py
│           │   │   ├── build_py.py
│           │   │   ├── develop.py
│           │   │   ├── dist_info.py
│           │   │   ├── easy_install.py
│           │   │   ├── egg_info.py
│           │   │   ├── __init__.py
│           │   │   ├── install_egg_info.py
│           │   │   ├── install_lib.py
│           │   │   ├── install.py
│           │   │   ├── install_scripts.py
│           │   │   ├── launcher manifest.xml
│           │   │   ├── py36compat.py
│           │   │   ├── register.py
│           │   │   ├── rotate.py
│           │   │   ├── saveopts.py
│           │   │   ├── sdist.py
│           │   │   ├── setopt.py
│           │   │   ├── test.py
│           │   │   ├── upload_docs.py
│           │   │   └── upload.py
│           │   ├── config.py
│           │   ├── depends.py
│           │   ├── _deprecation_warning.py
│           │   ├── dep_util.py
│           │   ├── dist.py
│           │   ├── _distutils
│           │   │   ├── archive_util.py
│           │   │   ├── bcppcompiler.py
│           │   │   ├── ccompiler.py
│           │   │   ├── cmd.py
│           │   │   ├── command
│           │   │   │   ├── bdist_dumb.py
│           │   │   │   ├── bdist_msi.py
│           │   │   │   ├── bdist.py
│           │   │   │   ├── bdist_rpm.py
│           │   │   │   ├── bdist_wininst.py
│           │   │   │   ├── build_clib.py
│           │   │   │   ├── build_ext.py
│           │   │   │   ├── build.py
│           │   │   │   ├── build_py.py
│           │   │   │   ├── build_scripts.py
│           │   │   │   ├── check.py
│           │   │   │   ├── clean.py
│           │   │   │   ├── config.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── install_data.py
│           │   │   │   ├── install_egg_info.py
│           │   │   │   ├── install_headers.py
│           │   │   │   ├── install_lib.py
│           │   │   │   ├── install.py
│           │   │   │   ├── install_scripts.py
│           │   │   │   ├── py37compat.py
│           │   │   │   ├── register.py
│           │   │   │   ├── sdist.py
│           │   │   │   └── upload.py
│           │   │   ├── config.py
│           │   │   ├── core.py
│           │   │   ├── cygwinccompiler.py
│           │   │   ├── debug.py
│           │   │   ├── dep_util.py
│           │   │   ├── dir_util.py
│           │   │   ├── dist.py
│           │   │   ├── errors.py
│           │   │   ├── extension.py
│           │   │   ├── fancy_getopt.py
│           │   │   ├── filelist.py
│           │   │   ├── file_util.py
│           │   │   ├── __init__.py
│           │   │   ├── log.py
│           │   │   ├── msvc9compiler.py
│           │   │   ├── _msvccompiler.py
│           │   │   ├── msvccompiler.py
│           │   │   ├── py35compat.py
│           │   │   ├── py38compat.py
│           │   │   ├── spawn.py
│           │   │   ├── sysconfig.py
│           │   │   ├── text_file.py
│           │   │   ├── unixccompiler.py
│           │   │   ├── util.py
│           │   │   ├── versionpredicate.py
│           │   │   └── version.py
│           │   ├── errors.py
│           │   ├── extension.py
│           │   ├── extern
│           │   │   └── __init__.py
│           │   ├── glob.py
│           │   ├── gui-32.exe
│           │   ├── gui-64.exe
│           │   ├── gui-arm64.exe
│           │   ├── gui.exe
│           │   ├── _imp.py
│           │   ├── __init__.py
│           │   ├── installer.py
│           │   ├── launch.py
│           │   ├── monkey.py
│           │   ├── msvc.py
│           │   ├── namespaces.py
│           │   ├── package_index.py
│           │   ├── py34compat.py
│           │   ├── sandbox.py
│           │   ├── script (dev).tmpl
│           │   ├── script.tmpl
│           │   ├── unicode_utils.py
│           │   ├── _vendor
│           │   │   ├── __init__.py
│           │   │   ├── more_itertools
│           │   │   │   ├── __init__.py
│           │   │   │   ├── more.py
│           │   │   │   └── recipes.py
│           │   │   ├── ordered_set.py
│           │   │   ├── packaging
│           │   │   │   ├── __about__.py
│           │   │   │   ├── _compat.py
│           │   │   │   ├── __init__.py
│           │   │   │   ├── markers.py
│           │   │   │   ├── requirements.py
│           │   │   │   ├── specifiers.py
│           │   │   │   ├── _structures.py
│           │   │   │   ├── tags.py
│           │   │   │   ├── _typing.py
│           │   │   │   ├── utils.py
│           │   │   │   └── version.py
│           │   │   └── pyparsing.py
│           │   ├── version.py
│           │   ├── wheel.py
│           │   └── windows_support.py
│           ├── setuptools-58.2.0.dist-info
│           │   ├── entry_points.txt
│           │   ├── INSTALLER
│           │   ├── LICENSE
│           │   ├── METADATA
│           │   ├── RECORD
│           │   ├── top_level.txt
│           │   └── WHEEL
│           ├── setuptools-58.2.0.virtualenv
│           ├── _virtualenv.pth
│           ├── _virtualenv.py
│           ├── wheel
│           │   ├── bdist_wheel.py
│           │   ├── cli
│           │   │   ├── convert.py
│           │   │   ├── __init__.py
│           │   │   ├── pack.py
│           │   │   └── unpack.py
│           │   ├── __init__.py
│           │   ├── macosx_libfile.py
│           │   ├── __main__.py
│           │   ├── metadata.py
│           │   ├── pkginfo.py
│           │   ├── util.py
│           │   ├── vendored
│           │   │   ├── __init__.py
│           │   │   └── packaging
│           │   │       ├── __init__.py
│           │   │       ├── tags.py
│           │   │       └── _typing.py
│           │   └── wheelfile.py
│           ├── wheel-0.37.0.dist-info
│           │   ├── entry_points.txt
│           │   ├── INSTALLER
│           │   ├── LICENSE.txt
│           │   ├── METADATA
│           │   ├── RECORD
│           │   ├── top_level.txt
│           │   └── WHEEL
│           └── wheel-0.37.0.virtualenv
└── pyvenv.cfg

82 directories, 608 files
```
  
As you can see the Pipenv's virtual environment uses to bring a too populated list of folders and files. You don't need to worry about this, it's just the abstraction party, and you won't need this to make any changes, all things are set up for you and ready to use.

# Installing and Removing Dependencies (PIPENV)

Firstly, make sure you're under this environment.
```shell
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$
```
If not, run the following command.
### ` $ pipenv shell `
```
Launching subshell in virtual environment...
marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$  . /home/marcosranes/Desktop/Tutorials/.venv/bin/activate
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$
```
As you can see, it should call `source $PATH/.venv/bin/activate` for you.\
Note: One substitute for the `source` command is `.` and spacing after that...\
(e.g. `source .venv/bin/activate`, thus: `. .venv/bin/activate`), and realize through its output that the above command does exactly as explained here.

So, let's proceed to some command lines



### ` $ pipenv graph `
```
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ pipenv graph
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ 
```
Nothing was returned.. means there's no output for showing for you.

Similar commands:
### ` $ pipenv run pip freeze `
### ` $ pip freeze `

## Installing libraries
### ` $ pipenv install --dev grip `
```shell
Installing grip...
✔ Installation Succeeded 
Pipfile.lock (16c839) out of date, updating to (d37eb4)...
Locking [dev-packages] dependencies...
Building requirements...
✔ Success! 
Locking [packages] dependencies...
Updated Pipfile.lock (d37eb4)!
Installing dependencies from Pipfile.lock (d37eb4)...
  🎃   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 0/0 — 00:00:00
```
### ` $ cat Pipfile `
```
[[source]]
url = "https://pypi.org/simple"
verify_ssl = true
name = "pypi"

[packages]

[dev-packages]
grip = "*"

[requires]
python_version = "3.9"
```
As we can see, now you have the grip lib installed here as a dev dependency for running our project... 
 
Let's go further for more details. See these commands

### ` $ pipenv graph `
```
grip==4.5.2
  - docopt [required: >=0.4.0, installed: 0.6.2]
  - Flask [required: >=0.10.1, installed: 2.0.2]
    - click [required: >=7.1.2, installed: 8.0.3]
    - itsdangerous [required: >=2.0, installed: 2.0.1]
    - Jinja2 [required: >=3.0, installed: 3.0.2]
      - MarkupSafe [required: >=2.0, installed: 2.0.1]
    - Werkzeug [required: >=2.0, installed: 2.0.2]
  - Markdown [required: >=2.5.1, installed: 3.3.4]
  - path-and-address [required: >=2.0.1, installed: 2.0.1]
  - Pygments [required: >=1.6, installed: 2.10.0]
  - requests [required: >=2.4.1, installed: 2.26.0]
    - certifi [required: >=2017.4.17, installed: 2021.10.8]
    - charset-normalizer [required: ~=2.0.0, installed: 2.0.7]
    - idna [required: >=2.5,<4, installed: 3.3]
    - urllib3 [required: >=1.21.1,<1.27, installed: 1.26.7]
```

### ` $ pipenv run pip freeze `
```
certifi==2021.10.8
charset-normalizer==2.0.7
click==8.0.3
docopt==0.6.2
Flask==2.0.2
grip==4.5.2
idna==3.3
itsdangerous==2.0.1
Jinja2==3.0.2
Markdown==3.3.4
MarkupSafe==2.0.1
path-and-address==2.0.1
Pygments==2.10.0
requests==2.26.0
urllib3==1.26.7
Werkzeug==2.0.2
```
## Uninstalling Packages
### ` $ pipenv uninstall requests `
```
Uninstalling requests...
Found existing installation: requests 2.26.0
Uninstalling requests-2.26.0:
  Successfully uninstalled requests-2.26.0

Removing requests from Pipfile...
Locking [dev-packages] dependencies...
Building requirements...
✔ Success! 
Locking [packages] dependencies...
Updated Pipfile.lock (249526)!
```
### Uninstalling a dev dependency

### ` $ pipenv uninstall --dev grip ` or ` $ pipenv uninstall -d grip `
```text
Uninstalling grip...
Found existing installation: grip 4.5.2
Uninstalling grip-4.5.2:
  Successfully uninstalled grip-4.5.2

Removing grip from Pipfile...
Locking [dev-packages] dependencies...
Building requirements...
✔ Success! 
Locking [packages] dependencies...
Building requirements...
✔ Success! 
Updated Pipfile.lock (f65fb2)!
(Tutorials) marcosranes@ubuntu21-vbox:~/Desktop/Tutorials$ 
```

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
 
As you can see, both the sections packages and dev-packages were cleared! No pinned packages anymore.

### Courtesy: How to create a symbolic link
### ` $ ln -s Pipenv.md $VIRTUAL_ENV/../draft-README.md `
### ` $ unlink $VIRTUAL_ENV/../draft-README.md `
### ` $ echo $VIRTUAL_ENV `
```
/home/marcosranes/Desktop/Tutorials/.venv
```
 
## Spawning new features ` pipenv run ` 

### ` $ pipenv run python `
```
Python 3.9.7 (default, Oct 31 2021, 00:33:07) 
[GCC 10.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()
```

### ` $ pipenv run pip freeze `
```
```
See the [PIPENV documentation](https://pipenv-es.readthedocs.io/es/stable/)
