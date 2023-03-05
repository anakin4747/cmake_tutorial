add_executable(cmake-good main.c)
# Format:
# add_executable(<name> [WIN32] [MACOSX_BUNDLE]
#              [EXCLUDE_FROM_ALL]
#              [source1] [source2 ...])
#
# So the executable made will be cmake-good using the source file main.c
# no other options are passed
# The files are both relative to the directory that this file is in

target_link_libraries(cmake-good PUBLIC say-hello)
# target_link_libraries(<target>
#                       <PRIVATE|PUBLIC|INTERFACE> <item>...
#                      [<PRIVATE|PUBLIC|INTERFACE> <item>...]...)
#
# This command links the say-hello library to the linker for compilation.
# The say-hello library needs to be defined before this to work correctly.


