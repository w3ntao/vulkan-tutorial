# Set the minimum version of CMake that can be used
# To find the cmake version run
# $ cmake --version
cmake_minimum_required(VERSION 3.20)

# Set the project name
project(vulkan_tutorial LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 17)

find_package(Vulkan REQUIRED)
find_package(glm REQUIRED)

add_subdirectory("ext/glfw")
include_directories("${GLFW_SOURCE_DIR}/deps")
link_libraries(glfw)

# Add an executable
add_executable(vk_tutorial main.cpp)

#target_link_libraries(vk_tutorial glm::glm)
target_link_libraries(vk_tutorial glfw ${GLFW_LIBRARIES} Vulkan::Vulkan glm::glm)

# sudo apt install libxkbcommon-dev
