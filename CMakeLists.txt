cmake_minimum_required(VERSION 3.15)
project(duilib)

add_compile_options("$<$<C_COMPILER_ID:MSVC>:/utf-8>")
add_compile_options("$<$<CXX_COMPILER_ID:MSVC>:/utf-8>")

add_subdirectory(gtkduilib)
add_subdirectory(360Demo)
add_subdirectory(qyplayer)