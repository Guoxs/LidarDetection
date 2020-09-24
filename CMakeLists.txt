cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

add_definitions(-std=c++14)

set(CXX_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS, "${CXX_FLAGS}")

project(LidarDetection)

find_package(PCL 1.8 REQUIRED)
include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

list(REMOVE_ITEM PCL_LIBRARIES "vtkproj4")


add_executable (lidarDetection src/lidarDetection.cpp src/render/render.cpp src/IO/lidarIO.cpp
        src/processPointClouds.cpp src/minbox/minBox.cpp)
target_link_libraries (lidarDetection ${PCL_LIBRARIES})




