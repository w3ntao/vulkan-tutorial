cmake_minimum_required(VERSION 3.20)

project(vulkan_tutorial LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 17)

find_package(Vulkan REQUIRED)
find_package(glm REQUIRED)
find_package(glfw3 REQUIRED)

add_executable(vk_tutorial main.cpp)

target_link_libraries(vk_tutorial Vulkan::Vulkan glfw ${GLFW_LIBRARIES} glm::glm)
