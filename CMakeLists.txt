cmake_minimum_required(VERSION 3.4)
set(PROJECT_NAME examples)
project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(${PROJECT_NAME} STATIC 
	formatter_lib/formatter.cpp
	formatter_ex_lib/formatter_ex.cpp
	solver_lib/solver.cpp
)

include_directories(
	formatter_lib/_install/include
	formatter_ex_lib/_install/include
	solver_lib/_install/include
)
link_directories(
	formatter_ex_lib/_install/lib
	solver_lib/_install/lib
)

add_executable(hello_world_ex hello_world_application/hello_world.cpp)
add_executable(solver_ex solver_application/equation.cpp)

target_link_libraries(hello_world_ex ${PROJECT_NAME})
target_link_libraries(solver_ex ${PROJECT_NAME})
