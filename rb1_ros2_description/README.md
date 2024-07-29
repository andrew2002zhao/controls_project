# The rb1_ros2_description package

This package provides the controllers for the elevator and the differential drive for a RB1 bot. 

To use this package 

1) clone it from git@github.com:andrew2002zhao/controls_project.git into src/
2) build it with cd ~/ros2_ws/src/ && colcon build
3) source the package with source cd ~/ros2_ws && source install/setup.bash
4) run the package with ros2 launch rb1_ros2_description rb1_ros2_xacro.launch.py
5) when the controllers are dinished installing, use ros2 service call /apply_joint_effort gazebo_msgs/srv/ApplyJointEffort '{joint_name: "robot_elevator_platform_joint", effort: 100.0, start_time: {sec: 0, nanosec: 0}, duration: {sec: 2000, nanosec: 0} }' to lift the shelf
