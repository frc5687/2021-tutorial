# The team has been working on V-SLAM for the new robots, localized here is an breif discription of V-SLAM and it's implemetion

# V-SLAM stands for Visual Simultaneous Localization and Mapping
It allows us to using a sereoscopic camera to locate ourselfs in space whilst simultaneously mapping said space.

# How V-SLAM works
V-SLAM mesaures pixel distance from one pixel in each image captured by the two sereo lenses. Then uses trig to calulate the distance. Using an algorithm to detect important ponits. Then uses optical flow to track the movement of those points, which is used to track movement. The Camera uses a IMU to track small quick movements, and then the IMU is reset to insure it doesn't suffer from drift. V-SLAM uses relocalization so that when the camera sees a location that it's seen before it can relocalize it's self.

## WARNING IF PLANNING TO WORK ON THE V-SLAM PLEASE INSURE A YOU POSSESS SOME OF THE SKILLS REQUIRMENTS. WITHOUT THESE IT WILL MAKE WORKING ON THE V-SLAM ALMOST IMPOSSIBLE

## Hardware 

# Cameras

# ZED 2i (https://www.stereolabs.com/zed/)
    -  Best steroscopic camera on the commercal market
    -  Needs an extrenal processer (Jetson Xavier NX)
    -  Has a lot of built in features 
    -  Needs CUDA
    -  Has a complete SDK (can be a pain to cofigure on Unix)
    -  Works with C/C++, C#, Python C# and Python take extra configuration

# Intel Realsense t-265 (https://www.intelrealsense.com/tracking-camera-t265/)
    -  Doesn't need an extrenal processer (Jetson Xavier NX)
    -  Suffers from really bad drift
    -  Only does basic V-SLAM
    -  SDK easy to set up on Unix one bash command
    -  Only works in python via pip3 package librealsense

## Coprocssors 

# Jetson Xavier NX(2x) (https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-xavier-nx/)
    - Powerful processer
    - Unix based (Jetpack)
    - Cooling problems
    - Made by NVIDIA
    - Has CUDA
    - ~ $ 400 - 1600

# Jetson Nano(1x) (https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-nano/)
    - Not as powerfulof a processer
    - Unix based (Jetpack)
    - Cooling problems
    - Made by NVIDIA
    - Has CUDA
    - Cheaper 
    - $ ~ 100 - 200


## Skills requirments

Working with the Jetsons and V-SLAM is not an easy task it requires a deep understanding the below

- C/C++(The unlaying code is all in C and we will be moveing to C++)
- CMake(This is of extreme importantance you MUST know what this is and how to use it first)
- Python3(less important as it's being phased out)
- Bash(It is impossible to do anything with the Zed SDK without a deep deep understanding of Bash scripting)
- pip3 (packages we use are pyzed(Zed API for python), cython(creative name for a Python - C api, ), numpy (if you don't know what this Gods help you, used for math but really really good for matrix math), matplotlib.pyplot (graphing), keras (tensorflow api AI and ML), tensorflow(library for AI and ML, be warned installing tensorflow can be a bit of a death sentance))
- sockets
- crontab
- Unix(all of the V-SLAM code runs on Jetpack 4.6 or whatever, which like most every good operating system is based of a linux kernal. In this case Ubuntu 18 LTS Bonic Beaver)
- sudo