# Task-3 Use another ROS robot whit SLAM approach to create and save a map.
1. Installation
1.1 Clone and install all dependencies:

sudo apt install -y python-rosdep
cd <catkin_ws>/src
git clone --recursive https://github.com/chvmp/champ
git clone https://github.com/chvmp/champ_teleop
cd ..
rosdep install --from-paths src --ignore-src -r -y


1.2 Build workspace:

cd <catkin_ws>
catkin_make
source <your_ws>/devel/setup.bash


2.1 Walking demo in RVIZ:
2.1.1 Run the base driver:

roslaunch champ_config bringup.launch rviz:=true

2.1.2 Run the teleop node:

roslaunch champ_teleop teleop.launch


2.2 SLAM demo:
2.2.1 Run the Gazebo environment:

roslaunch champ_config gazebo.launch 

2.2.2 Run gmapping package and move_base:

roslaunch champ_config slam.launch rviz:=true

To start mapping:

   Click '2D Nav Goal'.

   Click and drag at the position you want the robot to go.
    
    
