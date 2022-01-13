Fred's Robotics Research

# Interesting Code from Other FRC Teams

# My Thoughts
Once object detection works, robots can do much more autonomously.

# Interesting Articles

[Vision AI hardware for software developers](https://stackoverflow.blog/2021/12/08/vision-ai-hardware-for-software-developers/)

## Geometry Classes

The [2019-2020 Team 254 FRC Programming Workshop Series by Sumi Govindaraju '20](https://drive.google.com/drive/folders/1tZ6xdn-xzFpcAzW3VB5ttzQwuhUmvPJB) has some good info.

[Workshop #5: Autonomous Driving/Computer Vision By Sumi Govindaraju ‘20, Software Director](https://docs.google.com/presentation/d/1dmXfUdLesKGygx7IMIfH3ofiNyfo8EW0S_lpEBMNQ0A/edit#slide=id.gc6f73a04f_0_5) explains geometry classes:

 - Translation2d(x, y)
 - Rotation2d(theta)
 - Pose2d p = new Pose2d(Translation2d t, Rotation2d r)
 - "Add" positions using class.transformBy()
 - "Subtract" positions using class.inverse()
 - Twist2d(dx, dy, dtheta)

Examples use variables named "field_to_robot" and "field_to_vision."  These would be better named "origin_to_robot" and "origin_to_vision."  Field of play starts at origin (0,0) in the near right corner.  Moving forward from the origin is +x and moving left from the origin is +y.  This is counter intuitive to me.  I would put the origin in the near left corner and make moving right +x and moving forward +y.

Rotation standard appears to be that +theta turns left (counter clock wise).  Again, this is counter intuitive to me.  I would make turning right (clockwise) +theta.

We should confirm that the FRC standard is origin is near right corner of field with robot heading due north (along x axis), and +x moves away, +y moves left and +theta turns left.

Using these classes, we can define a Pose2d that is the current position and heading of the robot on the field relative to its starting position (origin_to_robot).  We can define a Twist2d that is the delta between two poses.

Can change frame of reference and keep track of other positions, such as robot_to_goal and robot_to_origin (the inverse of origin_to_robot).

Goals are generally stationary relative to origin, but robot moves.  When using image processing to determine positions, need to compensate for latency.  By the time an image has been processed to give us an idea of where we are, we have moved.  Can use odometry to calculate current position relative to position determined by vision system.