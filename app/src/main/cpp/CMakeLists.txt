cmake_minimum_required(VERSION 3.22.1)
project(native_lib)

add_library(native-lib SHARED
    native-lib.cpp
)

find_library(log-lib log)

# To avoid libc++abi unresolved in some environments
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Use NDK provided STL
target_link_libraries(native-lib ${log-lib})
