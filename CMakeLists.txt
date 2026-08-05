# CMake 3.28 is strictly required for native C++20 modules support
cmake_minimum_required(VERSION 3.28)

project(ModuleExample CXX)

# Enforce C++20 standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Create our executable and add the standard main.cpp
add_executable(my_app main.cpp)

# Explicitly tell CMake which files are C++ modules
target_sources(my_app
    PRIVATE
    FILE_SET CXX_MODULES FILES src/game_tree.cppm
)