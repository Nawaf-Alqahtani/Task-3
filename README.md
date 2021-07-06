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
source <catkin_ws>/devel/setup.bash


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

   I click '2D Nav Goal'.

   I click and drag the position i want the robot to go.
    
    
![map ](https://user-images.githubusercontent.com/85695324/124625455-7da6cf00-de86-11eb-8cd2-1ea2e17ca8a2.png)


   Save the map by running:

   roscd champ_config/maps
   rosrun map_server map_saver

2.3 Autonomous Navigation:
2.3.1 Run the Gazebo environment:

roslaunch champ_config gazebo.launch 

2.3.2 Run amcl and move_base:

roslaunch champ_config navigate.launch rviz:=true

To navigate:

   I click '2D Nav Goal'.

   I click and drag the position i want the robot to go.
   
   ![image](https://user-images.githubusercontent.com/85695324/124598035-db2e2200-de6c-11eb-8149-bb0d38c45710.png)

