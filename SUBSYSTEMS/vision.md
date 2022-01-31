# Vision Hardware and Software Available for FRC 5687 this Season

Vision hardware includes cameras and processor boards and other devices that allow our robot to sense patterns of radiation.  Vision software includes libraries that run on the Roborio (WPILib) and libraries and programs that run on processor boards or the driver station or a developer box.

The typical vision subsystem is a co-processor board running some version of Linux that is connected to a camera and to the Roborio.

As of January 2022, the team had

 * 1 Gloworm
 * 2 Limelight 2.0
 * 2 Limelight 2.0+
 * "But someone misplaced the limelight that was on Miley, so we are down to 3"

In general, we have four hardware processors in the mix whenever we develop a vision subsystem:

1. A **developer box**: a laptop or a desktop system that one of our students or mentor uses to configure devices, write code, and control devices during development.
1. **RoboRio**: the main processor on the robot which runs our Java code that controls robot behavior.
1. **Driver station**: the main remote control device that our human drive team uses to control the robot.
1. **Processor board**: many vision systems have their own boards to offload processing from the RoboRio and driver station.

Four common reasons to add vision to an FRC robot are

1. Help the human drive team control the robot.
1. Find or lock on to a target to improve accuracy of shooting at or moving toward the target.
1. Determine the robot's pose on the field (localize the robot on a map).
1. Detect other robots, game elements and playing field features.

The second and third reasons to add vision typically require solving the "PnP" problem.  Youyang et al. describe this problem as follows:

"Perspective-n-point [PnP] is a classical computer vision problem that uses three-dimensional points and image pixels to estimate camera pose. The visual robot often loses its position when the camera moves too fast or the environment changes. Perspective-n-point is used to relocate robot position." [Robust improvement solution to perspective-n-point problem](https://journals.sagepub.com/doi/full/10.1177/1729881419885700)

## Hardware

### Cameras

### Limelight (Both Hardware and Sofware)

[Limelight](https://limelightvision.io/) is a plug-and-play smart camera (hardware and software) purpose-built for FRC.  It is easy enough for teams with no vision experience or expert mentors, and powerful enough for experienced teams who need a reliable, competition-ready vision solution.

Features

Versions
 * [Limelight 2+](https://www.andymark.com/products/limelight-2-plus) (internals have been redesigned)
   - Reduce power consumption by up to 50%
   - Eliminate the LED "warm-up" period.
   - Further improve low voltage performance, dropping the brownout voltage to 4V.
   - Reduce the operating temperature by 20C
   - Enable LED dimming.
   - Increase max LED brightness by 15%
 * [Limelight 2](https://www.andymark.com/products/limelight2) (discontinued)
   - Smaller footprint (note that the mounting hole spacing has changed in both dimensions)
   - Increased FOV
     - From 54 x 41 degrees to 59.6 x 45.7 degrees
   - Improved build quality
     - Rigid lens mount
     - Improved plastic finish
     - Tighter margins around ports and LEDs
     - Light-pipe-exposed status LEDs
     - Easier access to main power port
     - Easier access to IP reset button
     - Easier access to microUSB port
     - POE jumper removed
   - POE is always enabled
   - Limelight bypasses normal NetworkTables limits to instantly submit targeting data
   - Serial port removed
   - MicroUSB cable provides power while flashing. No need to apply 12V power while flashing
   - Some LL1 units contained loud fans, and others contained quiet fans. The new LL2 fan's loudness is in-between those of the two LL1 fans
   - 60% more light than the standard dual-ring setup
   - Illuminance is increased by gloss-finish LED cones
   - Status LEDs
     - Inner green LED blinks quickly if a target has been acquired, and blinks slowly if no targets are in view.
     - Outer yellow LED blinks slowly if the unit is using an automatic IP configuration, and remains solid if the unit is using a static configuration.

### Gloworm

[Gloworm](https://gloworm.vision/) is an inexpensive and open source vision hardware subsystem design.  A batch of ~50 Gloworm units were produced and sold out in December of 2020. There are no active plans to produce more.

Features

 * Raspberry Pi Compute Module 3+ (BCM2837 64-bit SoC @ 1.2GHz, 1GB LPDDR2 SDRAM, 8GB eMMC Flash)
 * OV5647 Camera Module (640x480 @ 90FPS video, low distortion 62.7° lens)
 * Dimmable ~400 lumen green LED array (with constant brightness down to 7v)
 * 10/100 Ethernet
 * 12V Passive PoE (with reverse polarity protection and brownout tolerance)
 * USB C ports for flashing and peripherals (such as a USB camera)
 * Supports [PhotonVision](https://photonvision.org/) and [WPILibPi](https://github.com/wpilibsuite/WPILibPi/releases) (formerly FRCVision)
 * Completely open source (CERN Open Hardware License v2 - Permissive Variant) -- see [https://github.com/gloworm-vision/gloworm](https://github.com/gloworm-vision/gloworm)
 * 20mm 5v cooling fan

 Notes

 * Gloworm is powered via 12V passive PoE, not standard 48V PoE.
 * Connect gloworm to your robot with a [passive PoE injector](https://www.revrobotics.com/rev-11-1210/) and an Ethernet cable.
 * Wire the passive PoE injector to your PDP, not the VRM.
 * Install any size breaker in the PDP slot you're using.
 * Run an Ethernet cable from the passive PoE injector output to Gloworm's Ethernet port.
 * Plug any peripherals you have into the USB C port labeled with a camera icon.

## Software

### PhotonVision

[PhotonVision](https://photonvision.org/) is free computer vision software for FRC, designed for ease of use with a variety of cameras and co-processors: "teams can go from setting up a camera and coprocessor to detecting and tracking targets by simply tuning sliders."

Features

 * Identify and lock on to up to 5 individual targets.
 * Calibrate intrinsics per camera.
 * Make fine camera adjustments.
 * Use the same camera for driving and robot vision.
 * Run as many cameras as your hardware can handle.
 * Toggle, blink, and adjust brightness of your custom LEDs.
 * Run natively on Gloworm hardware.

Notes

 * Source code at [https://github.com/PhotonVision/photonvision/](https://github.com/PhotonVision/photonvision/)
 * Many ways to install PhotonVision, depending on the co-processor that you are using.
   * For Raspberry Pi, you can flash a Pi image.
   * For other co-processors such as Nvidia Jetson, you can run an install shell script.
 * Cameras
   * Pi Camera Module V1 and [V2](https://www.raspberrypi.com/products/camera-module-v2/) (V1 is strongly preferred over the V2)
   * Microsoft LifeCam HD-3000 (available from AndyMark)
   * NOT supported: Logitech C270 HD Webcam (most Logitech cameras will not work)
 * Raspberry Pi versions: 3 or 4
 * Can use GPU Acceleration to maximize processing performance; however that is only supported on the Raspberry Pi 3.

### WPILibPi (formerly FRCVision)

A Raspbian-based Raspberry Pi image of libraries required for vision coprocessor development for FRC (e.g. opencv, cscore, ntcore, robotpy-cscore, pynetworktables, Java 11, etc). New for 2021, WPILibPi now comes in two variants, the "base" image for vision coprocessors, and an image designed for use with Pololu Romi 32U4 based robots.

Features

 * Web dashboard for configuring the rPi (e.g. changing network settings), monitoring the vision program (console, restart), changing CameraServer and NetworkTables settings, and uploading vision processing applications, all without the need for SSH
 * Default application that performs simple streaming of multiple cameras as well as camera switching; the image is "plug and play" for FRC dashboard streaming (just set your team number in the rPi web dashboard)
 * Includes example C++, Java, and Python programs to use as a basis for vision processing code
 * Designed for robustness to hard power offs by defaulting the filesystem to read only mode; safe to power directly from the VRM without an external battery
 * Boots (power applied to vision program running) in less than 20 seconds
 * All wireless functionality disabled (both WiFi and Bluetooth), so legal for competition use out of the box.

Notes

 * Latest release at [https://github.com/wpilibsuite/WPILibPi/releases](https://github.com/wpilibsuite/WPILibPi/releases)

### Limelight (Both Hardware and Software)

Limelight is an integrated hardware and software solution.  Limelight software is available on the [Limelight Downloads page](https://limelightvision.io/pages/downloads).

* [Limelight 2022.0.3 Update](https://www.chiefdelphi.com/t/limelight-2022-0-3-update/400306)