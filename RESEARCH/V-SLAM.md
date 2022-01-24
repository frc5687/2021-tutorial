# The team has been working on V-SLAM for the new robots, localized here is an brief description of V-SLAM and its implementation
 
# V-SLAM stands for Visual Simultaneous Localization and Mapping
V-SLAM facilitates the usage of a stereoscopic camera to determination position in space whilst simultaneously mapping said space.
 
# How V-SLAM works (this section is confusing, expand your thoughts)
V-SLAM generates a disparity map to calculate image depth. V-SLAM uses optical flow to track the movement of key points in an image from frame to frame and then uses trig to calculate the movement of the camera using the movments of the points. It uses an IMU to track the small movements of the camera. The IMU is then reset to stop drift.
 
## WARNING: IF PLANNING TO WORK ON THE V-SLAM PLEASE INSURE A YOU POSSESS SOME OF THE SKILLS REQUIREMENTS. WITHOUT THESE IT WILL MAKE WORKING ON THE V-SLAM ALMOST IMPOSSIBLE
 
## Hardware 
 
# Cameras
 
# ZED 2i (https://www.stereolabs.com/zed/)
    -  Best stereoscopic camera on the commercial market
    -  Needs an external processor (Jetson Xavier NX)
    -  Has a lot of built in features 
    -  Needs CUDA **what is CUDA?** (CUDA is a parallel computing platform and programming model to facilitate using a GPU for general purpose computing)
    -  Has a complete SDK (can be a pain to configure on Unix)
    -  Works with C/C++, C#, Python C# and Python take extra configuration
 
# Intel Realsense t-265 (https://www.intelrealsense.com/tracking-camera-t265/)
    -  Doesn't need an external processor (Jetson Xavier NX)
    -  Suffers from really bad drift
    -  Only does basic V-SLAM
    -  SDK easy to set up on Unix one bash command
    -  Only works in python via pip3 package librealsense
 
## Coprocessors 
 
We use the Jetson Xavier NX as it is what we first got our hands on and is the most completely configured computer. It is also more than powerful which makes it easy to add new functionality.
 
# Jetson Xavier NX(2x) (https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-xavier-nx/)
    - Powerful processor
    - Unix based (Jetpack)
    - Cooling problems
    - Made by NVIDIA
    - Has CUDA
    - ~ $ 400 - 1600
 
# Jetson Nano(1x) (https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-nano/)
    - Not as powerful of a processor
    - Unix based (Jetpack)
    - Cooling problems
    - Made by NVIDIA
    - Has CUDA
    - Cheaper 
    - $ ~ 100 - 200
 
 
## Skills requirements
 
Working with the Jetsons and V-SLAM is not an easy task it requires a deep understanding the below
 
- C/C++(The underlaying code is all in C and we will be moving to C++)
- CMake(This is of extreme importance you MUST know what this is and how to use it first)
- Python3(less important as it's being phased out)
- Bash(It is impossible to do anything with the Zed SDK without a deep deep understanding of Bash scripting)
- pip3 (packages we use are pyzed(Zed API for python), cython(creative name for a Python - C api, ), numpy (used for math but really really good for matrix math), matplotlib.pyplot (graphing), keras (tensorflow api AI and ML), tensorflow(library for AI and ML, be warned installing the correct version tensorflow))
- sockets
- crontab
- Unix(all of the V-SLAM code runs on Jetpack 4.6 or **whatever**, based on the linux kernel. In this case Ubuntu 18 LTS Bionic Beaver)
- sudo

