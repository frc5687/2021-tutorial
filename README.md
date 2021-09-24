# 2021-tutorial
Tutorial for 2021-2022 school year to help students start programming (controls)

FRC stands for "FIRST Robotics Competition."  The basis for this competition is a standardized robotic framework that includes a National Instruments [roboRIO](https://forums.ni.com/t5/FIRST-Robotics-Competition/roboRIO-Details-and-Specifications/ta-p/3494658?profile.language=en) controller.  We're writing code to load onto a roboRIO to control our robot.

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
* [Debugging a Robot Program](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/debugging-robot-program.html)

### FRC Game Tools

A Windows computer with the [FRC Game Tools](https://docs.wpilib.org/en/stable/docs/zero-to-robot/step-2/frc-game-tools.html) installed on it is necessary for loading code onto the robot (imaging the roboRIO) and controlling the robot during competition.  The [FRC Driver Station](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#frc-driver-station-powered-by-ni-labview-windows-only) is the only software allowed to be used to control the state of the robot during competition.

## Meet the Robots

COMING SOON!

Team, please add pictures and a description of each working robot we have available.  In the description, explain which repo to use for each robot.

The code for each robot is different because each robot has a different set of hardware (motors, sensors, etc.) and each robot has a different set of behaviors depending on the game and its role on an alliance.  The [rules of the game](https://www.firstinspires.org/robotics/frc/game-and-season) for this year will be announced in December / January, but typically games consist of two teams of three robots.  On each team robots can specialize on "offense" (scoring points for your own team) or "defense" (preventing the other team from scoring points), or be a generalist and be able to play offense or defense as needed.

Robots can usually operate in two modes: autonomous and teleoperated.  For the first part of each match, the robots run the code we write to accomplish tasks on their own without human input.  After the autonomous period, human drivers and operators can use joysticks to send radio signals to the robots to operate as remote-controlled machines.  We usually write code to help the human drivers and operators -- for example, pushing a button might have the robot automatically lock onto a target to launch balls at it.  In "target-lock" mode, the human driver might be able to move the robot all over the field of play to scoop up more balls, but our controls code keeps the robot pointing at the target so the human operator can launch balls once they've been picked up by the intake mechanism and are ready to launch.

## Glossary

Term | Definition
-----|-----------
loop overrun | This happens when your code tries to do too much in the limited time available for each main event loop.  Unlike most software programs, which can take as much time as they want to complete a task, the code we're writing is running on a real-time operating system that is controlling a machine moving quickly through space.  Things need to happen on a predictable and dependable schedule.  For example, you may need to send signals to eight motors to send the robot in the right direction at the right speed.  The robot won't work right if your code is so complicated that you only have time each loop to calculate seven of the eight signals you need to send.  The standard loop time for FRC code is 20 milliseconds, i.e. all of the code you put in one loop must complete within 20 milliseconds or a loop overrun will occur.
millisecond (ms) | One one-thousandth of a second.  The standard FRC loop time is 20 milliseconds, or 2 hundredths of a second, or 50 loops per second.
repo | Short for repository, this is a collection of code that you can check out and check in as a unit.  The code for each robot is stored in a separate repo.
roboRIO | The [roboRIO](https://docs.wpilib.org/en/stable/docs/software/roborio-info/roborio-introduction.html) is the "brain" of our robot.  It is essentially a special-purpose computer designed for controlling robots.  The "[roboRIO 1.0](https://www.andymark.com/products/ni-roborio)" has been discontinued and an upgraded "[roboRIO 2.0](https://www.firstinspires.org/robotics/frc/blog/2021-ni-guest-blog-roborio2-0)" is on its way.  
unit testing | One of the best ways to prevent having to debug too many issues at once is to do [unit testing](https://en.wikipedia.org/wiki/Unit_testing).  This means breaking down what our code should do into small, discrete pieces that can be tested one at a time by automated tools.  Then, when a change is made, these tests can be run to see if it breaks anything.
VS Code | Visual Studio Code, an integrated development environment for writing software.  This combines a programming editor with syntax highlighting, plus tools for revision control, as well as building, running and debugging code.
version control | Also called "revision control," this is a system for keeping track of changes to a project. GitHub is the host we use for version control, and VS Code is one of the client programs we use to check out and check in code stored on GitHub.  All changes to our code are tracked so that you can see exactly what changed and who changed it between versions.
WPILib | This is the library of code that we use to control our robot.  Rather than reinventing the wheel, we start with code that other people have developed, and add our own enhancements to control the hardware we build.  WPI stands for the [Worcester Polytechnic Institute](https://www.wpi.edu/) in [Worcester, Massachusetts](https://en.wikipedia.org/wiki/Worcester,_Massachusetts).