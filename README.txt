We provide a C++ implementation of SurfaceNets for multiple materials.
SurfaceNets is a surfacing technique that creates smooth surfaces from 
data samples stored in a 3D volume. This implementation handles multiple 
materials, where each material is represented as an indexed value. Both
8-bit and 16-bit data formats are supported. 

More details about the method are available in:

Frisken, S., "SurfaceNets for Multi-Label Segmentations with Preservation of 
Sharp Boundaries", Journal of Computer Graphcis Techniques, 2021. 

When using this code or any derivative work, please cite this paper. 

This code includes a C++ library for SurfaceNets and a simple Qt- and OpenGL-
based application for testing and demoing the library. The code is provided 
with a Visual Studio solution that has been tested on Windows. Using this VS 
solution will require setting up paths to Qt and OpenGL.

This code is open source and licensed under the MIT license. We hope that
you will find it useful. For more more information, see the LICENSE.txt file 
provided with this README.txt file.