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

This year we are switching our recommended [integrated development environment (IDE)](https://en.wikipedia.org/wiki/Integrated_development_environment) from [IntelliJ IDEA](https://www.jetbrains.com/idea/) to [Visual Studio Code (VSCode)](https://code.visualstudio.com/).  You are welcome to use IntelliJ (or Eclipse, emacs or vim) if you'd prefer, but this tutorial assumes you're coding in VSCode.  If you don't already have a preference for your programming environment, start with VSCode.

### Software to download
* [Slack](https://slack.com/downloads) - for team communication.  You might want both a desktop and a mobile version of slack since we use this for team communication.
* [WPILib](https://github.com/wpilibsuite/allwpilib/releases/tag/v2021.3.1) - for tools and libraries we use in our code.  Make sure to get the latest release.
* [SourceTree](https://www.sourcetreeapp.com/) - for working with GitHub repositories.  (optional)

### Accounts you will need
* Slack - If you aren't on slack, please talk with or email a student on the team so they can make sure you get added to the right channels
* [GitHub](https://github.com/join?source=header) - Once you have created your account, let Ben Bernard know so we can add you to the team
* You may also be required to create Atlassian, Oracle, and JetBrains accounts in order to download their tools.

### Setting up your tools

Note: All tool setup is dependent on having Admin rights on your local machine. If you don't have admin right please see Amos Cooper to get that sussed out.

1. [Install WPILib](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/wpilib-setup.html)
2. Download VS Code for Single Install
3. Install these tools:

  - [x] Visual Studio Code
  - [x] Gradle
  - [x] Java JDK/JRE
  - [x] Tools and Utilities
  - [x] WPILib Dependencies
  - [x] Visual Studio Code Extensions

We'll be adding instructions for the following:

* Checking out a repo from GitHub
* Building a project
* Running a desktop simulation of the robot before loading code onto a real robot
* Deploying code to the real robot

### Practicing with GitHub for Version Control

If you're new to the team, one of the things you need to learn is [how to use GitHub for version control](https://www.howtogeek.com/180167/htg-explains-what-is-github-and-what-do-geeks-use-it-for/).

Our team has a practice repository called [learngit](https://github.com/frc5687/learngit).  Use the learngit repo to learn how to use GitHub to [clone a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository), [track issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues), [manage branches](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches) and create [pull requests](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).

Feel free to mess around as much as you want in learngit.  You won't mess anything up!  It's there for you to practice your git skills and learn how to share your code with other people on the team.

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
