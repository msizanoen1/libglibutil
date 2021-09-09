project(
    'libglibutil', 'c',
    version : '1.0.55',
)

pc = import('pkgconfig')

glib = dependency('glib-2.0')
gobject = dependency('gobject-2.0')

headers = [
    'include/gutil_history.h',
    'include/gutil_idlepool.h',
    'include/gutil_idlequeue.h',
    'include/gutil_inotify.h',
    'include/gutil_intarray.h',
    'include/gutil_ints.h',
    'include/gutil_log.h',
    'include/gutil_macros.h',
    'include/gutil_misc.h',
    'include/gutil_ring.h',
    'include/gutil_strv.h',
    'include/gutil_timenotify.h',
    'include/gutil_types.h',
]

install_headers(headers, subdir : 'libglibutil')

sources = [
    'src/gutil_history.c',
    'src/gutil_idlepool.c',
    'src/gutil_idlequeue.c',
    'src/gutil_inotify.c',
    'src/gutil_intarray.c',
    'src/gutil_ints.c',
    'src/gutil_log.c',
    'src/gutil_misc.c',
    'src/gutil_ring.c',
    'src/gutil_strv.c',
    'src/gutil_timenotify.c',
]

incdir = include_directories('include')

lib = library(
    'glibutil',
    sources : sources,
    dependencies : [glib, gobject],
    include_directories : incdir,
    version : meson.project_version(),
    install : true,
)

pc.generate(
    lib,
    name : 'libglibutil',
    description : 'Library of glib utilities',
    subdirs : 'libglibutil',
    requires : [glib],
)
