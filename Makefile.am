ACLOCAL_AMFLAGS = -I m4

AM_CPPFLAGS = -I$(top_srcdir)/include -DMINGW_HAS_SECURE_API=1

dist_doc_DATA =

lib_LTLIBRARIES = libmfx.la

libmfx_la_SOURCES = \
    src/mfx_critical_section.h       \
    src/mfx_exposed_functions_list.h \
    src/mfx_dispatcher.h             \
    src/mfx_dispatcher_log.h         \
    src/mfx_library_iterator.h       \
    src/mfx_load_dll.h               \
    src/main.cpp                     \
    src/mfx_critical_section.cpp     \
    src/mfx_dispatcher.cpp           \
    src/mfx_dispatcher_log.cpp       \
    src/mfx_load_plugin.cpp          \
    src/mfx_plugin_cfg_parser.cpp    \
    src/mfx_function_table.cpp


if WINDOWS
libmfx_la_SOURCES += \
    src/mfx_dxva2_device.h           \
    src/mfx_win_reg_key.h            \
    src/mfx_dxva2_device.cpp         \
    src/mfx_library_iterator.cpp     \
    src/mfx_load_dll.cpp             \
    src/mfx_win_reg_key.cpp          \
    src/mfx_plugin_hive.cpp
else
libmfx_la_SOURCES += \
    src/mfx_va_glue.c                  \
    src/mfx_critical_section_linux.cpp \
    src/mfx_library_iterator_linux.cpp \
    src/mfx_load_dll_linux.cpp         \
    src/mfx_plugin_hive_linux.cpp
endif


libmfx_la_LDFLAGS = -version-info $(MFX_LT_CURRENT):$(MFX_LT_REVISION):$(MFX_LT_AGE)
libmfx_la_LIBADD = -lsupc++ $(LIBVA_DRM_LIBS) $(LIBVA_X11_LIBS)

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = libmfx.pc

pkginclude_HEADERS = \
	mfx/mfxsession.h                 \
	mfx/mfxdefs.h                    \
	mfx/mfxla.h                      \
	mfx/mfxenc.h                     \
	mfx/mfxplugin.h                  \
	mfx/mfxcommon.h              	 \
	mfx/mfxvstructures.h             \
	mfx/mfxstructures.h              \
	mfx/mfxvideo.h

pkgincludedir = $(includedir)/mfx
