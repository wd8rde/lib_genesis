
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

noinst_PROGRAMS = test
test_SOURCES = main.cpp
test_LDADD = .libs/lib_genesis.la

