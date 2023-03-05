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

target_compile_definitions(say-hello PUBLIC SAY_HELLO_VERSION=3)
# Format:
# target_compile_definitions(<target>
#   <INTERFACE|PUBLIC|PRIVATE> [items1...]
#   [<INTERFACE|PUBLIC|PRIVATE> [items2...] ...])
#
# This allows us to define a Macro called SAY_HELLO_VERSION that gets replace
# with 2. We can use this Macro in our project and control its scope with
# INTERFACE, PUBLIC, or PRIVATE. Public means everything that inhereits this
# library inhereits this Macro. Private means the scope is limited to the
# library and things that inhereit the library dont inhereit this Macro.
# Interface is the opposite of PRIVATE with the macro only being defined by
# consumers of the library but not defined within the library itself
