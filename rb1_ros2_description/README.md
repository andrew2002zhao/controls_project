# The rb1_ros2_description package

This package provides the controllers for the elevator up/down and the differential drive for a RB1 bot. 


prerequisites

ROS2 humble must be installed beforehand and sourced with 
```
source /opt/ros/humble/setup.bash
```

To use this package 

1) clone it from git@github.com:andrew2002zhao/controls_project.git into src/
2) build with 
```
cd ~/ros2_ws/src/ && colcon build
```
3) source the package with 
```
cd ~/ros2_ws && source install/setup.bash
```

4) run the package with 

```
ros2 launch rb1_ros2_description rb1_ros2_xacro.launch.py
```

To lift the elevator up (assuming the simulation from the previous instructions are running)

1) Wait for the controllers to finish initialization (there should be something along the lines of [spawner]: process has finished cleanly)

2) open another terminal and type 
```
ros2 service call /apply_joint_effort gazebo_msgs/srv/ApplyJointEffort '{joint_name: "robot_elevator_platform_joint", effort: 100.0, start_time: {sec: 0, nanosec: 0}, duration: {sec: 2000, nanosec: 0} }'
```

To lift the elevator down (assuming the simulation from the previous instructions are running)

1) Wait for the controllers to finish initialization (there should be something along the lines of [spawner]: process has finished cleanly)

2) open another terminal and type 
```
ros2 service call /apply_joint_effort gazebo_msgs/srv/ApplyJointEffort '{joint_name: "robot_elevator_platform_joint", effort: 0.0, start_time: {sec: 0, nanosec: 0}, duration: {sec: 2000, nanosec: 0} }'
```
