# Udacity Nanodegree - Robotics Software Engineer - Project2

This is my project submission for Project2: Go Chase It! of [Udacity Nanodegree - Robotics Software Engineer](https://www.udacity.com/course/robotics-software-engineer--nd209?irclickid=U9u1PgV1xxyIROOV3m3wlTMuUkD0yqTMORvH3A0&irgwc=1&utm_source=affiliate&utm_medium=&aff=2298976&utm_term=&utm_campaign=__&utm_content=&adid=786224).

## Summary of tasks
In this project, you should create two ROS packages inside your catkin_ws/src: the drive_bot and the ball_chaser. Here are the steps to design the robot, house it inside your world, and program it to chase white-colored balls:

1. `drive_bot`:
    - Create a my_robot ROS package to hold your robot, the white ball, and the world.
    - Design a differential drive robot with the Unified Robot Description Format. Add two sensors to your robot: a lidar and a camera. Add Gazebo plugins for your robot’s differential drive, lidar, and camera. The robot you design should be significantly different from the one presented in the project lesson. Minimum required changes are adjusting the color, wheel radius, and chassis dimensions. You can also completely redesign the robot model!
    - Create a new world, which is different from the world you built in the Build My World project and house your robot inside that world.
    - Add a white-colored ball to your Gazebo world and save a new copy of this world.
    - The world.launch file should launch your world with the white-colored ball and your robot.

2. `ball_chaser`:
    - Create a ball_chaser ROS package to hold your C++ nodes.
    - Write a drive_botC++ node that will provide a ball_chaser/command_robot service to drive the robot by controlling its linear x and angular z velocities. The service should publish to the wheel joints and return back the requested velocities.
    - Write a process_image C++ node that reads your robot’s camera image, analyzes it to determine the presence and position of a white ball. If a white ball exists in the image, your node should request a service via a client to drive the robot towards it.
    - The ball_chaser.launch should run both the drive_bot and the process_image nodes.

## Usage
1. Copy the ball_chaser and my_robot folders into your workspace
2. `catkin_make` your workspace
3. Remember to source the setup.bash of your workspace
4. Launch the world and ball_chaser nodes
    ```
    roslaunch my_robot world.launch
    roslaunch ball_chaser ball_chaser.launch
    ```
5. On Gazebo simulator, put the white ball in front of the robot and observe.