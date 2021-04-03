
# Minimum CMake
cmake_minimum_required (VERSION 2.8.1)
project(OpenGLThings)
set(CMAKE_PROJECT_VERSION       "0")
set(CMAKE_PROJECT_VERSION_MAJOR "0")
set(CMAKE_PROJECT_VERSION_MINOR "0")
set(CMAKE_PROJECT_VERSION_PATCH "0")
enable_testing()


include(cmake/GitUtils.cmake)
include(cmake/FindGLFW3.cmake)
#include(cmake/FindGLEW.cmake)

find_package(GLEW REQUIRED)
find_package(glfw3 REQUIRED)


if( APPLE )
  message( "-- Detected Apple/MacOS ( include graphics Support ) "  )
  include_directories(${GLFW3_INCLUDE_DIR})
  add_definitions(-DGL_SILENCE_DEPRECATION)
else()
  message( "-- As long as it Ubuntu ( include graphics Support )  "  )
  include_directories(${GLFW3_INCLUDE_DIR})
endif()

#Boost and Family
#set(Boost_USE_STATIC_LIBS ON)
#find_package(Boost  COMPONENTS unit_test_framework  REQUIRED )


#Project Compiler Arguments
#if(APPLE)
#   message( "-- Detected Apple/MacOS ( Skipping Coverage ) " )
#   SET(PROJECT_COMPILER_FLAGS "-Wall -std=c++17 ")
#else()
#   SET(PROJECT_COMPILER_FLAGS "-Wall -fprofile-arcs -ftest-coverage -std=c++17 ")
#   SET(PROJECT_LINK_FLAGS    "-lgcov")
#endif()



SET(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} ${PROJECT_COMPILER_FLAGS} ")
SET(CMAKE_EXE_LINKER_FLAGS  "${CMAKE_EXE_LINKER_FLAGS} ${PROJECT_LINK_FLAGS}")


add_subdirectory(src)



