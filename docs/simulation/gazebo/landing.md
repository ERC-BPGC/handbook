# Gazebo

Gazebo is the most popular physics simulator (meaning you can model laws of physics in it) for robotics development. It can simulate robots in a
3D environment and can be fully integrated into ROS integrated with Gazebo using the
**gazebo_ros** ROS package. You can interface your robots in the simulation using ROS
and control them using ROS messages and services.

### 2.1 Installation

Gazebo and gazebo_ros package are both automatically installed when you install ROS. To make sure you have all the
ROS packages necessary for running Gazebo simulations are installed

`sudo apt-get install ros-melodic-gazebo-*`

Gazebo can also be installed independently of ROS by using the command 

`curl -sSL http://get.gazebosim.org | sh`

in the terminal for Ubuntu. Alternative methods of installing gazebo and installation guides for installling gazebo on other operating systems can be found [here](http://gazebosim.org/tutorials?cat=install).

### 2.2 Getting Started

You can launch the Gazebo GUI simulator window by just running the command `gazebo`
in the terminal. 



