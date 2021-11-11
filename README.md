# RAD-System-Roadless-Automated-Driving-

# ELECENG 4OI6 Proposal Report:

# Roadless Autonomous Driving (RAD)

```
Nathen Mathew (400074896)
Arij Saleem ( 400079175 )
Salman Khalid ( 400074802 )
Nathan Gomes (400074393)
```

### Executive Summary

The goal of Roadless Autonomous Driving (RAD) is to create a semi-autonomous, driver assistance system
for a scale autonomous vehicle. This system will aid drivers in both off-road and non-ideal weather conditions
capable of classifying objects, material, and pathway profiles, training a machine learning model to advise the
driving trajectory, and finally executing the suggested pathway.

### Objective and motivation

The RAD system will be designed to aid drivers in limited ‘off-road’ and non-ideal driving conditions, which
is not typically seen in applications of consumer vehicles. To begin, we will define ‘off-road’ pathways as a travel
route which contain:

- Road protrusions: variations in surface features ranging from pebbles, small rocks to larger protruding
    boulders
- Road cavities: pockets indentations of the roads of sizes ranging in depth and size, aka potholes. Capable
    of inadvertently changing vehicle trajectory/stability/passenger comfort if not avoided or
- Non-paved roadways, with possible changes in roadway topology such as pitch, roll

Likewise, we will define ‘non-ideal’ driving conditions as:

- Environmentally caused impedances where drivers may not be able to discern road/track paths on
    otherwise government regulated/safe roads
       o Heavy/fresh snowfall, concealing painted road/lane marks
       o Extreme rain downpour impeding visibility

Fulfilling this object would provide a solution where an unexperienced off-roading driver operating the RC vehicle
will be aided in traversing rough terrain (provided the vehicle powertrain, suspension and mechanical features will
not be a limitation). Likewise, the driver operating the vehicle in simulated non-ideal weather conditions will be
assisted in safe navigation of a roadway where clear distinction of painted line may not be visible.

### Background

Advanced driver-assistance systems have been increasingly incorporated into design and expectations of
consumer vehicles. Industry focus (aided by government regulations to create safer vehicles) has been to improve
driving experience, convenience, and safety since automobiles have been adopted by majority of the population.
Mass production of Electronic Cruise Control appeared mid 1980 (1) and is now a standard convenience and safety
feature expected. Followed by Adaptive Cruise Control, where vehicle speed is reactive to external vehicles/objects
entering range of host vehicle sensors (early 2000’s), were typically Laser or Radar based. The latest features on
luxury brands have been semi-autonomous suites which
combine the increasingly use of perception hardware,
processors, and extensively designed software’s to
automize a large portion of the driving experience.
Society of Automotive Engineers (SAE) defines a
“Levels of Driving Automation” to standardize levels of
driving automation capable in vehicles (2). Majority of
past and current technologies (including GM Super
Cruise, Tesla Autopilot) implemented in vehicles bring
Level 2 Autonomy, as they operate **_under limited
conditions._** Operation of these systems are often


constrained to ideal situations where vehicle sensors can, with excellent confidence, detect painted lines, posted
signs and other near-proximity features. As automakers explore the boundaries of Level 3-5 autonomy for
consumer vehicles, driver assistance technologies will have to improve their capabilities within harsher, non-ideal
environments, whether it be intentional when drivers choose to take their vehicles off regulated/government
managed roads, or when forces of weather reduce a current driver-assist capabilities of navigation on any road.

### Technical Approach

The approach towards developing our autonomous off-road vehicle project will be split up into 3
segments: Road Classification, Navigation, and Vehicle Control. These segments will involve modifications and
additions to an RC car (or equivalent) to convert it into a viable autonomous off-road vehicle.

For Road Classification, the proposed system will work with various sensors to identify the type of terrain
that the vehicle is traversing, construct a proximity environment model and to identify any potential obstacles
that may impede motion. The sensor suite is envisioned with some combination of stereo/thermal cameras,
LiDAR, and accelerometers. The hardware will provide sensory data as inputs to machine learning models that
will be trained to solve the perception problem. The output of these software models would provide information
such as waypoint identification, object detection and surface classification.

The Navigation segment would act as a data processing unit for the vehicle. It would receive information
from the Road Classification segment as well as potential user inputs and utilize it as input data to perform
various functions such as path planning, position/velocity estimations and road roughness predictions. The output
of these functions would serve as the control signals for the vehicle.

The Vehicle Controller segment would serve to control the velocity, yaw (direction/turn) and suspension
of the vehicle. Measurement sensors will be used to track the actual output values and to feed them back into
their respective controllers. Actuation will depend on the type of prototype vehicle the team is able to secure.
Either an on-board controller will aim to interface directly with the vehicles control circuitry, or wireless control
will be implemented using a provided wireless controller.

The output is required to have extremely low latency in the design, this can be actualized by either using
an embedded system or possibly an FPGA, to make it where the data can be processed very fast and in real time.
To implement our machine learning model, a on the fly inference devices such as the Google Edge TPU can be
used in our design.

An initial block diagram has been created to provide an overview of how the system can look following
the completion of this project. As research pieces, work items and discussions with supervisors are completed,
the scope and functionality of the project is subject to change.


We are also considering creating a user interface which displays the decisions made by the machine
learning model in real time. This UI would act in real time and could be coded in C++ with the use of the QT UI
toolkit, C++ because we would want the application to run fast and in real time with low latency. An alternative could be Java.

The ISO 26262 functional safety standard will be considered in every step of the design process.

### Resources

The team will retrofit an RC truck (or equivalent) with a sensor suite (stereo/thermal cameras, LiDAR,
accelerometers, encoders, suspension actuators, as well as microcontroller(s) or microprocessor units. Subject to
change, this constitutes majority of hardware requirement necessary for achieving “gold” deliverable. Software use
will mainly revolve around machine learning and computer vision open-source libraries. OpenCV is currently the
top contender for the computer visions software. Machine learning libraries options include TensorFlow and
PyTorch, tentative to change. Remaining supporting software systems will be custom solutions for the specific goal
or provided with purchased hardware components.

Majority of projects costs are expected to be attributed with hardware resources. The team has agreed
upon a self-funded budget of $800. This provides margin to purchase hardware components and contingency
funds in case of component failures or other emergency situations that may arise.

To accomplish the project, theoretical knowledge required includes machine learning, computer vision,
sensor integration and control system design. Team members will leverage experience (academic, professional,
and extracurricular), alongside self-directed research to successfully complete the project. The team has decided
each member allocates 10 hours of work per week to the project. This time can be accounted through activities
such as research, coding, testing, and discussions with team-members/mentors/supervisors, etc.

### References

```
(1) https://www.researchgate.net/publication/254053485_Advanced_Driver_Assistance_Systems_-
_Past_present_and_future
(2) https://www.sae.org/news/press-room/2018/12/sae-international-releases-updated-visual-chart-for-its-
%E2%80%9Clevels-of-driving-automation%E2%80%9D-standard-for-self-driving-vehicles
```

