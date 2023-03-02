cmake_minimum_required( VERSION 3.1 )

project(CMakeGLFW)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_executable(app main.cpp)

add_subdirectory(../lib/glfw-3.3.8 PATH_TO_GLFW)

target_link_libraries(app glfw)

find_package(OpenGL REQUIRED)

target_link_libraries(app OpenGL::GL)