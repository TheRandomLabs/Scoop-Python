<!-- markdownlint-disable MD010 -->
<!-- markdownlint-disable MD014 -->
<!-- markdownlint-disable MD046 -->

# Scoop-Python

A [Scoop](https://github.com/lukesampson/scoop) bucket for Python applications that do not provide
standalone executables.

	$ scoop bucket add python https://github.com/TheRandomLabs/Scoop-Python.git

This bucket is an alternative to using pip to install these packages.

## Reasoning

* pip does not have a built-in functionality to update all packages. This is inconvenient for
command-line tools and other executable applications such as HTTPie.
* pip does not have a simple way to preserve packages between Python updates. Again, this is
inconvenient for command-line tools and other executable applications such as HTTPie.
* Python virtual environments should be used to install other packages, so only executable
applications are accepted into this bucket.

## Drawbacks

* For the purpose of avoiding conflicts, uninstalling a package in this bucket will not
uninstall its dependencies.
* For local installs, binaries may not be added to PATH due to
[ScoopInstaller/Main#772](https://github.com/ScoopInstaller/Main/issues/772).
* Packages installed globally from this bucket will need to be migrated for any Python update.
* Packages installed locally from this bucket will need to be migrated for any minor or major
Python update.
* A script to migrate packages in this bucket between Python versions is provided in the `scripts`
directory of this bucket:

```powershell
$ & "$(Split-Path (Split-Path (Get-Command scoop).Source))\buckets\python\scripts\migrate-python-packages.ps1" --help
```
