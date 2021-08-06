# Building-SLAM-map-with-differential-drive-robot
In this repo, I tried to implement a SLAM map of Differential Drive Robot I found [here](https://github.com/devanshdhrafani/diff_drive_bot)
I created a catkin workspace and installed all packages and dependencies as written in the instructions.


After that I launched Gazebo in order to use the world and models to drive the robot:
```
$ roslaunch diff_drive_bot gazebo.launch 
```
I faced issues with launching Gazebo so I edited the config.yaml file and replace the old URL: (https://api.ignitionfuel.org) with the new URL: (https://api.ignitionrobotics.org).

Then launched the SLAM gmapping node:
```
$ roslaunch diff_drive_bot gmapping.launch
```

After that I tried to launch the keyboard_teleop.py to control the robot but did not work at all. So instead, I launched turtlebot3_teleop package and surprisingly worked very well in controlling this robot!
```
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

Finally, I saved the map using:
```
$ rosrun map_server map_saver -f ~/test_map
```

The resulted map:
![test_map](https://user-images.githubusercontent.com/83130573/128512483-7faab353-6719-44db-9f84-580f31260f47.png)
