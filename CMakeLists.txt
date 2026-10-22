cmake_minimum_required(VERSION 4.3)
project(window C)

set(CMAKE_C_STANDARD 17)

find_package(SDL3 REQUIRED CONFIG REQUIRED COMPONENTS SDL3-shared)

find_package(OpenGL REQUIRED)

include_directories( SYSTEM "include/" )

add_executable(window src/main.c src/gl.c)

target_link_libraries(window PRIVATE OpenGL::GL SDL3::SDL3)

file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/src/shaders"
        DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/src")

