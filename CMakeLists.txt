
cmake_minimum_required(VERSION 3.5)

project(hello_cmake)

add_library(
  Glad STATIC
  "glad/src/gl.c")

target_include_directories(Glad PUBLIC "glad/include")

add_executable(${PROJECT_NAME} src/glfw_test.cpp)

# find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

target_include_directories(${PROJECT_NAME} PUBLIC ${OPENGL_INCLUDE_DIR})

target_include_directories(${PROJECT_NAME} PUBLIC /usr/local/include)

target_link_libraries(${PROJECT_NAME} PUBLIC
  ${OPENGL_LIBRARIES}
  Glad
  glfw)
