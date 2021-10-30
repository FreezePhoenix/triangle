cmake_minimum_required (VERSION 3.5)
add_definitions(-std=c++20 -O3)
project("Triangle (Reworked)")

add_library(Triangle_HEADERS INTERFACE)
target_include_directories(Triangle_HEADERS INTERFACE include)

add_library(Triangle STATIC
	"triangle.cpp"
)

set_property(TARGET Triangle PROPERTY COMPILE_OPTIONS -DTRILIBRARY)
add_executable(triangle_exec triangle.cpp)
add_executable(showme showme.c)
target_link_libraries(showme PUBLIC X11)
target_link_libraries(Triangle Triangle_HEADERS)
set_target_properties(triangle_exec PROPERTIES OUTPUT_NAME triangle)
set_property(TARGET triangle_exec PROPERTY LINK_OPTIONS -static)