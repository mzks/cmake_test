cmake_minimum_required(VERSION 3.13)

project(sub1)
file(GLOB sources ${PROJECT_SOURCE_DIR}/src/*.cc)
file(GLOB headers ${PROJECT_SOURCE_DIR}/include/*.hh)
include_directories(${PROJECT_SOURCE_DIR}/include)
set(CMAKE_INSTALL_PREFIX .)

add_executable(sub1 src/sub1.cc)
install(TARGETS sub1 DESTINATION bin)
