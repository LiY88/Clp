# Copyright (C) 2006 International Business Machines and others.
# All Rights Reserved.
# This file is distributed under the Eclipse Public License.

## $Id: Makefile.am 1152 2007-12-28 03:59:07Z andreasw $

# Author:  Andreas Waechter           IBM    2006-04-13

AUTOMAKE_OPTIONS = foreign

include $(top_srcdir)/BuildTools/Makemain.inc

########################################################################
#                             libOsiClp                                #
########################################################################

# Name of the library compiled in this directory.
lib_LTLIBRARIES = libOsiClp.la

# List all source files for this library, including headers
libOsiClp_la_SOURCES = OsiClpSolverInterface.cpp OsiClpSolverInterface.hpp

# List all additionally required libraries
libOsiClp_la_LIBADD = $(OSICLPLIB_LFLAGS) ../libClp.la

# This is for libtool (on Windows)
libOsiClp_la_LDFLAGS = $(LT_LDFLAGS)

# Here list all include flags, relative to this "srcdir" directory.
AM_CPPFLAGS = -I$(srcdir)/.. $(OSICLPLIB_CFLAGS) -DOSICLP_BUILD

########################################################################
#                Headers that need to be installed                     #
########################################################################

# Here list all the header files that are required by a user of the library,
# and that therefore should be installed in 'include/coin-or'

includecoindir = $(pkgincludedir)
includecoin_HEADERS = OsiClpSolverInterface.hpp

install-exec-local:
	$(install_sh_DATA) config_osiclp.h $(DESTDIR)$(includecoindir)/OsiClpConfig.h

uninstall-local:
	rm -f $(DESTDIR)$(includecoindir)/OsiClpConfig.h
