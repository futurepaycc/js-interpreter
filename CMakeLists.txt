cmake_minimum_required (VERSION 2.8)
project(javascript-interpreter)

set (CMAKE_CXX_STANDARD 11)
include_directories (include)
aux_source_directory (src SRC)
add_library (main "${SRC}")
add_executable (node src/main.cpp)
add_executable (lexer src/test-lexer.cpp)
add_executable (parser src/test-parser.cpp)
target_link_libraries (lexer main)
target_link_libraries (parser main)
target_link_libraries (node main)