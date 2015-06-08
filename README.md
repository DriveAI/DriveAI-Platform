# DriveAI Platform

DriveAI Platform is a project designed to bring together

* LIDAR
* Stereo Vision
* Vehicle Actuation

To create a fully autonomous vehicle.

The platform is built on top of the Robotic Operating System commonly known as ROS.
The following is our compartmentalization of our problem, in the form of different ROS Nodes.

* Perception: Responsible for collecting raw data from our sensors. Performing object recognition, and giving said objects to the Path-Planning.
* Navigation: Responsible for keeping track of where the car is with respect to public roads, and calculating the most optimal path from point A to point B. Then conveying that information to Path-Planning
* Path-Planning: Responsible for taking Perception and Navigation information and sending commands to the Actuation node to actually actuate the vehicle.
* Actuation: Responsible for actuating the vehicle based on simple inputs.

## Requirements
This list of requirements will grow as our hardware needs become increasingly specific.
* USB 3.0
* Ubuntu 14.04 LTS x64

## Download
```bash
git clone --recursive https://github.com/DriveAI/DriveAI-Platform.git
git submodule foreach git checkout master
git submodule foreach git pull origin master
```

## Setup
```bash
cd DriveAI-Platform
sh Tools/InstallScripts/install-ros.sh
source /opt/ros/indigo/setup.<sh|zsh|bash>
source devel/setup.<sh|zsh|bash>
```

## Compile
We are currently in the process of rapidly prototyping our platform. Currently the most meaningful thing someone can run is our tests.
```bash
catkin_make utest
```

## Running our tests
There are four ROS Packages:
You can run their tests with the following syntax:
```bash
rosrun <Package-Name> utest
```
