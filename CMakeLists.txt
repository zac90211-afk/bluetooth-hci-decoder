cmake_minimum_required (VERSION 2.6)

project(hci-decoder)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if(UNIX)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")
endif()

file(
        GLOB_RECURSE
        btsnoop_source_files
        btsnoop-decoder/src/*
        btsnoop-decoder/include/*
)

add_library(
        btsnoop_static
        STATIC
        ${btsnoop_source_files}
)

add_library(
        btsnoop
        SHARED
        ${btsnoop_source_files}
)

target_include_directories(
        btsnoop_static
        PUBLIC
        btsnoop-decoder/include
        btsnoop-decoder/test/include
)

target_include_directories(
        btsnoop
        PUBLIC
        btsnoop-decoder/include
        btsnoop-decoder/test/include
)

file(
        GLOB_RECURSE
        btsnoop_test_files
        btsnoop-decoder/test/src/*
        btsnoop-decoder/test/include/*
)

add_executable(
        btsnoop-test
        ${btsnoop_test_files}
)

target_include_directories(
        btsnoop-test BEFORE PRIVATE
        btsnoop-decoder/test/include
        btsnoop-decoder/include
)

target_link_libraries(
        btsnoop-test
        btsnoop
        pthread
)

# Avoid forcing 32-bit builds when 32-bit toolchains are unavailable.

set(LIBRARY_OUTPUT_PATH lib/${CMAKE_BUILD_TYPE})
set(EXECUTABLE_OUTPUT_PATH bin/${CMAKE_BUILD_TYPE})

include_directories(
    include
    btsnoop-decoder/include
    test/include
)

file(
        GLOB_RECURSE
        source_files
        src/*
        include/*
)

add_library(
        bthci_static
        STATIC
        ${source_files}
)

add_library(
        bthci
        SHARED
        ${source_files}
)

target_link_libraries(
        bthci_static
        btsnoop_static
        pthread
)

target_link_libraries(
        bthci
        btsnoop_static
        pthread
)

# test build
file(
        GLOB_RECURSE
        source_test_files
        test/src/*
        test/include/*
)

add_executable(
        bthci-test
        ${source_test_files}
)

target_link_libraries(
        bthci-test
        bthci_static
        btsnoop_static
        pthread
)
