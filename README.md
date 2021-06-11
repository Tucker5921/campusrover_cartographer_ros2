# Campuserover Cartographer

## Installation
``` bash
# install dependencies
sudo apt-get update
# If below Ubuntu 18.04
sudo apt-get install -y python-wstool python-rosdep ninja-build stow
# If Ubuntu 20.04
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
# [optional] do it if you not did not run this before
sudo rosdep init 
rosdep update
rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y

# abseil-cpp library 
src/campusrover_cartographer/cartographer/scripts/install_abseil.sh
sudo apt-get remove ros-${ROS_DISTRO}-abseil-cpp

# Build and install
catkin_make_isolated --install --use-ninja

# add into .bashrc
echo "source ~/campusrover_cartographer_ws/install_isolated/setup.bash --extend" >> ~/.bashrc
```