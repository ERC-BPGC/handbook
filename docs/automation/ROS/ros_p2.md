## ROS Parameters and Parameter Server

Parameter server is a collection of values or parameters that can be retrieved or modified by the nodes during runtime upon requets through command prompt, nodes or launch files. Parameters are intended to be static, globally available values like integers, floats, strings and boolen values. Parameters are meant to be gloablly viewable so nodes can easily inspect the configuration state of the system and modify if necessary.

### Accessing and setting Parameters
#### Via command line 
Parameters can be accessed, modified or deleted using the `rosparam` command line utility in the `rosbash` suite of terminal commands.
1) To list all the parameters : <br/> 
    ```rosparam list```
    
   Or to list all the parameters in a specific namespace : <br/> 
    ```rosparam list </namespace>```
    
2) To assign a value to an already existing parameter or to set a new one : <br/>
    ```rosparam set <parameter_name> <parameter_value>```
    
3) To get/read a parameter value : <br/>
    ```rosparam get <parameter_name>```
    
    
  
