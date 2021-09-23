# 2021-tutorial
Tutorial for 2021-2022 school year to help students start programming (controls)

FRC stands for "FIRST Robotics Competition."  The basis for this competition is a standardized robotic framework that includes a National Instruments [roboRIO](https://www.ni.com/en-us/support/model.roborio.html) controller.  We're writing code to load onto a roboRIO to control our robot.

FRC teams choose one of three ways to program their robots:

1. LabVIEW
2. Java
3. C++

Our team's code base is in the [Java programming language](https://en.wikipedia.org/wiki/Java_(programming_language)).

This tutorial explains how to set up the tools and accounts our team uses to write Java code to control our robot.  For a more general introduction to programming FRC robots, see the [FIRST Robotics Competition Control System](https://docs.wpilib.org/en/stable/).  See below for links to interesting sections of those docs.

## Learn Java

If you already know Java, skip down to "Getting Started." If you don't know Java you'll need to learn it.

Just like anything in life, at first it's hard and then once you get the hang of it, it gets easier and more fun.  There is no substitute for practice!

### Video Overviews of Java

Watch these for a basic overview of the language.

* [Learn Java in 14 Minutes](https://www.youtube.com/watch?v=RRubcjpTkks) -- note: in this video tutorial Eclipse (not VSCode) is being used to write Java code so your code may look slightly different (for example, the color of primitives might be different) but the concepts are the same
* [Java Tutorial for Beginners](https://www.youtube.com/watch?v=eIrMbAQSU34)

### Online Code Courses for Java

To actually learn any programming language, you have to practice with it.  Use these code courses to solve increasingly hard problems until you're able to use Java to create your own programs.

* [CodeGym](https://codegym.cc/) -- do the free levels (no need to create an account or pay for the advanced levels)
* [Codecademy Learn Java](https://www.codecademy.com/learn/learn-java)

## Getting Started

Now that you understand a little Java, here's how to set up the programming tools our team uses.

### Note

Because the [FRC Driver Station](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#frc-driver-station-powered-by-ni-labview-windows-only) runs only on Windows, in the past most programming has been done in Windows as well.  You are free to use MacOS or Linux to code, but if you do you won't have access to the full suite of tools FRC provides.

This year we are switching our recommended [integrated development environment (IDE)](https://en.wikipedia.org/wiki/Integrated_development_environment) from [IntelliJ IDEA](https://www.jetbrains.com/idea/) to [Virtual Studio Code (VSCode)](https://code.visualstudio.com/).  You are welcome to use IntelliJ (or Eclipse or emacs or vi) if you'd prefer, but this tutorial assumes you're coding in VSCode.  If you don't already have a preference for your programming environment, start with VSCode.

### Software to download
* [Slack](https://slack.com/downloads) - You might want both a desktop and a mobile version of slack since we use this for team communication
* [Java](https://www.oracle.com/technetwork/java/javase/downloads/index.html) - Accept the license terms and select the latest stable Windows x64 build (jdk-?????-windows-x64.exe). 
* [git](https://git-scm.com/)
* [VSCode](https://code.visualstudio.com/) - Download the latest stable build
* [WPILib](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/wpilib-setup.html)
* [Gradle](https://gradle.org/gradle-download/) - Choose the "Binary only distribution"
* [SourceTree](https://www.sourcetreeapp.com/) - (optional) Just click the green Download for Windows button

### Accounts you will need
* Slack - If you aren't on slack, please talk with or email a student on the team so they can make sure you get added to the right channels
* [GitHub](https://github.com/join?source=header) - Once you have created your account, let Ben know so we can add you to the team
* You may also be required to create Atlassian, Oracle, and JetBrains accounts in order to download their tools.

### Setting up your tools
1. Be sure you have all the software mentioned above downloaded and accounts created
2. Install Java
3. Install git
4. Install VSCode
5. Install Gradle
6. Install SourceTree
6. Checkout the 2019-tutorial project
7. Open the project in VSCode
8. NOT READY YET (We'll be adding basic robot code) Build the project
9. NOT RREADY YET (We'll be adding instructions for how to deploy code to the robot) Do a test deploy

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