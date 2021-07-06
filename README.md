# Task-3 Use another ROS robot whit SLAM approach to create and save a map.
1. Installation
1.1 Clone and install all dependencies:

sudo apt install -y python-rosdep
cd <your_ws>/src
git clone --recursive https://github.com/chvmp/champ
git clone https://github.com/chvmp/champ_teleop
cd ..
rosdep install --from-paths src --ignore-src -r -y
