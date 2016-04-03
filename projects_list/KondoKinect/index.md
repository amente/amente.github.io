---
layout: project
title: "Controlling a Humanoid Robot with Kinect"
description: "Controlling a humanoid robot using Kinect for Windows V2"
group: project
weight: 4
thumbnail: /images/Projects/Kondo_Kinect/setup_200x200.png
status: 'active'
---
{% include JB/setup %}

I worked on this as my third year computer systems development
project course. The topic for the project was a platform for a humanoid robot. With my teammates we designed and programmed a controller for the Kondo KHR-2HV Humanoid Robot kit and added an interface to translate human arm movements gathered using Kinect for Windows V2 sensor to command the robot to mimic the movements.

<iframe width="560" height="315" src="//www.youtube.com/embed/GjveLGeWRgc" frameborder="0" allowfullscreen></iframe>

Kinect for Windows V2 sensor is the latest human body motion and gesture tracking
device manufactured by Microsoft. It includes a built-in 1080p high definition camera bundled
with depth sensors to locate and track human joints in 2D or 3D space. It also has a publicly
available API (Application Programming Interface). Kinect sensor can track up to six people at
the same time and has a detection range from 0.5 to 4.5 meters.

The humanoid robot was assembled from a provided kit which contains 17 servo motors
with a 0-180 degree movement range and the skeleton joints. The 17 motors were controlled by
a robot controller firmware code which translates the degrees into PWM signals. The 17 servos
are wired to a custom designed controller board which integrates several components: an Arm
Cortex M4 (TI Tiva C Launchpad Board), a custom designed shield (booster pack) with a power
supply, and an XBee wireless module. We developed a firmware code in C to parse command
packets from UART and control for the 17 servos using PWM (Pulse-width modulation).

Servo Controller BoosterPack for Tiva C
---------------------------------------
The Servo Controller BoosterPack is designed specifically for the Tiva C launchpad board.
It includes an on board power supply. It also has , accelerometer and gyroscope sensor, XBee radio module and debug LED's.


Firmware Implementation
-----------------------
The firmware code for the Tiva C Launchpad board was developed using Keil MDK and The Cortex Microcontroller Software Interface Standard (CMSIS) standard.
The software implementation can be found <a href="https://github.com/amente/BetterKondo_FW">here</a>

User Software Implementation
---------------------------
The user software is implemented in C#, using Microsoft .NET Framework 4.5. For the
user interface, we used the Windows Presentation Framework (WPF). As mentioned above, the
text-box and slider uses dynamic data binding with GUI control. The source code can be broken
down to three major parts: CommandSender.cs, KinectController.cs, and RobotController.cs.

The CommandSender.cs is a series of classes dealing with command sending functions in
our system. It parses commands and communicate with the robot through serial ports. Basically
it develops the protocols for the system.

KinectController.cs has couple major functionalities like acquiring frame data from the
Kinect, defining the joints and bones for the body, and drawing the bones on the camera feed.
Basically it contains all the functions that involves Kinect sensor.

RobotController.cs is the implementation of the mapping logic for arm movements.  It
relates the four servo motors on the robot to the corresponding joints on the body that is
currently tracked by Kinect. After receiving the location of each joint from the sensor, it
translates the 2D vectors into degrees and sets the relating servo angles into the translated
angles.


The source code for the user software implementation can be found <a href="https://github.com/amente/Kondo_Kinect">here</a>

Technical Challenges
--------------------

Calculating correct angles from joint data obtained from Kinect was initially challenging.
The value of angle generated from Kinect fluctuated dramatically and was quite unstable. Later
on, we discovered the inaccuracy on the angles was because of the way a 3D point from the
Kinect API was mapped into a 2D plane which caused the loss of value on depth.

The Kinect has different types of sensors (Camera, Infrared and Depth) with different
ranges of operation. For this reason, it has three different types of coordinates:

- Camera Space Point: These coordinates are distances measured in meters in the 3D
space in front of the camera.  
- Depth Space Point: These coordinates are 2D points at a given depth away from the
camera, where the person is standing.
- Color Space Point: These are also 2D points but in the pixel array defined by the HD
camera.

In theory, we could use any of those coordinates to calculate angles for the joints of a
person standing in front of the sensor. But in practice, we found that the 2D points work very
well instead of the 3D points from the camera space point.  By using the color space point and
doing some simple 2D vector maths on the points, we were able to get correct angles for both
left and right hand joints.
