cmake_minimum_required(VERSION 3.13)

project(cmake_test)

add_subdirectory(sub1)
#add_subdirectory(sub2)

add_custom_target(alltar DEPENDS sub1 sub2)
