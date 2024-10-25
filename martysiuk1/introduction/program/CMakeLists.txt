cmake_minimum_required(VERSION 3.4)

project(Program)

# Set a set of source files in your SOURCE_FILES variable project
set(SOURCE_FILES src/main.cpp)

# Include the above set of files to build an executable program Program
add_executable(Program ${SOURCE_FILES})

# Defining dependencies between Program and MathLibrary projects
target_link_libraries(Program MathLibrary)

# Include the include directory of the Program subproject to the global list. This way, every other subproject will "see" this directory
target_include_directories(Program PUBLIC include)