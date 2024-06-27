# water_navigation

## 1. Create workspace and download the code
```
$ mkdir -p catkin_ws/src
$ cd catkin_ws/src
$ git clone https://github.com/Chris-Arvin/water_navigation.git
$ cd ..
$ rosdep install –from-paths src –ignore-src –rosdistro-melodic -y
$ catkin_make
```

## 2. SLAM the environment
Open a terminal to start SLAM
```
$ source catkin_ws/devel/setup.bash
$ roslaunch water_slam water_slam.launch
```
Open another terminal to control the robot to observe the environment: 
```
$ source catkin_ws/devel/setup.bash
$ roslaunch water_teleop water_teleop_key.launch
```
When completing the SLAM, open another terminal to save the current map:
```
$ rosrun map_server map_saver -f my_map
```

## 4. Navigation
Open a terminal to start navigation
```
$ roslaunch water_navigation water_navigation.launch
```
Select a target in the RVIZ and see the navigation performance!
