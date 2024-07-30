# The rb1_ros2_description package

This package provides the controllers for the elevator up/down and the differential drive for a RB1 bot. 


**prerequisites**

ROS2 humble must be installed beforehand and sourced with 
```
source /opt/ros/humble/setup.bash
```
ROS2 controls must also be installed with instructions for installation at: https://control.ros.org/humble/doc/getting_started/getting_started.html


**To use this package**

1) Clone it from git@github.com:andrew2002zhao/controls_project.git into src/
2) Build with 
```
cd ~/ros2_ws/ && colcon build
```
3) Source the package with 
```
cd ~/ros2_ws && source install/setup.bash
```

4) Run the package with 

```
ros2 launch rb1_ros2_description rb1_ros2_xacro.launch.py
```

**To lift the elevator up** (assuming the simulation from the previous instructions are running)

1) Wait for the controllers to finish initialization (there should be something along the lines of [spawner]: process has finished cleanly)

2) Open another terminal and verify that the /apply_joint_effort service exists with
```
ros2 service list
```

3) Raise the elevator with 
```
ros2 service call /apply_joint_effort gazebo_msgs/srv/ApplyJointEffort '{joint_name: "robot_elevator_platform_joint", effort: 100.0, start_time: {sec: 0, nanosec: 0}, duration: {sec: 2000, nanosec: 0} }'
```

**To lift the elevator down** (assuming the simulation from the previous instructions are running)

1) Wait for the controllers to finish initialization (there should be something along the lines of [spawner]: process has finished cleanly)

2) Open another terminal and verify that the /apply_joint_effort service exists with

```
ros2 service list
```

3) Lower the elevator with 
```
ros2 service call /apply_joint_effort gazebo_msgs/srv/ApplyJointEffort '{joint_name: "robot_elevator_platform_joint", effort: -100.0, start_time: {sec: 0, nanosec: 0}, duration: {sec: 2000, nanosec: 0} }'
```
