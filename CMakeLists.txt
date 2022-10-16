cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(hello VERSION 1.0)

add_subdirectory(blah)
find_library(ZLIB z REQUIRED)
set(ZLIB_INCLUDE_DIR /usr/include)
# find_library(ZLIB libz.a REQUIRED PATHS /usr/lib/libz.a)
# file(GLOB_RECURSE SRC_FILES CONFIGURE_DEPENDS src/*.cpp)

add_executable(hello main.cpp)
target_include_directories(hello PUBLIC ${ZLIB_INCLUDE_DIR})
target_link_libraries(hello PUBLIC blah ${ZLIB})
