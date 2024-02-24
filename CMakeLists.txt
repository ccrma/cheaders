cmake_minimum_required(VERSION 3.12)
project(cheaders VERSION 1.0)

# Define the library target
add_library(cheaders INTERFACE)

# Set include directories so that users can #include <header.h>
target_include_directories(cheaders INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Installation instructions
install(
    TARGETS cheaders
    EXPORT cheadersTargets
)

install(
    DIRECTORY include/
    DESTINATION include
)

install(
    EXPORT cheadersTargets
    FILE cheadersTargets.cmake
    DESTINATION lib/cmake/cheaders
)
