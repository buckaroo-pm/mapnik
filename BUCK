include_defs('//BUCKAROO_DEPS')

prebuilt_cxx_library(
  name = 'config', 
  header_namespace = 'mapnik', 
  header_only = True, 
  exported_headers = {
    'config.hpp': 'include/mapnik/config.hpp', 
  }, 
  visibility = [
    'PUBLIC', 
  ], 
)

prebuilt_cxx_library(
  name = 'warning-ignore', 
  header_namespace = 'mapnik', 
  header_only = True, 
  exported_headers = {
    'warning_ignore.hpp': 'include/mapnik/warning_ignore.hpp', 
  }, 
  visibility = [
    'PUBLIC', 
  ], 
)

windows_srcs = glob([
  'src/**/*_win.cpp', 
])

platform_srcs = windows_srcs

cxx_library(
  name = 'mapnik',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('include', 'mapnik/**/*.hpp'), 
  ]), 
  srcs = glob([
    'src/**/*.cpp',
  ], exclude = platform_srcs),
  platform_srcs = [
    ('windows.*', windows_srcs), 
  ], 
  deps = [
    '//deps/agg:agg', 
    '//deps/boost/geometry:geometry', 
    '//deps/boost/gil:gil', 
    '//deps/mapnik/sparsehash:sparsehash', 
  ] + BUCKAROO_DEPS,
  visibility = [
    'PUBLIC', 
  ], 
)
