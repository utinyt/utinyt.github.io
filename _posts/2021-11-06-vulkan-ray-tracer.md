---
layout: post
title: "Vulkan Ray Tracer"
author: "Jooho Jeong"
categories: projects
tags: [projects.graphics]
image: path_tracing.gif
excerpt_separator: <!--more-->
---

This is a real-time ray tracer using C++ / Vulkan / GLSL.
<!--more-->

## Developing Environments
* OS: Windows 10
* IDE: Visual Studio 2019
* GPU: RTX 2060 SUPER

Successful build on other environments is not guaranteed.

## Third Party
* [tinyobjloader](https://github.com/tinyobjloader/tinyobjloader)
* [tinygltf](https://github.com/syoyo/tinygltf)
* [stb collection](https://github.com/nothings/stb)
* [imgui](https://github.com/ocornut/imgui)

## References
A lot of code were based on these great resources:
* [Vulkan tutorial by Alexander Overvoorde](https://vulkan-tutorial.com/Introduction)
* [Vulkan samples by Sascha Willems](https://github.com/SaschaWillems/Vulkan)
* [Nvpro Core from NVIDIA DesignWorks Samples](https://github.com/nvpro-samples/nvpro_core)
* [vk_raytracing_tutorial_KHR from NVIDIA DesignWorks Samples](https://github.com/nvpro-samples/vk_raytracing_tutorial_KHR)

## Updates
## Path Tracing - (Sep.20.2021)
![path_tracing](https://github.com/utinyt/Vulkan-Ray-Tracer/blob/master/screenshots/path_tracing.gif?raw=true)<br>

#### Reference: [vk_raytracing_tutorial_KHR - ray_tracing_gltf](https://github.com/nvpro-samples/vk_raytracing_tutorial_KHR/tree/master/ray_tracing_gltf)

## First model - (Sep.12.2021)
![bunny](https://raw.githubusercontent.com/utinyt/Vulkan-Ray-Tracer/master/screenshots/bunny.png)
#### Reference: [vk_raytracing_tutorial_KHR](https://nvpro-samples.github.io/vk_raytracing_tutorial_KHR)
