cmake_minimum_required(VERSION 3.4)
set(PROJECT_NAME formatter_ex)
project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(${PROJECT_NAME} STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex.cpp)
target_include_directories(${PROJECT_NAME} PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib/_install/include>
  $<INSTALL_INTERFACE:include>
)
target_link_directories(${PROJECT_NAME} PUBLIC 
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib/_install/lib>
  $<INSTALL_INTERFACE:lib>
)

install(TARGETS ${PROJECT_NAME}
    EXPORT formatter-config
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
)

install(FILES ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex.h DESTINATION include)
install(EXPORT formatter-config DESTINATION cmake)
