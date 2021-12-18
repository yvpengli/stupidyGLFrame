cmake_minimum_required(VERSION 3.8)

set(CMAKE_TOOLCHAIN_FILE D:/vcpkg/scripts/buildsystems/vcpkg.cmake
  CACHE STRING "Vcpkg toolchain file")

message(VCPKG_ROOT = "${CMAKE_TOOLCHAIN_FILE}")

project(OpenGL)

find_package(GLEW CONFIG REQUIRED)
find_package(glfw3 CONFIG REQUIRED)
find_package(glm CONFIG REQUIRED)

add_executable(OpenGL "main.cpp")

target_link_libraries(OpenGL PRIVATE GLEW::GLEW)
target_link_libraries(OpenGL PRIVATE glfw)
target_link_libraries(OpenGL PRIVATE glm::glm)
