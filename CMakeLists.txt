cmake_minimum_required(VERSION 3.30)
project(BasicWindow)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED YES)
set(CMAKE_CXX_EXTENSIONS OFF)


add_library(raylib STATIC IMPORTED)
set_target_properties(raylib PROPERTIES IMPORTED_LOCATION ${CMAKE_SOURCE_DIR}/lib/libraylib.a)

include_directories(${CMAKE_SOURCE_DIR}/include)

add_executable(good src/main.cpp)
target_link_libraries(good raylib winmm opengl32 m pthread)