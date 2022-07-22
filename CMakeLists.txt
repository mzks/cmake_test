cmake_minimum_required(VERSION 3.13)

project(cmake_test)
include(FetchContent)
file(GLOB sources ${PROJECT_SOURCE_DIR}/src/*.cc)
file(GLOB headers ${PROJECT_SOURCE_DIR}/include/*.hh)
include_directories(${PROJECT_SOURCE_DIR}/include)

find_package(Git)
if(NOT Git_FOUND)
  message("Git not found")
endif()

include_directories(common)
add_subdirectory(common)
add_subdirectory(sub1)
add_subdirectory(sub2)

add_custom_target(alltar DEPENDS common sub1 sub2)
