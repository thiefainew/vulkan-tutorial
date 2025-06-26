cmake_minimum_required(VERSION 3.10)
project(VulkanTutorial)
set(CMAKE_CXX_STANDARD 17)

# Load local machine-specific configuration (not tracked by Git)
if(EXISTS "${CMAKE_SOURCE_DIR}/cmake-config.cmake")
    include("${CMAKE_SOURCE_DIR}/cmake-config.cmake")
endif()

# Allow overrides or defaults
set(GLFW_INCLUDE_DIR "${GLFW_INCLUDE_DIR}" CACHE PATH "GLFW include directory")
set(GLFW_LIBRARY_DIR "${GLFW_LIBRARY_DIR}" CACHE PATH "GLFW library directory")
set(VULKAN_SDK_INCLUDE_DIR "${VULKAN_SDK_INCLUDE_DIR}" CACHE PATH "Vulkan SDK include directory")
set(VULKAN_SDK_LIB_DIR "${VULKAN_SDK_LIB_DIR}" CACHE PATH "Vulkan SDK library directory")
set(GLM_INCLUDE_DIR "${GLM_INCLUDE_DIR}" CACHE PATH "GLM include directory")

# Include headers
include_directories(
    ${CMAKE_SOURCE_DIR}
    ${GLFW_INCLUDE_DIR}
    ${GLM_INCLUDE_DIR}
    ${VULKAN_SDK_INCLUDE_DIR}
)

# Link directories
link_directories(
    ${GLFW_LIBRARY_DIR}
    ${VULKAN_SDK_LIB_DIR}
)

# Executable
add_executable(VulkanTutorial main.cpp)

# Linked libraries
target_link_libraries(VulkanTutorial glfw3 vulkan-1 gdi32)