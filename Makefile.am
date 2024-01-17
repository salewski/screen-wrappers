## Process this file with automake to produce Makefile.in -*-Makefile-*-

## SPDX-FileCopyrightText: <text>
##     © 2013, 2016, 2024 Alan D. Salewski <ads@salewski.email>
## </text>
##
## SPDX-License-Identifier: GPL-2.0-or-later


SUBDIRS = doc \
          src \
          .

# The ACLOCAL_AMFLAGS are used by 'autoreconf' and by the Makefile
# rebuild rule when they need to run 'aclocal'.
ACLOCAL_AMFLAGS = -I autotools


## ensure that these files make it into the distribution tarball
EXTRA_DIST = BUGS HACKING README.md

MAINTAINERCLEANFILES = config.status \
                       config.log    \
                       $(PACKAGE)-$(VERSION).tar.gz \
                       *~
