# The Flutter tooling requires that developers have CMake 3.10 or later
# installed. You should not increase this version, as doing so will cause
# the plugin to fail to compile for some customers of the plugin.
cmake_minimum_required(VERSION 3.10)

project(native_miniaudio_library VERSION 0.0.1 LANGUAGES C)

add_library(native_miniaudio SHARED
  "extras/miniaudio_split/miniaudio.c"
)

set_target_properties(native_miniaudio PROPERTIES
  PUBLIC_HEADER extras/miniaudio_split/miniaudio.h
  OUTPUT_NAME "native_miniaudio"
)

target_compile_definitions(native_miniaudio PUBLIC DART_SHARED_LIB)
