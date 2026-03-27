cmake_minimum_required(VERSION 3.10)
project(MyCppProject)

set(CMAKE_CXX_STANDARD 17)

# Main Executable
add_executable(my_app src/main.cpp)

# Enable Testing
enable_testing()
add_executable(run_tests tests/test_main.cpp)
add_test(NAME AllTests COMMAND run_tests)