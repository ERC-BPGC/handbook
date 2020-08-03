# Gazebo

Gazebo is the most popular physics simulator for robotics development. It can simulate robots in a
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
in the terminal. To understand how to spawn robot models in gazebo it is recommended to first get familiar with _.urdf_, _.sdf_ and _.world_ files. You can refer to the [Robot Description]() section to read about these.

A file can be opened simply by running the follwing command in the command line:

`gazebo <path/to/file>`

### 2.3 Client Server Separation

Running the `gazebo` command starts two programmes, namely the **gzserver** and the **gzclient**. The _gzserver_ is responsible for doing most of the 'processing' part, i.e., doing all the calculations for the simulation, sensor data generation, basically all the backend processing. The _gzclient_ is responsible for generating the user interface. It provides a nice visualization of simulation, and convenient controls over various simulation properties. _gzserver_ is capable of running independently of _gzclient_ and vice-versa. For eg; in many cases _gzserver_ is run on a cloud computer in case enough processing power is not available locally. Try running the command `gzserver` in one terminal and the command `gzclient` in other terminal. You will notice that the gazebo window pops up only when you run the `gzclient` command. The term **_run headless_** is used to refer to cases when only the _gzserver_ is being used.

