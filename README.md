<!-- markdownlint-disable MD010 -->
<!-- markdownlint-disable MD014 -->

# Scoop-Python

A [Scoop](https://github.com/lukesampson/scoop) bucket for Python applications that do not provide
standalone executables.

	$ scoop bucket add python https://github.com/TheRandomLabs/Scoop-Python.git

This bucket is an alternative to using pip to install these packages.

Note that for the purpose of avoiding conflicts, uninstalling a package in this bucket will not
uninstall its dependencies.

For local installs, binaries may not be added to PATH due to
[ScoopInstaller/Main#772](https://github.com/ScoopInstaller/Main/issues/772).

Global installs will be reset after Python is updated due to
[lukesampson/scoop#2180](https://github.com/lukesampson/scoop/issues/2180).
