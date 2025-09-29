# 概述——GPGPU的前世今生

> ”世上本没有路，走的人多了，也便成了路。"——鲁迅

## GPU的诞生

最初是没有GPU的，CPU把每个像素的RGB信息依次写入内存中的Frame Buffer，再输出到显示器上。

随着游戏的发展，对于图形处理的需求日益显现。

于是，市面上出现了多家提供显卡方案的厂家，比如S3/Trident/Voodoo等。



![GeForce256](images/nv_geforce_256.jpg)
>1999年10月，Nvidia发布了世界上第一块被称作GPU的GeForce 256

![GPU Graphic Pipeline](images/gpu_graphics_pipeline.png)

术语：
* Vertex 顶点：一般包括位置position<x,y,z>，法线方向normal<x,y,z>，颜色color<r,g,b,a>和纹理坐标texture coordinate<x,y>等信息
* Primitive 图元：包括点、线、三角形、四边形等简单形状
* Rasterize 光栅化：填充三角形所覆盖的像素
* Vertex/Pixel Shader：可编程模块，单入单出

## GPGPU的雏形

![CPU vs GPU](images/cpu_vs_gpu.png)

2002年，Nvidia提出了GPGPU的概念。

## GPGPU的出现

2006年11月，Nvidia发布了CUDA（Compute Unified Device Architecture），极大方便了普通开发者使用GPGPU。
