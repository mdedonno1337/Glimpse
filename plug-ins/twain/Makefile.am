## Process this file with automake to produce Makefile.in

libgimpui = $(top_builddir)/libgimp/libgimpui-$(GIMP_API_VERSION).la
libgimpconfig = $(top_builddir)/libgimpconfig/libgimpconfig-$(GIMP_API_VERSION).la
libgimpwidgets = $(top_builddir)/libgimpwidgets/libgimpwidgets-$(GIMP_API_VERSION).la
libgimp = $(top_builddir)/libgimp/libgimp-$(GIMP_API_VERSION).la
libgimpcolor = $(top_builddir)/libgimpcolor/libgimpcolor-$(GIMP_API_VERSION).la
libgimpbase = $(top_builddir)/libgimpbase/libgimpbase-$(GIMP_API_VERSION).la
libgimpmath = $(top_builddir)/libgimpmath/libgimpmath-$(GIMP_API_VERSION).la

libexecdir = $(gimpplugindir)/plug-ins/twain

libexec_PROGRAMS = twain


if OS_WIN32
twain_LDFLAGS = -mwindows -luser32

twainplatform = tw_win.c
endif

if HAVE_WINDRES
include $(top_srcdir)/build-aux/windows/gimprc-plug-ins.rule
twain_RC = twain.rc.o
endif


twain_SOURCES = \
	tw_func.c	\
	tw_func.h	\
	tw_util.c	\
	tw_util.h	\
	twain.c		\
	twain.h		\
	tw_local.h	\
	tw_platform.h	\
	$(twainplatform)

EXTRA_DIST = \
	README		\
	gimp-twain.png	\
	tw_dump.c	\
	tw_dump.h	\
	tw_win.c

AM_CPPFLAGS = \
	-I$(top_srcdir)	\
	$(GTK_CFLAGS)	\
	$(GEGL_CFLAGS)	\
	-I$(includedir)

LDADD = \
	$(libgimp)	\
	$(libgimpcolor)	\
	$(libgimpbase)	\
	$(GLIB_LIBS)	\
	$(RT_LIBS)	\
	$(INTLLIBS)	\
	$(twain_LIBS)	\
	$(twain_RC)
