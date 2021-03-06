cmake_minimum_required(VERSION 3.9)
project(team_algorithms_oop)

set(CMAKE_CXX_STANDARD 17)

set(TESTS_DIR ${CMAKE_SOURCE_DIR}/tests)
set(SRC_DIR ${CMAKE_SOURCE_DIR}/src)
set(DEPS_DIR ${CMAKE_SOURCE_DIR}/deps)
set(INCLUDE_DIR ${CMAKE_SOURCE_DIR}/include)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

include_directories(${SRC_DIR})
include_directories(${DEPS_DIR})
include_directories(${DEPS_DIR}/cereal/include)
include_directories(${INCLUDE_DIR})

set(LIB_NAME ${PROJECT_NAME}core)

option(ENABLE_TESTS "Build tests for project" ON)
if(ENABLE_TESTS)
    enable_testing()
    add_subdirectory(${TESTS_DIR})
endif()

add_executable(main main.cpp)
target_link_libraries(main PRIVATE sqlite3)




