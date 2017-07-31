This is the README.md file for the `'screen-wrappers'` project.

# Overview

The 'screen-wrappers' project provides a collection of programs that wrap
various common invocations of the [GNU screen(1) program][SCREEN].

The 'screen-wrappers' project web site is:

   * https://salewski.github.io/screen-wrappers/

The latest version of the project is `0.3.2`, and can be downloaded from:

   * https://salewski.github.io/screen-wrappers/downloads/screen-wrappers-0.3.2.tar.gz
   * https://salewski.github.io/screen-wrappers/downloads/screen-wrappers-0.3.2.tar.gz.SHA-1
   * https://salewski.github.io/screen-wrappers/downloads/screen-wrappers-0.3.2.tar.gz.SHA-256
   * https://salewski.github.io/screen-wrappers/downloads/screen-wrappers-0.3.2.tar.gz.SHA3-256
    
Older releases are available from the project's downloads page:

   * https://salewski.github.io/screen-wrappers/downloads/

The current version provides only the `screen-ls(1)` program, which will
format the output of `'screen -ls'` into a table (which improves readability),
display the screen session names without the leading pid value (for easier
sorting), etc.

The goal of the `'screen-wrappers'` project is to provide a central location
to collect tools that wrap screen invocations. It is hoped that productizing
and sharing these tools will lead both to improvements of the tools
themselves, help document best practices and/or useful screen recipes, and
otherwise make them available to a wider audience.

Once installed, you will want to read:

   * [screen-ls(1)]


See the "Prerequisites" section below for other programs that must be
installed and configured on your system before you can install the
`'screen-wrappers'` package.

See the [BUGS] file for information on reporting bugs.

See the [INSTALL] file for installation instructions.

See the [HACKING] file for developer build instructions and the like.

See the [NEWS] file for changes for this release, and a running list of
changes from previous releases. Any incompatibilities with previous versions
will be noted in the `'NEWS'` file.


## Prerequisites

`'screen-wrappers'` is intended to be built and run on Unix and Unix-like
systems, so expects a standard set of utilities (`cat`, `sed`, `awk`, `rm`,
...) to be present. These utilities are not explicitly listed below as
prerequisites as they should be present on any modern Unix or GNU/Linux system
(or in Cygwin, if you happen to be running on MS Windows).

The `'screen-ls'` program (and possibly other tools in the `'screen-wrappers'`
project) is implemented in Bash (a Bourne shell derivative). The
'screen-wrappers' project was developed and tested using Bash versions 4.2.37
and 4.3.30. It uses associative arrays which were added in Bash 4.0, so you'll
need a 4.x version or newer; the `'configure'` script will check for this and
exit with an error message if a new enough version of Bash is not found. The
author would appreciate hearing about any successes or failures with other
versions of Bash. In the unlikely event that your system does not already have
bash installed, it can be obtained from the project's site:

   * http://www.gnu.org/software/bash/

On a Debian system (including derivatives, such as Ubuntu), you can install
the program via:
```
    # apt-get install bash
```

or (for a statically linked version):
```
    # apt-get install bash-static
```

Because the `'screen-wrappers'` programs are wrappers around the GNU
`'screen'` program, that needs to be installed as well (of course). The
'screen' program is available here:

   * http://www.gnu.org/software/screen/

On a Debian system (including derivatives, such as Ubuntu), you can probably
install the program via:
```
    # apt-get install screen
```


# License

GPLv2+: GNU GPL version 2 or later <http://gnu.org/licenses/gpl.html>

Unless otherwise stated by a different license notice in a particular file,
all files in the `screen-wrappers' project are made available under the GNU
GPL version 2, or (at your option) any later version.

See the [COPYING] file for the full license.

Copyright (C) 2013, 2016, 2017 Alan D. Salewski <salewski@att.net>

    This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation; either version 2 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License along
    with this program; if not, write to the Free Software Foundation, Inc.,
    51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.



[BUGS]:         https://github.com/salewski/screen-wrappers/blob/master/BUGS
[COPYING]:      https://github.com/salewski/screen-wrappers/blob/master/COPYING
[HACKING]:      https://github.com/salewski/screen-wrappers/blob/master/HACKING
[INSTALL]:      https://github.com/salewski/screen-wrappers/blob/master/INSTALL
[NEWS]:         https://github.com/salewski/screen-wrappers/blob/master/NEWS
[screen-ls(1)]: https://salewski.github.io/screen-wrappers/man/man1/screen-ls.1.html
[SCREEN]:       http://www.gnu.org/software/screen/
