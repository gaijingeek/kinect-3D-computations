# Azure Kinect Body Tracking 3D computation Sample

## Introduction

This project is a modified Azure Kinect Body Tracking Simple3dViewer sample.
At the moment, it works exactly as the Simple3dViewer: it creates a 3d window that visualizes all the information provided
by the body tracking SDK. On top of that:
- it creates two files:
  1) NavelJointPositions.txt, listing the positions of the navel joints of all the bodies in a frame (bodyID  X  Y  Z), remember that X,Y are pixels whilst Z is the depth info in mm
  2) NavelJointDistance.txt, computing the euclidean distance between the Navel Joints "as is", using the raw values. 

## Usage Info

USAGE: kinect-3D-computations.exe SensorMode[NFOV_UNBINNED, WFOV_BINNED](optional) RuntimeMode[CPU, OFFLINE](optional)
* SensorMode:
  * NFOV_UNBINNED (default) - Narraw Field of View Unbinned Mode [Resolution: 640x576; FOI: 75 degree x 65 degree]
  * WFOV_BINNED             - Wide Field of View Binned Mode [Resolution: 512x512; FOI: 120 degree x 120 degree]
* RuntimeMode:
  * CPU - Use the CPU only mode. It runs on machines without a GPU but it will be much slower
  * OFFLINE - Play a specified file. Does not require Kinect device. Can use with CPU mode

```
e.g.   kinect-3D-computations.exe WFOV_BINNED CPU
                 kinect-3D-computations.exe CPU
                 kinect-3D-computations.exe WFOV_BINNED
                 kinect-3D-computations.exe OFFLINE MyFile.mkv
```

## Instruction

### Basic Navigation:
* Rotate: Rotate the camera by moving the mouse while holding mouse left button
* Pan: Translate the scene by holding Ctrl key and drag the scene with mouse left button
* Zoom in/out: Move closer/farther away from the scene center by scrolling the mouse scroll wheel
* Select Center: Center the scene based on a detected joint by right clicking the joint with mouse

### Key Shortcuts
* ESC: quit
* h: help
* b: body visualization mode
* k: 3d window layout
