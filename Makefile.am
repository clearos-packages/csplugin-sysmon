AUTOMAKE_OPTIONS = foreign
ACLOCAL_AMFLAGS = -I m4

SUBDIRS = inih

EXTRA_DIST = csplugin-events.conf csplugin-events.h events-alert.h \
	events-conf.h events-db.h events-db-sql.h events-socket.h \
	events-syslog.h eventsctl.h deploy/rsyslog.conf \
	csplugin-events.spec autogen.sh deploy/events.d

AM_CFLAGS = ${CFLAGS}
AM_CXXFLAGS = ${CXXFLAGS}

lib_LTLIBRARIES = libcsplugin-events.la

libcsplugin_events_la_SOURCES = csplugin-events.cpp events-alert.cpp \
				events-conf.cpp events-db.cpp \
				events-socket.cpp events-syslog.cpp
libcsplugin_events_la_CXXFLAGS = ${AM_CXXFLAGS}
libcsplugin_events_la_LIBADD = $(srcdir)/inih/libini.la

bin_PROGRAMS = eventsctl

eventsctl_SOURCES = eventsctl.cpp
eventsctl_CXXFLAGS = ${AM_CXXFLAGS}
eventsctl_LDADD = -lclearsync libcsplugin-events.la

