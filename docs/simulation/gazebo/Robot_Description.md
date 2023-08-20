# Introduction:
Robot models in gazebo serve as the digital counterparts of physical robots, representing their physical characteristics, kinematics, dynamics, and sensors in a virtual setting. These models play a crucial role in various fields, including robotics research, autonomous systems development, and even educational purposes.
Using Robot Description Formats, roboticists can rapidly prototype and experiment with various robotic configurations without the need for a physical robot. This capability significantly speeds up the development process, allowing for iterative testing, debugging, and fine-tuning of robot designs and control algorithms before deployment on real hardware.
# Model:
- ### URDF:
    In Gazebo, URDF files serve as the foundation for creating robot models. A URDF file contains essential information about the robot's mechanical structure, such as links, joints, sensors, and physical properties like mass, inertia, and collision geometry. Additionally, it can define visual elements, enabling users to visualize the robot accurately during simulations.
    These description files require designs of various components of the robot, hence are usually bundled with a meshes folder having an accessible path. The model files are of the XML format and have the extension `.urdf`; however, if you use macros to clean up the code, it becomes `urdf.xacro`.
    Refer to [roswiki](http://wiki.ros.org/urdf) for more on urdfs.
    There are plugins in various 3d modelling softwares that automatically generate urdfs.
    It can also be done manually. (Using the urdf snippet tool in vscode fast-tracks the process of writing urdfs). Following [tutorials](http://wiki.ros.org/urdf/Tutorials/Building%20a%20Visual%20Robot%20Model%20with%20URDF%20from%20Scratch) would help gain better understanding of its structure, which is imperative for tweaking attributes and on the go customisation. Sometimes, running a software like Gazebo just for visualisation becomes tedious use the URDF previewer that is conveniently part of the ROS extension in Visual Studio Code.

- ### Methods of spawning:
    - ##### Writing a simulation description format (SDF) file:
        - Create a config file.
        - Including meshes(stl,dae) in .sdf file.

    - ##### Importing using gazebo GUI:
        In gazebo, navigate to insert/path look for the mesh(.stl;.dae) file and add its path. The model can be dragged directly into the scene and can further be reloaded using the saved world file.

    - ##### Spawn.urdf in the launch file:
        - Call the spawn.urdf method of the ros_gazebo node from the ros_gazebo package
        ```xml
        <node name="spawn_model" pkg="gazebo_ros" type="spawn_model" args="-urdf -model urdf_assembly6 -param robot_description -z 1.0" output="screen" />
        <!--    model name          urdf          position-->
        ```
        - Position the urdf in 3d space (0 0 1.0)

# Control:
When urdfs are simply spawned into an environment, the joints go limp under the influence of gravity.
ROS (Robot Operating System) Controllers help maintaining a joint state or position and play a fundamental role in controlling robotic systems within the ROS ecosystem. To effectively interact with and control robots, ROS Controllers are employed to handle various aspects of robot behaviour, such as motion control, joint control etc.
The primary objective of ROS Controllers is to abstract the complexities of low-level hardware control and provide a unified interface for developers to command and manage robots. This abstraction allows robot designers and developers to focus on higher-level tasks and algorithms without having to deal with specific hardware details.

- ### Key Components of ROS Controllers:
    - **Hardware Interface**: The hardware interface is a crucial component of ROS Controllers, responsible for communication between the higher-level control system (software) and the robot's actuators (hardware). This needs to be added in the description file under the transmission tag:
        ```xml
           ‘’<transmission name="simple_trans">
           	<type>transmission_interface/SimpleTransmission</type>
           	<joint name="foo_joint">
           	<hardwareInterface>EffortJointInterface</hardwareInterface>
            </joint>’’
        ```
    Refer to [transmission elements](http://wiki.ros.org/urdf/XML/Transmission).
    - **Controller Plugins**: Controller plugins are modular software components that implement different control algorithms and strategies. These plugins receive high-level commands from the user or other ROS nodes and translate them into low-level control signals that the hardware can understand. Some commonly used controller plugins include joint position controllers, joint velocity controllers, and effort controllers.

    **Controller Manager**: The controller manager is responsible for loading and unloading controller plugins and managing their lifecycle. It provides a centralized interface for activating and deactivating controllers based on user commands or the current robot state. It is loaded into the launch file as a rosparam and is a config file in nature with the extension `.yaml`.
    ```xml
  <!-- Load joint controller configurations from YAML file to parameter server -->
    <rosparam file="$(find urdf_assembly6)/config/controllers.yaml" command="load"/>

  <!-- load the controllers -->
    <node name="controller_spawner" pkg="controller_manager" type="spawner" respawn="false"
        output="screen" ns="/manipulator" args="joint1_position_controller joint2_position_controller joint3_position_controller joint_state_controller"/>
    ```

    **Joint State Controller**: The joint state controller is a special type of controller that reads joint states (position, velocity, effort) from the robot's sensors and publishes them to the ROS network. This controller is essential for other controllers that require feedback about the robot's current state.

    **ROS Messages and Services**: ROS Controllers utilize ROS messages and services to receive commands and send feedback to other ROS nodes. This communication mechanism ensures seamless integration with the broader ROS ecosystem.

- ### Types of ROS Controllers:
    - **Position Controllers**: Position controllers are used to set the desired joint positions of a robot. They compute the necessary control efforts to reach and maintain these positions.

    - **Velocity Controllers**: Velocity controllers command the desired joint velocities of a robot. They regulate the joint speeds to achieve the desired motion.

    - **Effort Controllers**: Effort controllers apply specific forces or torques to robot joints, allowing for precise control of joint efforts. This type of control is particularly useful for applications requiring high accuracy and force/torque control.

    - **Trajectory Controllers**: Trajectory controllers enable robots to follow predefined trajectories, smoothly interpolating between waypoints.
# Glossary:
- ***Urdfs(Universal Robot Description Format)***-an xml format defining the attributes(inertial,visual) of a single robot. 
- ***Meshes***- models created using interconnected polygons to create a visual and geometric representation of the robot's structure
- ***SDF(simulation Description Format)***- t is an XML-based file format used to describe the world, objects, and entities in a simulated environment within the Gazebo robotics simulator.
- ***Xacro***-an xml format used to clean up urdfs by handling repetitive code blocks or macros.
- ***Transmission tags***- An extension to the URDF robot description model that is used to describe the relationship between an actuator and a joint.
