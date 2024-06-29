cmake_minimum_required(VERSION 3.16)

project( cmake_base     VERSION 0.0.1
                        DESCRIPTION "CMAKE BASE"
                        )

message(STATUS "Project : ${PROJECT_NAME}")

#CHECK FOR REQUIREMENTS

#CXX SETUP INTERFACE
add_library( cxx_setup
    INTERFACE)

if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    target_compile_options( cxx_setup
    INTERFACE -Wall -Werror -Wextra -Weffc++ -g)
else()
    target_compile_options( cxx_setup
    INTERFACE -Wall -Werror -Wextra -Weffc++ -O3)
endif()

target_compile_features( cxx_setup
    INTERFACE cxx_std_20)
target_include_directories( cxx_setup
    INTERFACE ${PROJECT_SOURCE_DIR})

#SUBDIRS
add_subdirectory(libs)
add_subdirectory(src)

