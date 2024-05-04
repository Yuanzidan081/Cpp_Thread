cmake_minimum_required (VERSION 3.0)
project(CPP_THREAD)


set(CMAKE_CXX_STANDARD_VERSION 17)
set(CMAKE_CXX_STANDARD_REQUIRED_VERSION ON)

if (NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Debug CACHE STRING "Choose the type of build (Debug or Release)" FORCE)
endif(NOT CMAKE_BUILD_TYPE)

if (WIN32)
  set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)
endif(WIN32)

message("the source directory is ${CMAKE_SOURCE_DIR}")
message("the binary directory is ${CMAKE_BINARY_DIR}")

set (chapter
Cpp_Thread_01_1)

file(GLOB SOURCE
    "src/Cpp_Thread_01_1/*.h"
    "src/Cpp_Thread_01_1/*.cpp")
set(NAME "${chapter}")
add_executable(${NAME} ${SOURCE})

if (MSVC)
    target_compile_options(${NAME} PRIVATE /std:c++17 /MP)
    target_link_options(${NAME} PUBLIC /ignore:4099)
endif(MSVC)

