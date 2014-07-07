# OpenGL ES 3.0 #
如前所述，本书将介绍OpenGL ES 3.0 API。我们将详细介绍OpenGL ES 3.0规范，针对各个特性给出示例，并讨论性能优化技术。阅读本书之后，你将会对OpenGL ES 3.0 API有深入的了解，很容易的写出OpenGL ES 3.0应用，并且不用担心要阅读多个规范来理解某个特性如何工作。

OpenGL ES 3.0实现了可编程着色器的图形管线，包含两个规范：OpenGL ES 3.0 API规范以及OpenGL ES Shading Languge 3.0规范（OpenGL ES SL）。图1-1展示了OpenGL ES 3.0图形管线。阴影部分表示可编程的阶段。

![OpenGLES3](OpenGLES3.0_images\OpenGLES3.png)
图 1-1 OpenGL ES 3.0 图形管线

## Vertex Shader ##
本节将对顶点着色器进行概要介绍。顶点和图元（fragment）着色器将在后续章节中详细介绍。顶点着色器实现了通用的操作顶点的可编程方法。

顶点着色器的输入包括：

- 着色器程序 - 顶点着色器程序源代码或可执行文件，描述对顶点的操作。
- 顶点着色器输入（或属性） - 用顶点数组描述的每顶点数据。
- Uniforms - 顶点或（图元）着色器所使用的常量数据。
- Samplers - 特殊类型的uniforms，表示顶点着色器所使用的纹理。

顶点着色器的输出，在OpenGL ES 2.0中被称为varying variables，在3.0中重命名为顶点着色器输出变量（vertex shader output variables）。在光栅化阶段，将对每个生成的片元计算顶点着色器输出值，进而传给片元着色器作为输入。从顶点着色器输出