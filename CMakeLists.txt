cmake_minimum_required(VERSION 3.15)
project(ConanCmakeDemo)

set(CMAKE_CXX_STANDARD 17)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)

conan_basic_setup()

#### target
add_executable(demo demo.cpp)
target_link_libraries(demo ${CONAN_LIBS})


##### unit test
enable_testing()
SET(TEST_SRC test/gtest.cpp
        test/condition_test.cpp
        )

add_executable(runUnitTests ${TEST_SRC})
TARGET_LINK_LIBRARIES(runUnitTests ${CONAN_LIBS})
