cmake_minimum_required(VERSION 3.27)
project(test)

add_library(a a.cpp)
add_library(a::a ALIAS a)
add_library(b b.cpp)

add_executable(e e.cpp)

target_link_libraries(e PUBLIC a)
target_link_libraries(e PUBLIC b)
target_link_libraries(b PUBLIC a::a)

target_link_options(e PUBLIC -Wl,-fatal_warnings)
