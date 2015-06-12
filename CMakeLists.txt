cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_FLAGS "-std=c++0x")

find_package(Qt5Core)

add_library(commander
	Commander.h
	Commander.cpp
)

add_executable(example
	CommanderExample.cpp
)

target_include_directories(commander PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(commander PUBLIC Qt5::Core)

target_include_directories(example PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(example PUBLIC commander Qt5::Core)
