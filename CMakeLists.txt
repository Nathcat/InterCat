cmake_minimum_required(VERSION 3.31.6)

project(InterCat)

add_subdirectory(glfw)
add_subdirectory(glm)

add_library(InterCat SHARED
  src/say_hello.cpp
)

target_include_directories(InterCat PUBLIC include)
target_link_libraries(InterCat glfw glm::glm)

add_subdirectory(InterCat_Test)

target_link_libraries(InterCat_Test PUBLIC InterCat)
