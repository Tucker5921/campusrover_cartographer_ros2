# Campuserover Cartographer

## Installation
``` bash
# install dependencies
sudo apt-get update
sudo apt-get install -y python3-wstool python3-rosdep ninja-build stow

# setup the ros workspace
mkdir ~/campusrover_cartographer_ws
cd ~/campusrover_cartographer_ws
wstool init src

# clone source code
cd ~/campusrover_cartographer_ws/src
git clone -b ubuntu20.04 git@github.com:IC-lab-campusrover/campusrover_cartographer.git
cd ~/campusrover_cartographer_ws
wstool update -t src

# Install ROS dependencies
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y

# abseil-cpp library 
src/cartographer/scripts/install_abseil.sh
sudo apt-get remove ros-${ROS_DISTRO}-abseil-cpp

# Build and install
catkin_make_isolated --install --use-ninja

# add into .bashrc
echo "source ~/campusrover_cartographer_ws/install_isolated/setup.bash --extend" >> ~/.bashrc
```