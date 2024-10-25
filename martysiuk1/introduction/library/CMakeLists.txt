cmake_minimum_required(VERSION 3.4)
project(MathLibrary)

set(SOURCE_FILES
    src/math_helpers.cpp
)
# Create a STATIC, SHARED or MODULE library from the indicated sources
add_library(MathLibrary ${SOURCE_FILES})

target_include_directories(MathLibrary PUBLIC include)