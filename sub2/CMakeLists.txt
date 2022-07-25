cmake_minimum_required(VERSION 3.13)

project(sub2)

find_package(Git)
if(NOT Git_FOUND)
  message("Git not found")
endif()

file(GLOB sources ${PROJECT_SOURCE_DIR}/*.cc)
file(GLOB headers ${PROJECT_SOURCE_DIR}/*.hh)
include_directories(${PROJECT_SOURCE_DIR}/include)

add_subdirectory(../common common)
include_directories(../common)
add_executable(sub2 src/sub2.cc)
target_include_directories(sub2 PUBLIC "${CMAKE_BINARY_DIR}")
install(TARGETS sub2 DESTINATION bin)
