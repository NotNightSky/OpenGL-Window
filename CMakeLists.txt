cmake_minimum_required(VERSION 4.3)
project(window)

set(CMAKE_CXX_STANDARD 20)

find_package(SDL3 REQUIRED CONFIG REQUIRED COMPONENTS SDL3-shared)

find_package(OpenGL REQUIRED)

include_directories( SYSTEM "/include" )

add_executable(window src/main.cpp src/gl.c)

target_link_libraries(window PRIVATE OpenGL::GL SDL3::SDL3)
