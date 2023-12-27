cmake_minimum_required(VERSION 3.10)
project(OOP_MAI)
set(CMAKE_CXX_STANDARD 20)

add_subdirectory(googletest)

add_executable(OOP_MAI src/main.cpp src/functions.cpp)
add_executable(tests tests/tests.cpp src/functions.cpp)

target_include_directories(OOP_MAI PRIVATE src)
target_include_directories(tests PRIVATE src)

target_link_libraries(tests PRIVATE GTest::gtest_main)

include(GoogleTest)
gtest_discover_tests(tests)
