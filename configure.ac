#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.60)
AC_INIT(genesissdr, 1.0, [wd8rde@gmail.com>])
AC_CONFIG_MACRO_DIRS([m4])
#AM_INIT_AUTOMAKE([-Wall -Werror foreign])
#AM_INIT_AUTOMAKE([-Werror foreign])
AM_INIT_AUTOMAKE([subdir-objects])
AC_CONFIG_SRCDIR([genesis.cpp])
#AC_CONFIG_HEADER([config.h])

AC_CANONICAL_HOST

# Checks for programs.
AC_PROG_CC
AC_PROG_CXX
LT_INIT([dlopen])

dnl XXX we need to cover Intel as well as PowerPC
if test $host_cpu = "powerpc" && test $host_vendor = "apple"; then

	dnl set specific macosx paths (fink)
	CFLAGS="$CFLAGS -I/sw/include"
	LDFLAGS="$LDFLAGS -L/sw/lib"
	CPPFLAGS="$CPPFLAGS -I/sw/include"
fi

# Checks for libraries.
AC_CHECK_LIB([hidapi-libusb], [hid_get_serial_number_string], ,
	[AC_MSG_ERROR("Could not find library hidapi-libusb.")])
AC_CHECK_LIB([pthread], [pthread_create])

# Checks for header files.
AC_HEADER_STDC
AC_HEADER_SYS_WAIT
AC_CHECK_HEADERS([fcntl.h stdlib.h string.h sys/time.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_C_INLINE
AC_TYPE_SIZE_T
AC_HEADER_TIME
AC_HEADER_STDBOOL
AC_TYPE_UID_T

# Checks for library functions.
AC_PROG_GCC_TRADITIONAL
AC_FUNC_STAT
AC_CHECK_FUNCS([memset])
PKG_CHECK_MODULES(HID, hidapi-libusb >= 0.8)

PKG_PROG_PKG_CONFIG
PKG_INSTALLDIR

AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([genesissdr.pc])
AC_OUTPUT
