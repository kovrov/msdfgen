cmake_minimum_required(VERSION 3.1)

project(msdfgen-core)

file(GLOB SOURCES *.cpp *.h)

add_library(${PROJECT_NAME} ${SOURCES})
set_property(TARGET ${EXECUTABLE_NAME} PROPERTY CXX_STANDARD 14)
add_definitions(-DMSDFGEN_USE_CPP11)

target_link_libraries(${PROJECT_NAME} ${FREETYPE_LIBRARIES}  ${HF_LIBRARIES})
