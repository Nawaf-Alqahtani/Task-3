# Task-3 Use another ROS robot whit SLAM approach to create and save a map.

I used a Quadruped Robot Controller for this task and I simulated and wrote commands for this bot to create a map and then save it.


1. Installation:

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
 
 ![Screenshot 2021-07-06 200719](https://user-images.githubusercontent.com/85695324/124640337-f19ca380-de95-11eb-9a06-b229336678e0.png)

![Screenshot 2021-07-06 201952](https://user-images.githubusercontent.com/85695324/124641927-e3e81d80-de97-11eb-847a-4630bf5be461.png)


   And this is the saved map after simulation : 
   
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
   
   ![Screenshot 2021-07-06 200719](https://user-images.githubusercontent.com/85695324/124640337-f19ca380-de95-11eb-9a06-b229336678e0.png)
   
   ![Screenshot 2021-07-06 202115](https://user-images.githubusercontent.com/85695324/124642195-3de8e300-de98-11eb-8fea-8096ff4bd873.png)
   
  And this is the saved map after simulation :
   
   ![image](https://user-images.githubusercontent.com/85695324/124598035-db2e2200-de6c-11eb-8149-bb0d38c45710.png)


