cmake_minimum_required(VERSION 3.10)
project(clox C)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wextra -Wno-unused-parameter -g")

include_directories(include)

file(GLOB SRCS "src/*.c")

add_executable(clox ${SRCS})

if(UNIX AND NOT APPLE)
    target_link_libraries(clox PRIVATE m)
endif()

set_property(TARGET clox PROPERTY RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin")
