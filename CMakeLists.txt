cmake_minimum_required(VERSION 3.20)
project(TestGame)
set(CMAKE_CXX_STANDARD 17)

add_executable(TestGame src/main.cpp )

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)

add_subdirectory(external/glfw)
target_link_libraries(${PROJECT_NAME} glfw)

add_subdirectory(external/glad/cmake glad_cmake)
glad_add_library(glad_gl_core_mx_33 STATIC LOADER API gl:core=4.6)
target_link_libraries(${PROJECT_NAME} glad_gl_core_mx_33)
