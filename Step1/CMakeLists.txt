# TODO1: Set the minimum required version of CMake to be 3.23
cmake_minimum_required(VERSION 3.23)

# TODO2: Create a project named Tutorial
project(Tutorial)

# TODO3: Add an executable target called Tutorial to the project
add_executable(Tutorial)

# TODO4: Add the Tutorial/Tutorial.cxx source file to the Tutorial target
target_sources(Tutorial 
                PRIVATE 
                Tutorial/Tutorial.cxx)

# TODO7: Add the MathFunctions library as a linked dependency
#        to the Tutorial target
add_library(MathFunctions)

target_sources(MathFunctions
                PRIVATE 
                    MathFunctions/MathFunctions.cxx
                PUBLIC 
                    FILE_SET HEADERS
                    BASE_DIRS 
                        MathFunctions
                    FILES
                        MathFunctions/MathFunctions.h)

target_link_libraries(Tutorial 
                        PRIVATE
                            MathFunctions)

# TODO11: Add the Tutorial subdirectory to the project

# TODO13: Add the MathFunctions subdirectory to the project
