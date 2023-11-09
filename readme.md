#LD19 DATASHEET
refer the images using below datasheet

https://www.elecrow.com/download/product/SLD06360F/LD19_Development%20Manual_V2.3.pdf

but use below commeds to run lidar real time mapping

# Armbot Navigation Package
This ROS package contains the navigation stack for a custom 4-wheel skid-steer drive robot in Gazebo. The robot is equipped with a 2D-Laser Scanner, a RGBD Camera and an IMU. The purpose of this package is to learn and explore ROS Navigation Stack. The URDF for the robot has a utilitarian design and does not include any mesh files for complex view or geometry. Any one interested with improving the visual aesthetics or geometrical complexity, feel free to do so by modifying the base URDF files.

This project was tested on Ubuntu 20.04 LTS with ROS Noetic. Check the ROS official documentation for the Installation [ROS Installation](http://wiki.ros.org/noetic/Installation/Ubuntu).

## Installation
> Step 1
```
cd ~
mkdir -p ldlidar_ros_ws/src
sudo apt-get install git
```
> Step 2
```
cd ~/ldlidar_ros_ws/src
git clone https://gitee.com/ldrobotSensorTeam/ldlidar_stl_ros.git
```
or
```
git clone https://github.com/ldrobotSensorTeam/ldlidar_stl_ros.git
```
> Step 3
Connect the lidar to system or raspberrypi open a terminal under the ubuntu system and enter --> ls /dev/ttyUSB* 
if Serial port device is detected, in terminal show like /dev/ttyUSB0

>Step 4
```
sudo chmod 777 /dev/ttyUSB*
```
>Step 5
```
cd ~/ldlidar_ros_ws
catkin_make
source devel/setup.bash
```
>Step 6
```
echo source ~/ldlidar_ros_ws/devel/setup.bash >> ~/.bashrc
source ~/.bashrc
```

>Step 7
```
source devel/setup.bash
roslaunch ldlidar_stl_ros ld19.launch
```

>Step 8
open new terminal
```
source devel/setup.bash
rosrun rviz rviz
```
After the interface starts, click file->open->Config in the menu bar of the
interface, then select: ldlidar.rviz file in the ~/ldlidar_ros_ws/src/ldlidar_stl_ros/rviz/
directory, open the configuration file ldlidar.rviz, and click LaserScan Select
/LiDAR/LD19 in the Topic

>Step 9
open new terminal
```
cd ~/ldlidar_ros_ws/src
git clone https://github.com/poovarasanemb/hector_slam.git
cd ~/ldlidar_ros_ws
catkin_make
```
>Step 10
```
source devel/setup.bash
roslaunch hector_slam tutorial.launch
```
