cmake_minimum_required(VERSION 3.10)
project(MyCppProject)

set(CMAKE_CXX_STANDARD 17)

add_library(core STATIC
    src/add.cpp
)
target_include_directories(core PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/src)

# Main Executable
add_executable(my_app src/main.cpp)
target_link_libraries(my_app PRIVATE core)

# Enable Testing
enable_testing()
add_executable(run_tests tests/test_main.cpp)
target_link_libraries(run_tests PRIVATE core)

# Use the full path so this works with multi-config generators
add_test(NAME AllTests COMMAND $<TARGET_FILE:run_tests>)