cmake_minimum_required(VERSION 3.1)
project(test_package)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(Thrift CONFIG REQUIRED)

add_executable(${PROJECT_NAME}
    calculator_constants.cpp
    calculator_types.cpp
    Calculator.cpp
    test_package.cpp
)
target_link_libraries(${PROJECT_NAME} thrift::thrift)
set_target_properties(${PROJECT_NAME} PROPERTIES CXX_STANDARD 11)
