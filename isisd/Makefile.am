## Process this file with automake to produce Makefile.in.

AM_CPPFLAGS = -I.. -I$(top_srcdir) -I$(top_srcdir)/lib -I$(top_builddir)/lib
DEFS = @DEFS@ -DSYSCONFDIR=\"$(sysconfdir)/\"
INSTALL_SDATA=@INSTALL@ -m 600
LIBS = @LIBS@ 

AM_CFLAGS = $(WERROR)

noinst_LIBRARIES = libisis.a
sbin_PROGRAMS = isisd

libisis_a_SOURCES = \
	isis_memory.c \
	isis_adjacency.c isis_lsp.c dict.c isis_circuit.c isis_pdu.c \
	isisd.c isis_misc.c isis_zebra.c isis_dr.c \
	isis_flags.c isis_dynhn.c iso_checksum.c isis_csm.c isis_events.c \
	isis_spf.c isis_redist.c isis_route.c isis_routemap.c isis_te.c \
	isis_vty.c isis_mt.c \
	isis_tlvs.c


noinst_HEADERS = \
	isis_memory.h \
	isisd.h isis_pdu.h isis_adjacency.h isis_constants.h \
	isis_lsp.h dict.h isis_circuit.h isis_misc.h isis_network.h \
	isis_zebra.h isis_dr.h isis_flags.h isis_dynhn.h isis_common.h \
	iso_checksum.h isis_csm.h isis_events.h isis_spf.h isis_redist.h \
	isis_route.h isis_routemap.h isis_te.h isis_mt.h \
	isis_tlvs.h

isisd_SOURCES = \
	isis_main.c $(libisis_a_SOURCES) \
	isis_bpf.c isis_dlpi.c isis_pfpacket.c

isisd_LDADD = ../lib/libfrr.la @LIBCAP@

examplesdir = $(exampledir)
dist_examples_DATA = isisd.conf.sample
