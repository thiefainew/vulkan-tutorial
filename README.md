# Vulkan Tutorial Project

⚠️ This project is currently set up for **Windows** using **MinGW-w64**, GLFW, GLM, and the Vulkan SDK.

Here is the minimal setup using CMake.

## Requirements

- [GLFW](https://www.glfw.org/) (headers and MinGW-compatible `.a` libraries)
- [GLM](https://github.com/g-truc/glm) (header-only)
- [Vulkan SDK](https://vulkan.lunarg.com/)
- [CMake](https://cmake.org/)
- [MinGW-w64](https://winlibs.com/) (with g++)

## Setup

1. Create a `cmake-config.cmake` file in the project root (example paths, adjust with yours):

```cmake
set(GLFW_INCLUDE_DIR "C:/libs/glfw/include")
set(GLFW_LIBRARY_DIR "C:/libs/glfw/lib-mingw-w64")
set(VULKAN_SDK_INCLUDE_DIR "C:/VulkanSDK/1.4.313.2/Include")
set(VULKAN_SDK_LIB_DIR "C:/VulkanSDK/1.4.313.2/Lib")
set(GLM_INCLUDE_DIR "C:/libs/glm")
````

> This file defines your local paths and should **not be committed**.

2. Build the project:

```sh
cmake -B build
cmake --build build
```

3. Run the executable:

```sh
./build/VulkanTutorial.exe
```