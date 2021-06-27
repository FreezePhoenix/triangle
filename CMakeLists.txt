cmake_minimum_required (VERSION 3.5)
project(triangle)
add_definitions(-std=c++20 -O4)

add_library(triangle STATIC triangle.cpp)
add_executable(triangle_exec triangle.cpp)
set_target_properties(triangle_exec PROPERTIES OUTPUT_NAME triangle)
set_property(TARGET triangle PROPERTY COMPILE_OPTIONS -DTRILIBRARY)