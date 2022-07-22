cmake_minimum_required(VERSION 3.13)


execute_process(COMMAND
  "${GIT_EXECUTABLE}" describe --match=NeVeRmAtCh --always --abbrev=40 --dirty
  WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}"
  OUTPUT_VARIABLE GIT_SHA1
  OUTPUT_STRIP_TRAILING_WHITESPACE)

project(common)
add_custom_target(common)

# generate common.hh
configure_file("${CMAKE_CURRENT_SOURCE_DIR}/common.hh.in" "${CMAKE_CURRENT_SOURCE_DIR}/common.hh" @ONLY)

list(APPEND SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/common.hh")

