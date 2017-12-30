
lib_LTLIBRARIES = lib_genesis.la
lib_genesis_la_CPPFLAGS = $(HID_CFLAGS) -std=gnu++0x
lib_genesis_la_CDFLAGS = $(HID_LIBS)

lib_genesis_la_SOURCES = \
	genesis.cpp\
	cmdbase.cpp\
	cmdpacket.cpp\
	genesis_observer.cpp\
	hid_util.cpp\
	bsd_string.c\
	si570.c\
	simpleini-master/ConvertUTF.c

lib_genesis_ladir = $(includedir)/genesissdr

nobase_lib_genesis_la_HEADERS = \
	genesis.h\
	genesis_observer.h\
	hid_util.h\
	g59cmd.h\
	simpleini-master/SimpleIni.h\
	simpleini-master/ConvertUTF.h\
	cmdbase.h\
	g11cmd.h\
	si570.h\
	bsd_string.h\
	cmdpacket.h

noinst_PROGRAMS = test
test_SOURCES = main.cpp
test_LDADD = .libs/lib_genesis.la

# Install the pkg-config file; the directory is set using
# PKG_INSTALLDIR in configure.ac.
pkgconfig_DATA = genesissdr.pc
