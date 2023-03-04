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

target_include_directories(say-hello PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")
# Format:
# target_include_directories(<target> [SYSTEM] [AFTER|BEFORE]
#  <INTERFACE|PUBLIC|PRIVATE> [items1...]
#  [<INTERFACE|PUBLIC|PRIVATE> [items2...] ...])
#
# This command adds this directory as a path to included files for the library
# say-hello. PUBLIC means that the executables that link this library will also
# inhereit this include path. The variable CMAKE_CURRENT_SOURCE_DIR is the
# directory that is currently being processed. So when this file is processed,
# the directory this file is in is added as an include directory to say-hello.
