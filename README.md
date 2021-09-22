# 2021-tutorial
Tutorial for 2021-2022 school year to help students start programming (controls)

FRC stands for "FIRST Robotics Competition."  The basis for this competition is a standardized robotic framework that includes a National Instruments [roboRIO](https://www.ni.com/en-us/support/model.roborio.html) controller.  We're writing code to load onto a roboRIO to control our robot.

## Getting Started

This tutorial explains how to set up the tools and accounts our team uses to write code to control our robot.  For a more general introduction to writing code to control robots like ours, see the [FIRST Robotics Competition Control System](https://docs.wpilib.org/en/stable/).  See below for more links to interesting sections of the FRC control system documentation.

### Note

CAUTION: The following information is copied from the 2019 tutorial and is subject to change this year.  Once this tutorial has been updated with this year's plan, this caution notice will be removed.

Because the [FRC Driver Station](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#frc-driver-station-powered-by-ni-labview-windows-only) runs only on Windows, most of us have chosen to do our programming in Windows as well.  You are free to use Mac OSX, but these instructions will cover only Windows installations.

### Software to download (CAUTION: subject to change)
* [Slack](https://slack.com/downloads) - You might want both a desktop and a mobile version of slack since we use this for team communication
* [Java](https://www.oracle.com/technetwork/java/javase/downloads/index.html) - Accept the license terms and select the latest stable Windows x64 build (jdk-?????-windows-x64.exe). 
* [VSCode](https://code.visualstudio.com/) - Download the latest stable build
* [IntelliJ](https://www.jetbrains.com/idea/download/) - Download the Windows Community edition
* [Gradle](https://gradle.org/gradle-download/) - Choose the "Binary only distribution"
* [SourceTree](https://www.sourcetreeapp.com/) - Just click the green Download for Windows button
* [git](https://git-scm.com/)

### Accounts you will need
* Slack - If you aren't on slack, please talk with or email a student on the team so they can make sure you get added to the right channels
* [GitHub](https://github.com/join?source=header) - Once you have created your account, let Ben know so we can add you to the team
You may also be required to create Atlassian, Oracle, and JetBrains accounts in order to download their tools.

### Setting up your tools (CAUTION: subject to change)
1. Be sure you have all the software mentioned above downloaded and accounts created
2. [Install Java](https://github.com/frc5687/2019-tutorial/wiki/Install-Java) (if you don't already have it installed)
3. [Install IntelliJ](https://github.com/frc5687/2019-tutorial/wiki/Install-IntelliJ)
4. [Install Gradle](https://github.com/frc5687/2019-tutorial/wiki/Install-Gradle)
5. [Install SourceTree](https://github.com/frc5687/2019-tutorial/wiki/Install-SourceTree)
6. Checkout the 2019-tutorial project
7. Open the project in IntelliJ
8. Build the project
9. Do a test deploy

## Communication channels on slack

* controls - for discussions about programming the robot
* github - for pull requests (code changes you want the team to review)
* general - messages for the whole robotics team

## FRC Control System Documentation

For coders, these are useful sections of the [FRC Control System documentation](https://docs.wpilib.org/en/stable/):

* [What is WPILib?](https://docs.wpilib.org/en/stable/docs/software/what-is-wpilib.html)
* [roboRIO Introduction](https://docs.wpilib.org/en/stable/docs/software/roborio-info/roborio-introduction.html)
* [Software Component Overview](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html)
* [Creating a Robot Program](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/creating-robot-program.html)
  - TimedRobot
  - RobotBase
  - Command Robot
  - Romi
* [Robot Simulation](https://docs.wpilib.org/en/stable/docs/software/wpilib-tools/robot-simulation/introduction.html)
* [Imaging your roboRIO](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-3/imaging-your-roborio.html)
* [Building and Deploying Robot Code](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/deploying-robot-code.html)

### FRC Game Tools

A Windows computer with the [FRC Game Tools](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/frc-game-tools.html) installed on it is necessary for loading code onto the robot (imaging the roboRIO) and controlling the robot during competition.  The [FRC Driver Station](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#frc-driver-station-powered-by-ni-labview-windows-only) is the only software allowed to be used to control the state of the robot during competition.