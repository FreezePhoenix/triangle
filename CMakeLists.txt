cmake_minimum_required (VERSION 3.5)
add_definitions(-std=c++20 -O3)
project("Triangle (Reworked)")

add_library(triangle STATIC
	"triangle.cpp"
)
target_include_directories(triangle PUBLIC include src)
set_property(TARGET triangle PROPERTY COMPILE_OPTIONS -DTRILIBRARY)
add_executable(triangle_exec triangle.cpp)
set_target_properties(triangle_exec PROPERTIES OUTPUT_NAME triangle)