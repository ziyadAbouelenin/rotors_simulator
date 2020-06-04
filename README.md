# Rotors_Simulator
RotorS is a UAV gazebo simulator

Installation Instructions - Ubuntu 16.04 with ROS Kinetic and Gazebo 7
---------------------------------------------------------
 1. Install and initialize ROS kinetic desktop full, additional ROS packages, catkin-tools, and wstool:

 ```console
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
$ sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
$ sudo apt-get update
$ sudo apt-get install ros-kinetic-desktop-full ros-kinetic-joy ros-kinetic-octomap-ros ros-kinetic-mavlink python-catkin-tools protobuf-compiler libgoogle-glog-dev ros-kinetic-control-toolbox
$ sudo rosdep init
$ rosdep update
$ echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
$ sudo apt-get install python-rosinstall python-rosinstall-generator python-wstool build-essential
 ```

 2. If you don't have ROS workspace yet you can do so by

```console
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/src
$ catkin_init_workspace  # initialize your catkin workspace
$ cd ~/catkin_ws/
$ catkin init
$ cd ~/catkin_ws/src
$ git clone https://github.com/ziyadAbouelenin/rotors_simulator.git
$ cd ~/catkin_ws
$ rosdep install --from-paths src -i
$ catkin build
```


 3. We would also like to use the demos with an external state estimator, so the following additional packages are needed:

```console
$ cd ~/catkin_ws/src
$ git clone https://github.com/ethz-asl/ethzasl_msf.git
$ git clone https://github.com/ethz-asl/rotors_simulator_demos.git
$ git clone https://github.com/ethz-asl/glog_catkin.git
$ git clone https://github.com/catkin/catkin_simple.git
$ cd ~/catkin_ws /
$ catkin build
```
 4. Add sourcing to your `.bashrc` file

```console
$ echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```
>**Note* if you are missing autoconfig
```console
$ sudo apt-get install autoconf
```

