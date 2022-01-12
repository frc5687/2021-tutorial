# Dennis' Robotics Research

## Teams Of Interest:

 - Team 900 [Zebracorns](https://team900.org/labs/):  Team has pretty complex software that is probably out of the scope of what we want/can do.
 - Team 254 [The Cheesy Poofs](https://www.team254.com/): One of the best teams in the world. Don’t always release software.
 - Team 2910 [Jack in the Bot](https://frcteam2910.org/): Well known swerve team
 - Team 1114 [Simbotics](https://www.simbotics.org/): Another one of the best in the world teams.
 

## Localization & Vision:

### Cameras:
 - Zed camera by Stereolab’s
 - Intel Cameras (discontinued?) Depth, Lidar, Slam, Etc.

### Algorithms for localization:

#### [Kalman Filter Family](https://en.wikipedia.org/wiki/Kalman_filter):
 - Kalman Filter (For Linear Systems)
 - Extended Kalman Filter (Non-linear Systems by linearizations with jacobians.)
 - Unscented Kalman Filter (Non-linear, Sampling technique better than EFK, more computationally expensive)

#### [Particle Filter / Monte Carlo Localization](https://en.wikipedia.org/wiki/Monte_Carlo_localization#Basic_description):
 - Commonly used for indoor localization
 - Computationally expensive as well.

## Reasources:

- [Probabilistic Robotics Textbook](https://docs.ufpr.br/~danielsantos/ProbabilisticRobotics.pdf): has a ton of information about the derivations of multiple types of filters as well as sudo code.
- [Cyrill Stachniss Youtube](https://www.youtube.com/c/CyrillStachniss/playlists):  Professor at University of Bonn has a ton of information relating to robotics, the observation model we can use will stem from his video about observation models.
- [Python Robotics Repo](https://pythonrobotics.readthedocs.io/en/latest/): Has a ton of code written in python. Good for trying to understand some algorithms.
