cmake_minimum_required(VERSION 3.1)

project(msdfgen)

add_subdirectory(core)
add_subdirectory(ext)

add_executable(${PROJECT_NAME} main.cpp)
set_property(TARGET ${EXECUTABLE_NAME} PROPERTY CXX_STANDARD 14)
add_definitions(-DMSDFGEN_USE_CPP11 -DMSDFGEN_STANDALONE)

target_link_libraries(${PROJECT_NAME} msdfgen-ext)
