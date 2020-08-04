cr_cartographer
Compiling Cartographer ROS
System Requirements
The Cartographer ROS requirements are the same as the ones from Cartographer.

The following ROS distributions are currently supported:

Indigo
Kinetic
Lunar
Melodic
Building & Installation
In order to build Cartographer ROS, we recommend using wstool and rosdep. For faster builds, we also recommend using Ninja.
```
sudo apt-get update
sudo apt-get install -y python-wstool python-rosdep ninja-build
```
Create a new cartographer_ros workspace in ‘catkin_ws’.
```
mkdir catkin_ws
cd catkin_ws
wstool init src
wstool merge -t src https://raw.githubusercontent.com/
wstool update -t src
```
Install cartographer_ros’ dependencies (proto3 and deb packages). The command ‘sudo rosdep init’ will print an error if you have already executed it since installing ROS. This error can be ignored.
```
src/cartographer/scripts/install_proto3.sh
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y
```

Build and install.

```  
catkin_make_isolated --install --use-ninja
```