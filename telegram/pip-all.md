---
title: How to Update All Python Packages
tags: reference, email, snippets, wtf, documentation, medium, cli, linux
davodtime: 09252022-061521
local: shareddocuments:///private/var/mobile/Library/Mobile%20Documents/iCloud~md~obsidian/Documents/OBSHIDDIAN/drafts/EFF9B7B5-25A6-4B07-8860-EFDB587D87BB.md
dg-publish: true
share: true
draft: drafts://open?uuid=EFF9B7B5-25A6-4B07-8860-EFDB587D87BB
---
Updated `09252022-061200`

- [Source](https://www.activestate.com/resources/quick-reads/how-to-update-all-python-packages/)
- [WTF](https://davidblue.wtf/drafts/EFF9B7B5-25A6-4B07-8860-EFDB587D87BB.html)
- [Archive](http://web.archive.org/web/20220925091221/https://www.activestate.com/resources/quick-reads/how-to-update-all-python-packages/)
- [pip Update Shortcut](drafts://open?uuid=84F3BCEE-4BA4-43B3-A85E-45EA8410FA19)
- [Medium](https://medium.com/handset/how-to-update-all-python-packages-with-a-single-pip-command-dc0657f0dc7d)
- [Telegraph](https://telegra.ph/How-to-Update-all-Python-Packages-with-a-Single-pip-Command-09-25)
- [**Gist**](https://gist.github.com/extratone/e1cc5b3053573aa5ca4e41468470c3cb)
- [Pastebin](https://pastebin.com/RJNvuhi9)
- [How to Update All Python Packages](https://chaff.writeas.com/how-to-update-all-python-packages)

---

<script src="https://gist.github.com/extratone/e1cc5b3053573aa5ca4e41468470c3cb.js"></script>

**Shell Commands**

```shell
pip list --outdated
pip freeze | %{$_.split('==')[0]} | %{pip install --upgrade $_}
pip3 list --outdated --format=freeze | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip3 install -U
pip3 list -o | cut -f1 -d' ' | tr " " "\n" | awk '{if(NR>=3)print)' | cut -d' ' -f1 | xargs -n1 pip3 install -U
pip freeze > requirements.txt
pip install -r requirements.txt --upgrade
pipenv shell
pipenv update
```

**Python Script**

```python
import pkg_resources from subprocess import call for dist in pkg_resources.working_set:     call("python -m pip install --upgrade " + dist.<projectname>, shell=True)
```

---

# How to Update all Python Packages with a Single pip Command

![The Psalms PyPi](https://user-images.githubusercontent.com/43663476/192139585-4ab7baac-b9c3-4ab4-a334-3eea9e9a85df.png)

## Ensure all present Python packages on Windows and Linux systems are parallel with their latest available versions from the command line.

With Python, the best practice of pinning all the packages in an environment at a specific version ensures that the environment can be reproduced months or even years later.

- Pinned packages in a requirements.txt file are denoted by `==`. For example, `requests==2.21.0`. Pinned packages should never be updated except for a very good reason, such as to fix a critical bug or vulnerability.
- Conversely, unpinned packages are typically denoted by `>=`, which indicates that the package can be replaced by a later version. Unpinned packages are more common in development environments, where the latest version can offer bug fixes, security patches and even new functionality.

As packages age, many of them are likely to have vulnerabilities and bugs logged against them. In order to maintain the security and performance of your application, you’ll need to update these packages to a newer version that fixes the issue.

The [pip package manager](https://pip.pypa.io/en/stable/ "pip Documentation") can be used to update one or more packages system-wide. However, if your deployment is located in a virtual environment, you should use the Pipenv package manager to update all Python packages. 

**NOTE:** be aware that upgrading packages can break your environment by installing incompatible dependencies. This is because pip and pipenv do not resolve dependencies.

## Python Package Upgrade Checklist

In general, you can use the following steps to perform a package upgrade:

1. Check that Python is installed

Before packages can be updated, ensure that a Python installation containing the necessary files needed for updating packages is in place by following the steps outlined in "[Using Python on Windows]" in the official documentation.

2. Get a list of all the outdated packages

To generate a list of all outdated packages:

```shell
pip list --outdated
```

3. Upgrade outdated packages

Depending on your operating system or virtual environment, refer to the following sections.

The easiest way to update all packages in a Windows environment is to use pip in conjunction with Windows PowerShell:

1. Open a command shell by typing `powershell` in the Search Box of the Task bar
2. Enter:

```shell
pip freeze | %{$_.split('==')[0]} | %{pip install --upgrade $_}

```

This will upgrade all packages system-wide to the latest version available in the [Python Package Index](https://pypi.org "Python Package Index") (PyPI).

## Update all Python Packages on Linux

Linux provides a number of ways to use pip in order to upgrade Python packages, including grep and awk.

To upgrade all packages using pip _with **grep**_ on Ubuntu Linux:

```shell
pip3 list --outdated --format=freeze | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip3 install -U
```

To upgrade all packages using pip _with **awk**_ on Ubuntu Linux:

```shell
pip3 list -o | cut -f1 -d' ' | tr " " "\n" | awk '{if(NR>=3)print)' | cut -d' ' -f1 | xargs -n1 pip3 install -U
```

## Updating Python Packages on Windows or Linux

Pip can be used to upgrade all packages on either Windows or Linux:

1. Output a list of installed packages into a requirements file (requirements.txt):

```shell
pip freeze > requirements.txt
```

1. Edit requirements.txt, and replace all `==` with `>=`. Use the `Replace All` command in the editor.
2. Upgrade all outdated packages:

```shell
pip install -r requirements.txt --upgrade
```

## Updating all Packages in a Virtual Environment

The easiest way to update unpinned packages (i.e., packages that do not require a specific version) in a virtual environment is to run the following Python script that makes use of pip:

```python
import pkg_resources from subprocess import call for dist in pkg_resources.working_set:     call("python -m pip install --upgrade " + dist.<projectname>, shell=True)
```

## Updating all Packages in a Pipenv Environment

The simplest way to update all the unpinned packages in a specific virtual environment created with pipenv is to do the following steps:

1. Activate the Pipenv shell that contains the packages to be upgraded:

```shell
pipenv shell
pipenv update
```
