# Minimum cmake version required to build this project
cmake_minimum_required(VERSION 3.4)

# Development platform configuration parameters and flags compiler
set(CMAKE_CXX_COMPILER g++) # g++ as C++ compiler
set(CMAKE_C_COMPILER gcc) # gcc as C compiler
set(CMAKE_CXX_STANDARD 17) # C++ 17 standard, without this parameter g++ will use the default value. For g++ since version 8 it is C++14
set(CMAKE_CXX_STANDARD_REQUIRED ON) # The C++ standard specified above is required

# Debug profile and max debug info level g3 and debug info format to dwarf-4 (must be gdb version 7).
# BUILD_TYPE can be set to:
#empty
#Debug
#Release
#RelWithDebInfo
#MinSizeRel

# Debug flags generating debugger information have been additionally set
set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_CXX_FLAGS_DEBUG "-g3 -gdwarf-4")  # Set the project name and language to C++
project(IntroductionProject)
enable_language(CXX) 
# In a special file compile_commands.json you can see all compiler operations with parameters, 
set(CMAKE_EXPORT_COMPILE_COMMANDS ON) 
set(CMAKE_VERBOSE_MAKEFILE TRUE)

# Include a subproject located in the program subdirectory. There must be a CMakeLists.txt file in it
add_subdirectory(program)

add_subdirectory(library)

# Enabling tests causes the test target to appear in Makefiles
enable_testing()