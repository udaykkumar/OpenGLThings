
# Minimum CMake
cmake_minimum_required (VERSION 2.8.1)
project(OpenGLThings)
set(CMAKE_PROJECT_VERSION       "0")
set(CMAKE_PROJECT_VERSION_MAJOR "0")
set(CMAKE_PROJECT_VERSION_MINOR "0")
set(CMAKE_PROJECT_VERSION_PATCH "0")



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


SET(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} ${PROJECT_COMPILER_FLAGS} ")
SET(CMAKE_EXE_LINKER_FLAGS  "${CMAKE_EXE_LINKER_FLAGS} ${PROJECT_LINK_FLAGS}")


add_subdirectory(src)



