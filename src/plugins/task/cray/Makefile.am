# Makefile for task/cray plugin

AUTOMAKE_OPTIONS = foreign

PLUGIN_FLAGS = -module -avoid-version --export-dynamic

AM_CPPFLAGS = -I$(top_srcdir) -I$(top_srcdir)/src/common

pkglib_LTLIBRARIES = task_cray.la

# Null task plugin.
task_cray_la_SOURCES = task_cray.c
task_cray_la_LDFLAGS = $(SO_LDFLAGS) $(PLUGIN_FLAGS)

if HAVE_REAL_CRAY
  task_cray_la_LIBADD = -ljob
endif
