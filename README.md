# Campuserover Cartographer

## Installation
``` bash
# install wstool
sudo apt-get update
sudo apt-get install -y python-wstool python-rosdep ninja-build

# setup the ros workspace
mkdir ~/campusrover_cartographer_ws
cd ~/campusrover_cartographer_ws
wstool init src

# clone source code
cd ~/campusrover_cartographer_ws/src
git clone git@github.com:IC-lab-campusrover/campusrover_cartographer.git

# Build and install
cd ~/campusrover_cartographer_ws/
catkin_make_isolated --install --use-ninja

# add into .bashrc
echo "source ~/campusrover_cartographer_ws/install_isolated/setup.bash --extend" >> ~/.bashrc
```