---
layout: project
title: "Cansat Competition 2014"
description: "Enviromentally powered atmospheric probe"
group: project
weight: 3
thumbnail: /images/Projects/CanSat/cansat_4_200x200.png
status: 'inactive'
pictures:
- /images/Projects/CanSat/cansat_1.png
- /images/Projects/CanSat/cansat_2.png
- /images/Projects/CanSat/cansat_3.png
- /images/Projects/CanSat/cansat_4.png
- /images/Projects/CanSat/cansat_5.png
- /images/Projects/CanSat/cansat_6.png
- /images/Projects/CanSat/cansat_7.png
- /images/Projects/CanSat/cansat_8.png
- /images/Projects/CanSat/cansat_9.png
- /images/Projects/CanSat/cansat_10.png
- /images/Projects/CanSat/cansat_11.png
- /images/Projects/CanSat/cansat_12.png
- /images/Projects/CanSat/cansat_13.png
---
{% include JB/setup %}

The <a href='http://www.cansatcompetition.com/Main.html'>CanSat Competition </a> is organized annually
by the American Aeronautics and Astronautics Society with featuring sponsors
such as NASA and brings university teams from all over the world to participate by designing,
building and launching a can sized satellite like system.

I led a team of 10 students from Carleton University to take part
in the 2014 annual CanSat Competition. We finished the competition
ranking 8th place out of 36 teams who completed the competition
and 63 teams who registered.

The mission for the 2014 CanSat competition was to design,
build and launch an “Environmentally Powered Atmospheric
Probe”.

The main objectives were:

- Harvest energy from the environment to power the Payload.
- Collect telemetry from both Container and Payload at a
minimum of 1HZ and transmit it to Ground Station.
- Control the descent of the Container and Payload to
altitude-defined speeds.
- Deploy the payload at 500m.
- Keep the egg intact through out the whole trip.

{% include carousel.html %}


The system firmware code is available <a href="https://github.com/amente/cansat_2014_system">here</a>

Also the ground control station software is available
<a href="https://github.com/amente/cansat_2014_gs">here</a>

The critical design review document is available
<a href="http://amente.github.io/images/Projects/CanSat/cansat_2014_cdr.pdf">here</a>

Below is a brief description of the mission and the system.

<img src="/images/Projects/CanSat/cansat_mission_2014.png"/>

The CanSat system has two main modules, The Container and The Payload. The role of the container module is to enclose the payload and release it at an altitude of 500m during decent. The payload module includes a scientific payload which is a large hen egg. The egg has to survive throughout the mission, from launch to final impact.

Both the payload and container included various sensors, and transmit telemetry to ground station
in real time.
This is the sensor subsystem overview:

<img src="/images/Projects/CanSat/sensor_subsystem.png"/>

The sensors were interfaced to FreeScale HC08 MCU, via an I2C bus. We used the MCU inside the
Programmable XBee radio modules. We selected the MCU to reduce our power
requirement and simplify our system. The system also included an EEPROM for logging telemetry data as a backup and a Real Time Clock (RTC) for keeping mission time.

<img src="/images/Projects/CanSat/cdh_subsystem.png"/>

The telemetry packet format was the following:

<img src="/images/Projects/CanSat/telemetry.png"/>

One of the requirements for the mission was to power the payload with energy harvested from the
environment. For our system we used solar panels. The electrical power subsystem was the following:

<img src="/images/Projects/CanSat/eps.png"/>

The flight software (firmware) is an important part of the system. It was designed to be very reliable and simple. Here is the flight software architecture:

<img src="/images/Projects/CanSat/fsw.png"/>

The other important software in the system is the ground station software. The main purpose of this software is to plot the received telemetry data in real time.

<img src="/images/Projects/CanSat/gcs.png"/>
