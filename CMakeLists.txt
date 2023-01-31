cmake_minimum_required(VERSION 3.0.0)
project(CSC109CH07.31B VERSION 0.1.0)

include_directories(C:/Users/aiden/Documents/cxxtest-4.4/)
set(CXXTEST_PYTHON_TESTGEN_EXECUTABLE C:/Users/aiden/Documents/cxxtest-4.4/bin/cxxtestgen)
find_package(CxxTest REQUIRED)
enable_testing()

CXXTEST_ADD_TEST(unittest # name of the test
    runner.cpp  # THIS IS GENERATED BUT YOU NEED TO ADD IT HERE
    ${CMAKE_CURRENT_SOURCE_DIR}/Triangle.cpp  # add source files
    ${CMAKE_CURRENT_SOURCE_DIR}/TestTriangle.h  # YOUR TEST DESCRIPTION FILE
)

add_executable(CSC109CH07.31B main.cpp Triangle.h Triangle.cpp TestTriangle.h)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)