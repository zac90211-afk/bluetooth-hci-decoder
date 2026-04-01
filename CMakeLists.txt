cmake_minimum_required (VERSION 2.6)

project(hci-decoder)
add_subdirectory( btsnoop-decoder )

find_package(Threads REQUIRED)

option(BUILD_32BIT "Build 32-bit binary" OFF)

if(MSVC)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /W3")
elseif(UNIX)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -std=c++11")
    if(BUILD_32BIT)
        set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -m32")
    endif()
endif()

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
        Threads::Threads
)

target_link_libraries(
        bthci
        btsnoop_static
        Threads::Threads
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
        Threads::Threads
)