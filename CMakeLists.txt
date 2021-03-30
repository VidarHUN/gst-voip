cmake_minimum_required(VERSION 3.10)

# project name
project(gst-voip)

find_package(PkgConfig) # Finding pkg-config is a helper tool

# using pkg-config to getting Gstreamer
pkg_check_modules(GSTREAMER REQUIRED gstreamer-1.0)

# including GStreamer header files directory
include_directories(
    ${GLIB_INCLUDE_DIRS}
    ${GSTREAMER_INCLUDE_DIRS}
)

# linking GStreamer library directory
link_directories(
    ${GLIB_LIBRARY_DIRS}
    ${GSTREAMER_LIBRARY_DIRS}
)

# executable
add_executable(${PROJECT_NAME} gst-voip.c)

# linking GStreamer library with target executable
target_link_libraries(${PROJECT_NAME} ${GSTREAMER_LIBRARIES})
