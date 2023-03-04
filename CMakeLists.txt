cmake_minimum_required(VERSION 3.22)
# State the minimum version of cmake required to be 3.22

project(myProject VERSION 1.0.0)
# Name project myProject and specify the VERSION variable to be 1.0.0

add_subdirectory(say-hello)
# Format:
# add_subdirectory(source_dir [binary_dir] [EXCLUDE_FROM_ALL] [SYSTEM])
# 
# This tells cmake to look for another CMakeLists.txt in the source_dir
# say-hello

add_subdirectory(main)
# We need to ensure that say-hello is defined before main so that the library
# is properly linked to the main executable 
