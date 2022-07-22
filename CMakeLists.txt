cmake_minimum_required(VERSION 3.13)
enable_testing()


# Disable build at top-level of sources
get_filename_component(srcdir "${CMAKE_SOURCE_DIR}" REALPATH)
get_filename_component(bindir "${CMAKE_BINARY_DIR}" REALPATH)
if("${srcdir}" STREQUAL "${bindir}")
    message("Do not build on the top level source.")
    message(FATAL_ERROR "Hint: git clean -d -f -x -n")
endif()

project(cmake_test)

IF (APPLE)
   SET(CMAKE_INSTALL_RPATH_USE_LINK_PATH ON)
ENDIF()

include_directories(common)
add_subdirectory(common)

add_subdirectory(sub1)
add_subdirectory(sub2)

add_custom_target(alltar DEPENDS common sub1 sub2)


## Tests
add_test(NAME dummy COMMAND pwd)
