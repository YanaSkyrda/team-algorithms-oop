project(tests)

set(CMAKE_CXX_STANDARD 17)

set(SRC_LIST
        main.cpp
        Tests.cpp)

add_executable(${PROJECT_NAME} ${SRC_LIST})
target_link_libraries(${PROJECT_NAME} PRIVATE sqlite3)

add_test(NAME AllTests COMMAND tests)
