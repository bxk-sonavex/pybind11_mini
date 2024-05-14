cmake_minimum_required(VERSION 3.25)
project(cmake_example)

add_library(lib STATIC src/lib/lib.cpp)
set_target_properties(lib PROPERTIES POSITION_INDEPENDENT_CODE ON)

add_subdirectory(pybind11)
pybind11_add_module(cmake_example src/binder.cpp)
target_link_libraries(cmake_example PRIVATE lib)
