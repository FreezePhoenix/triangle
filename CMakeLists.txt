cmake_minimum_required (VERSION 3.5)
project("Triangle (Reworked)")

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG}")

add_library(Triangle_HEADERS INTERFACE)

add_library(Triangle STATIC
	"src/triangle.cpp"
)

target_include_directories(Triangle_HEADERS INTERFACE include)

target_link_libraries(Triangle Triangle_HEADERS)
