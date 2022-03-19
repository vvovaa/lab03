cmake_minimum_required(VERSION 3.4)
project(formatter)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(formatter STATIC formatter.cpp)
include_directories(.)

# SET( APP_EXE test_lib )
# add_executable(${APP_EXE} main.cpp)
# target_link_libraries(${APP_EXE} print)
