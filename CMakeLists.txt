cmake_minimum_required(VERSION 3.22)
# State the minimum version of cmake required to be 3.22

project(myProject VERSION 1.0.0)
# Name project myProject and specify the VERSION variable to be 1.0.0

add_library(
    say-hello
    hello.h
    hello.c
    )
# add_library(<name> [STATIC | SHARED | MODULE]
#              [EXCLUDE_FROM_ALL]
#              [<source>...])
#
# So we add a library called say-hello from the source files hello.h and
# hello.c
# The library that is created will follow the format lib<name>.a for UNIX
# systems so this one will be called libsay-hello.a 
# This will be a STATIC library as the default is static and I did not specify
# a type of library

add_executable(cmake-good main.c)
# Format:
# add_executable(<name> [WIN32] [MACOSX_BUNDLE]
#              [EXCLUDE_FROM_ALL]
#              [source1] [source2 ...])
#
# So the executable made will be cmake-good using the source file main.c
# no other options are passed
# The files are both relative to the directory that this file is in

target_link_libraries(cmake-good PRIVATE say-hello)
# target_link_libraries(<target>
#                       <PRIVATE|PUBLIC|INTERFACE> <item>...
#                      [<PRIVATE|PUBLIC|INTERFACE> <item>...]...)
#
# This command links the say-hello library to the linker for compilation


