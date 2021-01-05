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

### 2.4 Environment Variables in Gazebo

[Environment Variables]() are variables whose values are valid throughout the system and are used by different applications and the OS for several purposes. These environment variables can contain different types of things ranging from parameter values to paths to certain files depending on what they are used for. Gazebo uses various such environment variables too. These variables and their uses are described below:

* **GAZEBO_MODEL_PATH :** This environment variable contains colon-separated paths to different directories where gazebo will search for models. Models refers to the sdf file describing the robot. For more information on this refer to the [Robot Description]() section of the handbook.
  &nbsp;
* **GAZEBO_RESOURCE_PATH:** This environment variable contains colon-separated set of directories where Gazebo will search for other resources such as world and media files. For eg. if you run the command `gazebo worlds/pioneer2dx.world`. You will see gazebo window pop up with an empty environment. In fact you can execute this command in any directory. You might ask how does gazebo know where the `worlds`  directory is stored?. The answer is that the path to the world directory, that is `/usr/share/gazebo-7/worlds` is stored in the environment variable `GAZEBO_RESOURCE_PATH`.
&nbsp;
* **GAZEBO_MASTER__URI:** [URI]() of the [Gazebo master](). This specifies the IP and port where the server(gzserver) will be started and tells the clients(gzclients) where to connect to.
&nbsp;
* **GAZEBO_PLUGIN_PATH:** colon-separated set of directories where Gazebo will search for the plugin shared libraries at runtime. Plugins are basically..... You can refer to [this]() section to read more about gazebo plugins.
&nbsp;
* **GAZEBO_MODEL_DATABASE_URI:** URI of the online model database where Gazebo will download models from.

The default values of these environment variables are stored in the `<install_path>/share/gazebo/setup.sh` file. If you want to change the values of this variables for example, add or remove a path from `GITHUB_MODEL_PATH` you will have to source this file first using the command

`source <install_path>/share/gazebo/setup.sh`

Once this is done you can edit that value of the variable by editing the value by opening the `setup.sh` file or directly thorugh the terminal/command line using the command:

`GITHUB_MODEL_PATH=$GITHUB_MODEL_PATH:<path of the directory you want to add>`