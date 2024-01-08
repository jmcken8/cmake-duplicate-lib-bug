add_library(a a.cpp)
add_library(a ALIAS a)
add_library(b b.cpp)

add_executable(e)

target_link_libraries(e PUBLIC a)
target_link_libraries(e PUBLIC b)
target_link_libraries(b PUBLIC a::a)
