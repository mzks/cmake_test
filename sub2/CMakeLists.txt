cmake_minimum_required(VERSION 3.13)

project(sub2)
file(GLOB sources ${PROJECT_SOURCE_DIR}/src/*.cc)
file(GLOB headers ${PROJECT_SOURCE_DIR}/include/*.hh)
set(CMAKE_INSTALL_PREFIX .)

add_executable(sub2 src/sub2.cc)
install(TARGETS sub2 DESTINATION bin)
