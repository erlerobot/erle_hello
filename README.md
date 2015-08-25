# erle_hello

HELLO ERLE!

##ABOUT ROS2
Version 2.0 of the Robot Operating System (ROS)

Follow https://github.com/ros2/examples/wiki to setup the development environment.

##COMPILATION
Build the prototype using the bootstrap script from ament_tools:
```
cd ~/ros2_ws/
src/ament/ament_tools/scripts/ament.py build --build-tests --symlink-install
```
On build run the binaries talker_erle and listener_erle in different terminal windows:
```
./talker_erle
./listener_erle
```
