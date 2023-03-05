cmake_minimum_required(VERSION 3.22)

project(myProject VERSION 1.0.0)
# Project sets a variable called ${PROJECT_NAME} to the name of the project
# and sets a variable called ${PROJECT_VERSION} to the value that follows the
# keyword VERSION

# All data types in cmake are strings
# No commas only whitespace to delimit arguments

set(MY_VARIABLE "I am a Variable")
# Variables in cmake are not set with an assignment operator "="
# Instead they are set with the set command. Above I am setting a variable
# called MY_VARIABLE to the value "I am a Variable".
# To reference this variable elsewhere you need to use ${variable name}

message(STATUS "I am a message\nThis is a variable ${MY_VARIABLE}")
# A command analogous to echo or printf
# We need quotes here to ensure the spaces dont delimit the message
# If in doubt use STATUS to echo messages
# Can be used for all sorts of messages like warnings or error messages


