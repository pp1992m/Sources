#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.63])
AC_INIT([libgfan], [0.6], [ren@mathematik.uni-kl.de])
AC_CONFIG_MACRO_DIR([../m4])
AC_CONFIG_AUX_DIR([../build-aux])
AC_CONFIG_SRCDIR([gfanlib.h])
AC_CONFIG_HEADER([_config.h])

AM_INIT_AUTOMAKE([-Wall foreign subdir-objects]) # -Wno-extra-portability -Werror silent-rules
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])
m4_ifdef([AM_PROG_AR], [AM_PROG_AR])

# Add pre'prefixed config
AX_PREFIX_CONFIG_H([config.h],[],[_config.h])

AM_MAINTAINER_MODE([enable])

SING_RESET_FLAGS()
SING_CHECK_SET_ARGS()

# Checks for programs.
# AC_PROG_CC
# AC_PROG_CXX
AC_PROG_LN_S
#AC_PROG_INSTALL

# Checks for libraries.
LT_INIT([win32-dll])

SING_WIN_FLAGS

# Checks for header files.
AC_HEADER_STDC

# Checks for typedefs, structures, and compiler characteristics.
AC_C_INLINE

LB_CHECK_GMP(4.0,,AC_MSG_ERROR([Unable to find GMP on your machine: please use --with-gmp=PATH_TO_DIR_CONTAINING_LIB_AND_INCLUDE (see also ./configure --help if you do not understand what we are talking about)]))

SING_CHECK_GFANLIB

AC_LANG_PUSH(C++)
AX_CHECK_COMPILE_FLAG([-std=c++11], [CXX11_FLAG="-std=c++11"], [CXX11_FLAG="-std=c++0x"], [])
AC_SUBST(CXX11_FLAG)
AC_LANG_POP()

#AC_MSG_RESULT($ac_cv_singuname)
#if test "$ac_cv_singuname" = unknown; then
#  AC_MSG_WARN(Unknown architecture: Check singuname.sh)
#  ac_cv_singuname="unknown"
#fi
#AC_DEFINE_UNQUOTED(S_UNAME, "$ac_cv_singuname")
#SINGUNAME=$ac_cv_singuname
#AC_SUBST(SINGUNAME)

AC_CONFIG_FILES([Makefile])
## AC_CONFIG_HEADERS([config.h])
AC_OUTPUT
