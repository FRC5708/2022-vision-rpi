cmake_minimum_required(VERSION 3.22.2)
project(2022-vision-rpi)

find_package(PkgConfig REQUIRED)
pkg_check_modules(gstreamer REQUIRED gstreamer-1.0)

add_executable(2022-vision main.cpp)
target_include_directories(2022-vision PUBLIC ${gstreamer_INCLUDE_DIRS})
target_link_libraries(2022-vision ${gstreamer_LIBRARIES})