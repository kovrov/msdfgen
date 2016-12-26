cmake_minimum_required(VERSION 3.1)

# Multi-channel signed distance field generator
project(msdfgen-ext)

# freetype
find_package(Freetype REQUIRED)
include_directories(${FREETYPE_INCLUDE_DIRS})

find_package(PkgConfig REQUIRED)
pkg_check_modules(TINYXML tinyxml2)
include_directories(${TINYXML_INCLUDE_DIRS})

file(GLOB SOURCES *.cpp *.h)

add_library(${PROJECT_NAME} ${SOURCES} ../lib/lodepng.cpp)
set_property(TARGET ${EXECUTABLE_NAME} PROPERTY CXX_STANDARD 14)
add_definitions(-DMSDFGEN_USE_CPP11)

target_link_libraries(${PROJECT_NAME} ${FREETYPE_LIBRARIES} ${TINYXML_LIBRARIES} msdfgen-core)
