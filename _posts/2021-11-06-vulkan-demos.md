---
layout: post
title: "Vulkan Demos"
author: "Jooho Jeong"
categories: project
tags: [projects.graphics]
image: n_body_simulation.gif
excerpt_separator: <!--more-->
---

This is a real-time 3D rendering application using C++ / Vulkan / GLSL.
<!--more-->

## Developing Environments
* OS: Windows 10
* IDE: Visual Studio 2019
* GPU: RTX 2060 SUPER

Successful build on other environments is not guaranteed.

## Third Party
* [tinyobjloader](https://github.com/tinyobjloader/tinyobjloader)
* [stb collection](https://github.com/nothings/stb)
* [imgui](https://github.com/ocornut/imgui)

## References
A lot of code were based on these great resources:
* [Vulkan tutorial by Alexander Overvoorde](https://vulkan-tutorial.com/Introduction)
* [Vulkan samples by Sascha Willems](https://github.com/SaschaWillems/Vulkan)
* [Nvpro Core from NVIDIA DesignWorks Samples](https://github.com/nvpro-samples/nvpro_core)
* [LearnOpenGL by Joey de Vries](https://learnopengl.com)

## Updates
## N-Body Simulation + HDR & Bloom - (Oct.31.2021)
![n body simulation](https://github.com/utinyt/Vulkan/blob/master/vulkan/screenshots/n_body_simulation.gif?raw=true)<br>
#### Average frame time: 5.57ms (179.6 FPS)
* 32768 particles (uniformly distributed on the surface of a sphere)
* Screen resolution 1200x800
* HDR (reinhard tone mapping)
* Bloom (gaussian blur)
* Compute shader + shared variables
<br>

## Deferred Rendering + SSAO & MSAA - (Oct.05.2021)
![deferred_rendering](https://raw.githubusercontent.com/utinyt/Vulkan/master/vulkan/screenshots/deferred_rendering.png)<br>
Youtube link : https://youtu.be/CDU1MrpubUw

### Scene setup
* 20 point lights
* 1024 bunnies - instanced rendering
* Screen resolution 1200x800
* MSAA applied (maximum sample count supported by current device)
  
### Optimization #1
![deferred_rendering edge detection](https://github.com/utinyt/Vulkan/blob/master/vulkan/screenshots/deferred_rendering_edge_detection.png?raw=true)<br>
Used edge detection (comparing neighborhood normal vectors) to only apply msaa to the pixels on edges<br>

### Optimization #2
To fix thread coherence problem ("edge pixels" and "non-edge pixels" are computed in one pass), the render pass for edge pixels was separated by using stencil buffer generated from edge detection algorithm.<br>

#### Reference : [Antialiased Deferred Rendering by NVIDIA Gameworks](https://docs.nvidia.com/gameworks/content/gameworkslibrary/graphicssamples/d3d_samples/antialiaseddeferredrendering.htm)<br>
<br>

## MSAA - (Sep.16.2021)
![mass_x1](https://raw.githubusercontent.com/utinyt/Vulkan/master/vulkan/screenshots/msaa_x1.png)<br>
![mass_x8](https://raw.githubusercontent.com/utinyt/Vulkan/master/vulkan/screenshots/msaa_x8.png)<br>
<br>

## Skybox & environment (reflection) mapping - (Sep.16.2021)
![skybox](https://github.com/utinyt/Vulkan/blob/master/vulkan/screenshots/skybox.gif?raw=true)<br>
#### Skybox textures: [http://www.humus.name/index.php?page=Textures&start=8](http://www.humus.name/index.php?page=Textures&start=8)
<br>

## Initial framework - (Sep.06.2021)
![initial_framework](https://github.com/utinyt/Vulkan/blob/master/vulkan/screenshots/initial_framework.png?raw=true)<br>
#### Initial scene with stanford bunny - simple diffuse light applied <br>

Most of basic vulkan features were implemented at this point: <br>
* [Devices](https://github.com/jooho556/TeamPositive/blob/master/vulkan/core/vulkan_device.h): Collection of physical / logical device handle <br>
* [Swapchain](https://github.com/jooho556/TeamPositive/blob/master/vulkan/core/vulkan_swapchain.h): Manage images in swapchain (acquire / present) <br>
* [MemoryAllocator](https://github.com/jooho556/TeamPositive/blob/master/vulkan/core/vulkan_memory_allocator.h): Naive memory allocator that pre-allocate big chunk(s) of memory per memory type <br>
* [Textures](https://github.com/jooho556/TeamPositive/blob/master/vulkan/core/vulkan_texture.h): Load texture from a file (stb_image used) <br>
* [Mesh](https://github.com/jooho556/TeamPositive/blob/master/vulkan/core/vulkan_mesh.h): Load model from a obj file (tinyobjloader used) <br>

