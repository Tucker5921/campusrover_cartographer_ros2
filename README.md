# Campuserover Cartographer

## Installation
``` bash
# install wstool
sudo apt-get update
sudo apt-get install -y python-wstool python-rosdep ninja-build

# setup the ros workspace
mkdir ~/campusrover_catographer_ws
cd ~/campusrover_catographer_ws
wstool init src

# clone source code
cd ~/campusrover_catographer_ws/src
git clone git@github.com:IC-lab-campusrover/campusrover_cartographer.git

# Build and install
cd ~/campusrover_catographer_ws/
catkin_make_isolated --install --use-ninja
```