add_library(somelib SHARED somelib.cpp)

target_include_directories( somelib
    INTERFACE
    ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(somelib PUBLIC cxx_setup)