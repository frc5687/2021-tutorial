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

  - [x] Visual Studio Code - for writing code
  - [x] [Gradle](https://docs.gradle.org/current/userguide/userguide.html) - for building code
  - [x] Java JDK/JRE - for compiling and running JAVA code
  - [x] Tools and Utilities - various other things
  - [x] WPILib Dependencies - stuff the library needs
  - [x] Visual Studio Code Extensions - things that make it easier to write code

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

## Controls Team Best Practices

Over the years the controls team has developed best practices so we can meet the demands of developing code both **off-season**, when we can afford to explore new ideas because we are not under deadline to produce working code, and **during the season**, when our team is under intense time pressure to build a working robot and then iterate quickly to improve it.  In the off season (fall semester), our main goals are to identify and train the students who will be able to participate in coding during the season and plan our coding strategy for the upcoming season.  Once the season starts (after January), our goal is to write code that will help our alliance win matches during competitions.

If you are a first-year student, you are welcome to just watch, or get involved as much as you want.  There are no expectations for first-year students; we recognize that you can learn a lot just by observing without the pressure of feeling like you need to code.  For sophomores and above, we do expect you to contribute to the team.  The more effort you put in, the more authority and responsibility you will earn.  We will encourage you to develop your skills as a programmer and as a team player who can be counted on to meet reasonable (but sometimes challenging) expectations.

### Repositories

Code for each robot is kept in a separate repository.  For example, [frc5687/2021-robot](https://github.com/frc5687/2021-robot) has the code for the 2021 competition robot (compbot).  We will create a new repository for the code for our new robot this season.

### Issue and Event Branches

Ideally the main branch will always compile, can be loaded onto the robot, gives us a working robot, and contains a record of our best ideas.  Obviously, sometimes we will break things, in which case we will roll back the main branch to the last known good release.  We create a new branch for issues, and a new branch for each event.  During events, we often discover bugs and need to make quick changes which we may or may not want to pull into our main branch.  Once we have an issue branch working and we're agreed it has good ideas in it, we pull it into the main branch.

### Classes

In general, we have one class per subsystem of the robot. Subsystems include the *drive*, which controls the four wheels on the robot platform that allow us to move the robot around the playing field, the *intake*, which controls the mechanism that allows us to pick up game pieces (usually balls), and the *shooter*, which controls the mechanism that allows us to launch balls to score points.  There are additional subsystems depending on the game and the hardware of our robot.

### IDEAS and ROADMAP (New this year)

This year we will be adding new files to our repo to document our ideas and plans.

* We will have an **IDEAS folder** with a file for each coder on the team for you to write down ideas related to the code -- these can be algorithms you want to try, the "big picture" behind the way you implemented your code, or anything else that explains what you were thinking when you were working on the team code.  This is also a good place to jot down questions that you can answer later.  Use this folder for brainstorming and research and keeping track of different things you're trying.

* We will put group decisions about code we plan to implement in a **ROADMAP file**.  Unlike the IDEAS folder, which is for brainstorming and researching ideas, the ROADMAP is for recording design decisions and goals we're committed to achieving as a team.

The IDEAS and ROADMAP are in addition to comments we write in the code itself, and are also in addition to the GitHub issues we use to track bugs and feature requests.  The ROADMAP will have the overall plan; the GitHub issues will track details as we accomplish milestones in our ROADMAP.

## Glossary

Term | Definition
-----|-----------
ARM chip | The [ARM family of reduced instruction set computing processors](https://en.wikipedia.org/wiki/ARM_architecture) is is one of the two major classes of microcomputer architectures (the other being the [x86 family](https://en.wikipedia.org/wiki/X86)).  A compiler converts our Java code to a series of instructions that the ARM chip on our roboRIO can understand.
controller area network (CAN) bus | The [CAN bus](https://docs.wpilib.org/en/stable/docs/hardware/sensors/serial-buses.html#can-bus) is a serial communications protocol designed to allow devices to communicate directly with each other.  For example, the roboRio and the power distribution panel on our robot can send information to each other over the CAN bus.
central processing unit (CPU) | The central processing unit is an electronic device inside every computer or computerized piece of equipment that receives signals, performs logic operations, and transmits signals based on the results.  The main CPU of our robot is inside the roboRIO.  Some devices on our robot might have their own CPUs to allow those devices to be "smarter" so they can perform their own sequences of logic operations, allowing us to offload some calculations from the roboRIO to those devices.
dashboard | A dashboard shows us what's going on with our device.  There are severl different dashboards we can use to get a visual overview of what our code is doing: [LabVIEW Dashboard (Windows Only)](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#labview-dashboard-windows-only), [SmartDashboard](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#smartdashboard), [Shuffleboard](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#shuffleboard) and [Glass](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-software.html#glass).
drive team | Our drive team remotely controls our robot during competition (and practices).  During play we will have two humans with joysticks providing operator input via radio signals to the robot. In addition, we usually have a coach watching the field of play to help the people on the joysticks know what to do, and a human player whose role depends on the game rules.  In some games, the human players may drop game pieces onto the field.
input / output (I/O) | Input is information coming in to the CPU; output is information going out of the CPU.  This is accomplished by varying the voltage of circuits to set the value of "pins" which are the termination points of electrical wires between different electronic components of the robot.  Usually, setting voltage high on a pin means "1" or "true" and setting voltage low means "0" or "false."  A sequence of values, sampled at regular time intervals, transmits information.
loop overrun | This happens when our code tries to do too much in the limited time available for each main event loop.  Unlike most software programs, which can take as much time as they want to complete a task, the code we're writing is running on a real-time operating system that is controlling a machine moving quickly through space.  Things need to happen on a predictable and dependable schedule.  For example, we may need to send signals to eight motors to send the robot in the right direction at the right speed.  The robot won't work right if our code is so complicated that our robot only has time each loop to calculate seven of the eight signals we need to send.  The standard loop time for FRC code is 20 milliseconds, i.e. all of the code we put in one loop must complete within 20 milliseconds (1/50th of a second) or a loop overrun will occur.
Hertz (Hz) | Hertz is the unit of frequency.  One hertz is equal to one cycle per second.  The main CPU in our robot operates at 667 megahertz (MHz), which means it can process 667 million instructions per second.
millisecond (ms) | One one-thousandth of a second.  It's important to understand how much our robot can do in a millisecond.  The standard FRC loop time is 20 milliseconds, or 2 hundredths of a second, or 50 loops per second (50 Hz).  Since our CPU runs at 667 MHz, that means that our CPU can process roughly 10 million instructions per loop.  Different input / output (I/O) ports run at different rates, which is useful to understand.  For example, the roboRIO CAN bus typically uses a clock frequency of 16 MHz, which means our CPU can do 40 cycles between every time the CAN bus signal can change, and the CAN bus signal can change 320,000 times per loop.  Depending on the protocol, a bus may need to change the signal many times in order to transmit one bit of information (for example, the bus protocol may require a sequence of changes to establish the address of the device to receive the information, followed by a sequence of changes that includes a checksum so the receiver can verify that the information was received correctly).  The roboRIO CAN bus transmits one million bits of information per second (1 Mbps), so each loop the CAN bus can transmit 20,000 bits of information.
operator input (OI) | Throughout our codebase, OI means operator input from our drive team using two joysticks, one for our driver and one for our operator.
power distribution panel (PDP) | We can check the CAN bus to get information from the [power distribution panel (PDP)](https://docs.wpilib.org/en/stable/docs/software/can-devices/power-distribution-panel.html) about our robot's power situation, including current temparature, total current draw, and the draw of each device power channel.  This helps us manage our energy use intelligently so we can keep our robot running to win games.
repo | Short for repository, this is a collection of code that you can check out and check in as a unit.  The code for each robot is stored in a separate repo.
roboRIO | The [roboRIO](https://docs.wpilib.org/en/stable/docs/software/roborio-info/roborio-introduction.html) is the "brain" of our robot.  It is essentially a special-purpose computer designed for controlling robots.  Our team has several "[roboRIO 1.0](https://www.andymark.com/products/ni-roborio)" devices, which have now been discontinued; an upgraded "[roboRIO 2.0](https://www.firstinspires.org/robotics/frc/blog/2021-ni-guest-blog-roborio2-0)" is in the works from the company that makes them.  A roboRIO 1.0 includes a dual-core [Xilinx Zynq Z-7020](https://www.xilinx.com/content/dam/xilinx/support/documentation/selection-guides/zynq-7000-product-selection-guide.pdf) [ARM chip](https://en.wikipedia.org/wiki/ARM_architecture) running at 667 MHz, 256 MB of RAM and 512 MB of non-volatile memory.  A large number and type of ports are built in, as well as a 3-axis acceleromter.  The roboRIO 2.0 adds an SD card slot and promises an increase in processor speed and memory.
unit testing | One of the best ways to prevent having to debug too many issues at once is to do [unit testing](https://en.wikipedia.org/wiki/Unit_testing).  This means breaking down what our code should do into small, discrete pieces that can be tested one at a time by automated tools.  Then, when a change is made, these tests can be run to see if it breaks anything.
VS Code | Visual Studio Code, an integrated development environment for writing software.  This combines a programming editor with syntax highlighting, plus tools for revision control, as well as building, running and debugging code.
version control | Also called "revision control," this is a system for keeping track of changes to a project. GitHub is the host we use for version control, and VS Code is one of the client programs we use to check out and check in code stored on GitHub.  All changes to our code are tracked so that you can see exactly what changed and who changed it between versions.
WPILib | This is the library of code that we use to control our robot.  Rather than reinventing the wheel, we start with code that other people have developed, and add our own enhancements to control the hardware we build.  WPI stands for the [Worcester Polytechnic Institute](https://www.wpi.edu/) in [Worcester, Massachusetts](https://en.wikipedia.org/wiki/Worcester,_Massachusetts).