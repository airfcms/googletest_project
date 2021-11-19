cmake_minimum_required (VERSION 3.8)

project (googletest_project) 

set(GOOGLETEST_PROJECT_INCLUDE_DIRS ${CMAKE_CURRENT_SOURCE_DIR}/src CACHE STRING "Project include dirs")

include_directories( ${GOOGLETEST_PROJECT_INCLUDE_DIRS}) 

add_library(googletest_project ${CMAKE_CURRENT_SOURCE_DIR}/src/component1.cc)

add_subdirectory( ${CMAKE_CURRENT_SOURCE_DIR}/tests )
