# Makefile for jobcomp/pgsql plugin

AM_CPPFLAGS = $(PGSQL_CFLAGS) \
	-I$(top_srcdir) -I$(top_srcdir)/src/common
AUTOMAKE_OPTIONS = foreign

PLUGIN_FLAGS = -module -avoid-version --export-dynamic

if WITH_PGSQL
pkglib_LTLIBRARIES = jobcomp_pgsql.la

# Pgsql storage plugin.
jobcomp_pgsql_la_SOURCES = jobcomp_pgsql.c \
			pgsql_jobcomp_process.c pgsql_jobcomp_process.h
jobcomp_pgsql_la_LDFLAGS = $(SO_LDFLAGS) $(PLUGIN_FLAGS)
jobcomp_pgsql_la_CFLAGS = $(PGSQL_CFLAGS)
jobcomp_pgsql_la_LIBADD  = $(top_builddir)/src/database/libslurm_pgsql.la \
	$(PGSQL_LIBS)
jobcomp_pgsql_la_DEPENDENCIES = $(top_builddir)/src/database/libslurm_pgsql.la
else
EXTRA_jobcomp_pgsql_la_SOURCES = jobcomp_pgsql.c \
		pgsql_jobcomp_process.c pgsql_jobcomp_process.h
endif
