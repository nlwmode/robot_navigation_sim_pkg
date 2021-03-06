# robot_navigation_sim_pkg

This is a package that can realize 2D navigation in gazebo.

# Configure your compute !

the operator system is ubuntu 16.04.

- **step1 :**  This package is heavily dependent on ROS, before this ,you should install ros from [ROS](http://wiki.ros.org/cn/)
- **step2 ：** This package is mainly use [ros-navigaiotn package](http://wiki.ros.org/cn/navigation),you can install it by :

```
sudo apt-get install ros-kinetic-navigation*
```

- **step3 :** For gazebo and ros interaction , you should install the [gazebo-ros packages](http://wiki.ros.org/gazebo_ros_pkgs) , and also the robot description package:

```
sudo apt-get install ros-kinetic-gazebo*
```

# How to run !

- step 1: git clone the pkg
``` 
git clone https://github.com/nlwmode/robot_navigation_sim_pkg.git

cd robot_navigation_sim_pkg

catkin_make

source devel/setup.bash
```
- step 2: this step start up gazebo and rviz for innitialization.

```
roslaunch delivery_robot_navigation initialization.launch
```
- step 3:using gmapping for mapping

```
roslaunch delivery_robot_navigation gmapping.launch
```
- step 4: move the robot (Make sure the mouse optical center is in the current terminal window):
```
rosrun teleop_twist_keyboard teleop_twist_keyboard.py 
```
- step 5: save the map:

```
cd YOUR_WORKPLACE/robot_navigation_sim_pkg/src/delivery_robot_navigation/maps
rosrun map_server map_saver -f map_beihang
```
-- step 6: using move_base for navigation:
```
roslaunch delivery_robot_navigation navigation.launch
```

