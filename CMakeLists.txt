cmake_minimum_required(VERSION 3.22.2)
project(2022-vision-rpi)

find_package(PkgConfig REQUIRED)
#include(FindPkgConfig)
pkg_check_modules(gstreamer REQUIRED gstreamer-1.0)
message("gstreamer:  ${gstreamer_INCLUDE_DIRS}")

#execute_process(
#    COMMAND pkg-config --cflags gstreamer-1.0
#    OUTPUT_VARIABLE gstreamer-1.0_INCLUDE_DIRS
#)

#message("gstreamer:  ${gstreamer-1.0_INCLUDE_DIRS}")
#set(CMAKE_CXX_FLAGS ${gstreamer-1.0_INCLUDE_DIRS})

add_executable(2022-vision main.cpp)
target_include_directories(2022-vision PUBLIC ${gstreamer_INCLUDE_DIRS})
target_link_libraries(2022-vision ${gstreamer_LIBRARIES})