## Process this file with automake to produce Makefile.in

# The name of the module.
DOC_MODULE = libgimpbase3

# The top-level SGML file.
DOC_MAIN_SGML_FILE = $(DOC_MODULE)-docs.sgml

# The directory containing the source code.
DOC_SOURCE_DIR = $(top_srcdir)/libgimpbase

# Extra options to pass to gtkdoc-scangobj
SCANGOBJ_OPTIONS =

# Extra options to supply to gtkdoc-scan
SCAN_OPTIONS = --deprecated-guards="GIMP_DISABLE_DEPRECATED"

# Extra options to supply to gtkdoc-mkdb
MKDB_OPTIONS = --sgml-mode --output-format=xml --name-space=gimp

# Extra options to supply to gtkdoc-fixref
FIXXREF_OPTIONS =

# Used for dependencies
HFILE_GLOB = $(DOC_SOURCE_DIR)/*.h
CFILE_GLOB = $(DOC_SOURCE_DIR)/*.c

# Header files to ignore when scanning
IGNORE_HFILES = \
	gimpbase.h		\
	gimpbase-private.h	\
	gimpcompatenums.h	\
	gimpprotocol.h		\
	gimpreloc.h		\
	gimpwire.h		\
	gimpwin32-io.h

# Images to copy into HTML directory
HTML_IMAGES=

# Extra SGML files that are included by $(DOC_MAIN_SGML_FILE)
content_files =

# Other files to distribute
extra_files =

# CFLAGS and LDFLAGS for compiling scan program. Only needed
# if $(DOC_MODULE).types is non-empty.
GTKDOC_CFLAGS = \
	@CFLAGS@		\
	-I$(top_srcdir) 	\
	-I$(top_builddir) 	\
	@GEGL_CFLAGS@

GTKDOC_LIBS = \
	$(top_builddir)/libgimpbase/libgimpbase-$(GIMP_API_VERSION).la		\
	$(top_builddir)/libgimpcolor/libgimpcolor-$(GIMP_API_VERSION).la	\
	@GEGL_LIBS@


include $(top_srcdir)/gtk-doc.make

# This is a hack. The entire commit must be reverted once
# this file gets removed by gtk-doc.make
CLEANFILES += $(DOC_MODULE).actions
