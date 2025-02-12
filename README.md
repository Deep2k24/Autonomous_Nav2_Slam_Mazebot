# Autonomous_Nav2_Slam_Mazebot
Autonomous Navigation with Nav2 in Gazebo

Setup Instructions

1. Extract the Package
First, unzip the package in your ROS 2 workspace:
unzip your_ros2_package.zip -d ~/your_ros2_workspace/src

2. Build the Package
Navigate to your ROS 2 workspace and build the package using colcon:
cd ~/your_ros2_workspace
colcon build

3. Source the Workspace
After building, source your workspace to use the package:
source ~/your_ros2_workspace/install/setup.bash

To automatically source it every time you open a new terminal, add the following line to your ~/.bashrc file:

echo "source ~/your_ros2_workspace/install/setup.bash" >> ~/.bashrc
source ~/.bashrc

4. Launching the Simulation
Open four terminals and execute the following commands:

Terminal 1: Launch the Robot Description
ros2 launch navigation_bot_description new_display.launch.py use_sim_time:=True

Terminal 2: Launch Navigation Stack
ros2 launch nav2_bringup bringup_launch.py use_sim_time:=True map:=maps/maze.yaml

Terminal 3: Start RViz
ros2 run rviz2 rviz2 -d /opt/ros/humble/share/nav2_bringup/rviz/nav2_default_view.rviz

Terminal 4: Set Initial Pose
ros2 run navigation_bot_description initial_pose

