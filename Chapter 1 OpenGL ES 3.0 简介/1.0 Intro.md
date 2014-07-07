OpenGL ES是OpenGL for Embedded Systems的简称，是用于手持和嵌入式设备的高级3D图形程序的（API）。OpenGL ES是现在智能手机的主流图形API，同时也在向桌面扩展。支持OpenGL ES的平台包括iOS，Android，BlackBerry，bada，Linux和Windows。OpenGL ES同时支持着WebGL - 基于浏览器3D图形的web标准。

随着2009年7月iPhone 3GS以及2010年3月Android2.0的发布，iOS和Android设备开始支持OpenGL ES 2.0。本书的第一版对OpenGL 2.0做了详细的介绍。本版将对OpenGL ES 3.0进行介绍。随着各个手持平台的发展，其对OpenGL ES 3.0的支持是必然的。事实上，在搭载Android 4.3+的设备，以及运行iOS7的iPhone 5s上，OpenGL ES 3.0已经得到了支持。OpenGL ES 3.0向后兼容OpenGL ES 2.0，也就是说，用OpenGL ES 2.0编写的应用可以在OpenGL ES 3.0上继续工作。

OpenGL ES是Khronos Group创建的众多API集之一。该组织于2000年1月创建，是由成员提供经费、致力于开放标准和免费API的工业联盟。Khronos Group同时管理着OpenGL - 跨平台的桌面系统3D API标准，该标准已被Linux，UNIX，Mac OS X以及Microsoft Windows支持，并得到广泛的应用。

由于OpenGL的广泛使用，以该标准为基础来进行针对手持、嵌入式设备标准的开发，再对其进行修改以满足这些设备的需求和约束是很自然的。在OpenGL ES的早期版本（1.0,1.1和2.0），这些设备约束主要包括：有限的处理能力和可用内存，低内存带宽，以及对低功耗的要求。在定义OpenGL ES规范时，工作组基于以下原则来进行工作：

 - OpenGL API非常庞大且复杂，而OpenGL ES工作组的目标是创建适用于受限设备的API。为了达到这个目的，工作组首先将OpenGL API中冗余的部分移除。如果有多种方式完成某个操作，那么只保留最常用的方式，其余的都将被移除。例如指定几何体，在OpenGL中可以采用立即模式、显示列表、顶点数组三种方式。在OpenGL ES中，只保留了顶点数组，立即模式和显示列表都被移除了。
 - 去除冗余很重要，但是保持对OpenGL的兼容性同样重要。OpenGL ES在设计时，会尽可能的保证使用OpenGL的嵌入式子集的应用能够在OpenGL ES上运行。这使得开发者可以使用这两种API，用同样的功能集来开发应用和工具。
 - 为了适应手持、嵌入式设备的约束，同时引入了新的功能。比如，为了降低功耗并提高着色器的性能，精度限定符（precision qualifiers）被引入到着色语言中。
 - OpenGL ES的设计者们为图像质量设计了最小功能集。在早期的手持设备上，屏幕尺寸有限，这使得屏幕上每个像素的绘制质量要尽可能的好。
 - OpenGL ES工作组希望确保任何OpenGL ES实现都符合规范，并能在图像质量、正确性和鲁棒性方面达到标准。为此，他们设计了一致性测试，任何OpenGL ES实现都需要通过此测试，以确保符合标准。
 
 迄今为止，Khronos已经发布了四个版本的OpenGL规范：OpenGL ES 1.0和ES1.1（本书中将统称OpenGL ES 1.*），OpenGL ES 2.0和OpenGL ES 3.0。其中，1.0和1.1版本分别以OpenGL 1.3和1.5规范为基础，实现了固定管线。
 
 OpenGL ES 2.0规范以OpenGL 2.0规范为基础，实现了可编程图形管线。
 
 OpenGL ES 3.0以OpenGL 3.3规范为基础，是手持设备的下一代图形标准。OpenGL ES 2.0和DirectX9的能力相当，其同期硬件则对应于Microsoft Xbox 360。与此同时，桌面版GPU的图形功能在逐步增强。大量技术，如shadow mapping，volume rendering，GPU-based particle animation，geometry instancing，texture compression，gamma correction，其底层的关键技术在OpenGL ES 2.0中都是缺失的。OpenGL ES 3.0在保证兼顾嵌入式系统的约束的同时，将这些功能引入到手持设备中。
 
 当然，在设计早期OpenGL ES版本时需要考虑的一些约束在今天已经不复存在。比如，手持设备的屏幕尺寸已经很大（有些分辨率甚至超过了桌面PC显示器）。而且，很多手持设备目前都配备了高性能多核CPU以及大量的内存。因此，Khronos Group在开发OpenGL ES 3.0时，更注重的是手持应用所需要的特性。
 
 接下来将对OpenGL ES 3.0管线进行介绍。
 