cmake_minimum_required(VERSION 3.26)
project(Application)

add_executable(Application main.cpp)

#Include Engine Files
include_directories(${CMAKE_SOURCE_DIR}/Engine)
target_link_libraries(Application Engine)

install(TARGETS Application RUNTIME DESTINATION bin)