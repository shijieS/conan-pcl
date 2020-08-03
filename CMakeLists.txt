cmake_minimum_required(VERSION 3.1.0)
project(cmake_wrapper)

if(EXISTS "${CMAKE_BINARY_DIR}/conanbuildinfo.cmake")
  include("${CMAKE_BINARY_DIR}/conanbuildinfo.cmake")
else()
  include(conanbuildinfo.cmake)
endif()
conan_basic_setup()

SET(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CONAN_FLANN_ROOT})
SET(CMAKE_INCLUDE_PATH ${CMAKE_INCLUDE_PATH} ${CONAN_INCLUDE_DIRS})

add_subdirectory("source_subfolder")
