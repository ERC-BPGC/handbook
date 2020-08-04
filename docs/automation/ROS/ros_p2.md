## ROS Parameters and Parameter Server

Parameter server is a collection of values or parameters that can be retrieved or modified by the nodes during runtime upon requests through command prompt, nodes or launch files. Parameters are intended to be static, globally available values like integers, floats, strings and boolean values and can be stored independently or within a YAML file. Parameters are meant to be gloablly viewable so nodes can easily inspect the configuration state of the system and modify if necessary.

### Accessing and setting Parameters
#### Via command line 
Parameters can be accessed, modified or deleted using the `rosparam` command line utility in the `rosbash` suite of terminal commands.
1) To list all the parameters : <br/> 
    ```rosparam list```
    
   Or to list all the parameters in a specific namespace : <br/> 
    ```rosparam list </namespace>```
        
2) To assign a value to an already existing parameter or to set a new one : <br/>
    ```rosparam set <parameter_name> <parameter_value>```
    
    Note : You can also load the parameters into the parameter server from a YAML file using <br/>
    ```rosparam load <filename> <namepsace>```
    
3) To get/read a parameter value : <br/>
    ```rosparam get <parameter_name>```
    
   Note : You can also dump/save the parameters into a YAML file from parameter server using <br/>
    ```rosparam dump <filename> <namespace>```
    
For more insights regarding the `rosparam` tool refer to [this](http://wiki.ros.org/rosparam) link.   
    
#### Via the rospy API library 
Parameters from the parameter server can be accessed and modified using `rospy` API library. This is generally used when the parameters are to be used by a node during the runtime.
Refer [this](http://wiki.ros.org/rospy/Overview/Parameter%20Server) link for more imformation on handling parameters using `rospy` API library.

#### Via launch files
Parameters can be set, created and loaded into the parameter server while creating launch files. Refer to [this](http://wiki.ros.org/roslaunch/XML/param) link ROSWiki for more information on handling parameters in launch files.

Following links can be referred to for more insights on parameters and parameter server [1](http://wiki.ros.org/Parameter%20Server), [2](https://www.clearpathrobotics.com/assets/guides/kinetic/ros/ROS%20Parameter%20Server.html), [3](https://www.cse.sc.edu/~jokane/agitr/agitr-small-param.pdf)

