# Task1
How to install Ros2foxy on the Justin Nano

install-ros2-and-ubuntu20-in-jeston-nano
Install Ubuntu 20.04 and ROS2 in jeston Nano :

1- At first I download ubuntu20 from this site (https://forums.developer.nvidia.com/t/xubuntu-20-04-focal-fossa-l4t-r32-3-1-custom-image-for-the-jetson-nano/121768)

2- then I make extract for Ubuntu file to put it in a (balenaEtcher) website download link (https://www.balena.io/etcher/)

3-when I open ubuntu20 i will install tools for Ros 2 foxy (https://docs.ros.org/en/foxy/Installa...)

4- commands to Set locale: 1-(locale) 2- (sudo apt update && sudo apt install locales) 3- (sudo locale-gen en_US en_US.UTF-8) 4- (sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8) 5- (locale )

-commands to Setup Sources: 1- apt-cache policy | grep universe This should output a line like the one below: 500 http://us.archive.ubuntu.com/ubuntu focal/universe amd64 Packages release v=20.04,o=Ubuntu,a=focal,n=focal,l=Ubuntu,c=universe,b=amd64 If you don’t see an output line like the one above, then enable the Universe repository with these instructions. sudo apt install software-properties-common sudo add-apt-repository universe

Now add the ROS 2 apt repository to your system. sudo apt update && sudo apt install curl gnupg2 lsb-release sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

-commands to Install ROS 2 packages: Update your apt repository caches after setting up the repositories. sudo apt update ROS 2 packages are built on frequently updated Ubuntu systems. It is always recommended that you ensure your system is up to date before installing new packages. sudo apt upgrade Desktop Install (Recommended): ROS, RViz, demos, tutorials. sudo apt install ros-foxy-desktop ROS-Base Install (Bare Bones): Communication libraries, message packages, command line tools. No GUI tools. sudo apt install ros-foxy-ros-base

commands Environment setup: Sourcing the setup script: Set up your environment by sourcing the following file. source /opt/ros/foxy/setup.bash
