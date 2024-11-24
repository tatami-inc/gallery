cmake_minimum_required(VERSION 3.24)

project(tatami_gallery
    VERSION 0.1.0
    DESCRIPTION "Examples of tatami use cases"
    LANGUAGES CXX)

include(FetchContent)

FetchContent_Declare(
  tatami
  GIT_REPOSITORY https://github.com/tatami-inc/tatami
  GIT_TAG master # ^0.3.0
)

FetchContent_MakeAvailable(tatami)

#########################################
# Building the char2double demonstration.

add_executable(
    char2double
    src/char2double.cpp
)

target_link_libraries(
    char2double 
    tatami
)

#########################################
# Building the colsums demonstration.

add_executable(
    colsums 
    src/colsums.cpp
)

target_link_libraries(
    colsums 
    tatami
)

#########################################
# Building the OpenMP demonstration.

add_executable(
    parallel 
    src/parallel.cpp
)

find_package(OpenMP)
if(OpenMP_CXX_FOUND)
    target_link_libraries(parallel PUBLIC OpenMP::OpenMP_CXX)
endif()

target_link_libraries(
    parallel 
    PUBLIC
    tatami
)

#########################################
# Checking sparse workspace performance.

add_executable(
    sparse_extractor 
    src/sparse_extractor.cpp
)

target_link_libraries(
    sparse_extractor
    tatami
)
