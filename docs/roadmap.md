# Roadmap for Robotics

Robotics is a vast field which often overlaps with many other disciplines ranging from machine learning to physics. For a beginner this can be pretty intimidating, we know, we’ve been there. To make it easier to get started, we have collected the following resources. You can also find more resources at our [website](http://erc-bpgc.github.io/).

## A common beginning

As a beginner, the most important thing is to start learning a language since it opens up a lot of opportunities in terms of projects to work on and things to do.  Also keep in mind that once you know one language well, it's relatively easy to pick up another one quickly.

In robotics, different languages have different uses:

1. *Automation*: Machine Learning: python for basic stuff, C++ for more advanced stuff
2. *Embedded systems and electronics*: C
3. *Modelling*: python, MATLAB

We would recommend starting with either **python** or **C/C++**. Knowing both is pretty much essential for advanced robotics. Here are some places where you can get started:

### Python

* [Web tutorial](http://introtopython.org/)
* [Corey Schafer’s video tutorials](https://www.youtube.com/playlist?list=PL-osiE80TeTskrapNbzXhwoFUiLCjGgY7)

### C

* [FreeCodeCamp Video Tutorials](https://www.youtube.com/watch?v=KJgsSFOSQv0)
* [Browser based tutorial](https://www.learn-c.org/)
* [Beej’s Guide](http://beej.us/guide/bgc/html) (follow if you already know programming)

### C++

* [Welcome to C++ Playlist - YouTube](https://www.youtube.com/playlist?list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb)
* [Web tutorial](https://www.learncpp.com/)

### MATLAB & Simulink

* [MATLAB Onramp](https://in.mathworks.com/learn/tutorials/matlab-onramp.html) and [Simulink Onramp](https://in.mathworks.com/learn/tutorials/simulink-onramp.html). These courses introduce you to the MATLAB and Simulink environments. Many other self paced courses can be found [here](https://matlabacademy.mathworks.com/?s_tid=gn_trg_cosp).
* This interesting “[How to](https://www.youtube.com/playlist?list=PLn8PRpmsu08oBSjfGe8WIMN-2_rwWFSgr)” playlist by MATLAB teaches some basics how to’s with MATLAB & Simulink, check out the videos which are required for solving any doubts.
* [Versioning with Git](https://www.youtube.com/watch?v=AJynESuE1dc&list=PLn8PRpmsu08o7pv1tJ7EnEyHVWSU2-OrR&index=5) this video will help with using Git & Version control with your Simulink projects.

## Development Environment

Writing code isn't just as simple as typing into a text editor. Usually there are many other components involved such as a compiler, external libraries, path environments, a terminal, version control, documentation etc… Don't worry if you don't know what these things mean, together they are generally known as your development environment. To begin with, make sure you are comfortable with the following

* *Linux Operating System*: Linux is an open source operating system - this means that anyone can view and propose changes to its source code. It comes in many variants, Ubuntu being the recommended choice for beginners. It's essential to have access to linux (either through [dual booting](https://help.ubuntu.com/community/WindowsDualBoot), [virtual machine](https://itsfoss.com/install-linux-in-virtualbox/) or [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) - more on these [here](https://erc-bpgc.github.io/handbook/automation/ROS/setting_up/)) due to its tight integration with many of the tools used to program robots (and development in general).
* *Linux Terminal*: While most of us are familiar with the point and click based interface of windows, computers first started off as terminals - text based prompts that you had to type into. The terminal is still used for pretty much everything in software development and is an essential skill. [YouTube Tutorial](https://youtu.be/oxuRxtrO2Ag)
* *Git*: When working on complex code, or as part of a team, keeping track of changes to the code becomes very important. Git provides a way to do this and much more. Platforms such as GitHub and GitLab have become the bedrock of the open source community in recent years. [YouTube Tutorial](https://www.youtube.com/watch?v=RGOj5yH7evk)

## Electronics

The Electronics part of Robotics can be divided into 3 parts : Microcontroller, Sensors and Actuators. Sensors and Actuators (through drivers) are interfaced with the microcontroller to form the electronics system of the robot. Basic electronics components like wires, resistors, capacitors are used in interfacing and this whole assembly is mounted on a breadboard, prototyping board or a printed circuit board (Based on the stage of the project).

To start off with learning about microcontrollers (structure, layout, how to program) one is advised to start with learning Arduino. [Arduino](https://www.arduino.cc/en/Guide/Introduction) is a low cost, open source and easy to learn microcontroller. The syntax used to program Arduino is similar to that of C/C++ and a software called [Arduino IDE](https://www.arduino.cc/en/software) is used to program it. Arduino has its own set of [official tutorials](https://www.arduino.cc/en/Tutorial/HomePage). One can also find many tutorials on YouTube channels like [Jeremy Blum](https://www.youtube.com/playlist?list=PLA567CE235D39FA84), [Paul McWhorter](https://www.youtube.com/c/mcwhorpj), etc. There is also a basic tutorial and more info regarding Arduino IDE, from us over [here](https://erc-bpgc.github.io/handbook/electronics/Development_Boards/Arduino/). There is an online simulator which is capable of simulating Arduino projects, called [TinkedCad](https://www.tinkercad.com/), in case one is not willing to buy an Arduino board.

After learning Arduino and understanding the basic concepts regarding working of a microcontroller one can dive deep and try out other microcontrollers like [STM32 (BluePill)](https://erc-bpgc.github.io/handbook/electronics/Development_Boards/STM32/), etc.

Sensors are electronic components used by the robot to get information about the environment. Some few examples of sensors are wheel encoders, temperature sensors, depth cameras (Kinect), LiDARs, Ultrasound sensors, etc. On the other hand actuators are components using which the robot brings about changes in the environment. Ex. Motors (DC, Stepper, Servo, BLDC), Linear Actuators (Solenoid or a linear servo), etc. Actuators are interfaced with the microcontroller using drivers because of the different power budgets of the microcontroller and the actuators.

After interfacing one might want to assemble it on a prototyping board or even a PCB (for long term use). A software called [EAGLE](https://www.autodesk.in/products/eagle/overview?plc=F360&term=1-YEAR&support=ADVANCED&quantity=1) is used to design a PCB. One can download and install it free of cost from the [official website](https://www.autodesk.in/products/eagle/free-download) of AutoDesk. Tutorials on [Jeremy Blum’s](https://www.youtube.com/playlist?list=PL868B73617C6F6FAD) and [Terminal Two’s](https://www.youtube.com/playlist?list=PLr0mEvO7yBe6QHexsgU2WFUGesFFobGZp) YouTube Channel are a great place to start PCB designing using EAGLE.

## Automation

### Robot Operating System (ROS)

Think about how you might go about automating a human like robot that helps out at home. Would you just write one big program to control all its behaviour (navigation, motion, obstacle detection, battery monitoring, speech processing etc..)? The much smarter thing to do would be to have smaller independent programs for each of these which can communicate with each other (i.e one program for moving around, one for talking, one for picking things up etc..).  The problem that arises now is how would these individual programs communicate. The Robot Operating System provides a solution for this. It is not an actual OS, rather a framework which makes communication and coordination easier. Check out [this](https://www.youtube.com/watch?v=N6K2LWG2kRI) and [this](https://www.youtube.com/watch?v=LyC9RAYE96M) video, and [this](https://erc-bpgc.github.io/handbook/automation/ROS/ros/) text for more.

To setup your ROS environment check out [this](https://erc-bpgc.github.io/handbook/automation/ROS/setting_up/).

The official [ROS tutorials](http://wiki.ros.org/ROS/Tutorials) are very good for introduction. The concepts are given in a concise manner, and a lot of example code (Python as well as C++) is given for understanding. Also read about various ROS parameters [here](https://erc-bpgc.github.io/handbook/automation/ROS/ros_p2/).

In case of specific questions, try googling them. Many questions might have been asked before by someone else and an answer might be available on [ROS Answers](https://answers.ros.org/questions/).

A Recommended course: [Hello (Real) World with ROS - Robot Operating System - TU Delft OCW](https://ocw.tudelft.nl/courses/hello-real-world-ros-robot-operating-system/)

[Also refer Morgan Quigley's Programming Robots with ROS](https://www.pdfdrive.com/programming-robots-with-ros-a-practical-introduction-to-the-robot-operating-system-d166617536.html)

### Path Planning

Path planning is the process of "finding" a path or a trajectory for a robot by avoiding obstacles or following set dynamic or kinematic constraints of a robot. Quite literally, it's something we as humans do quite instinctively, but robots find it difficult and we try to make them "intelligent" by using some algorithms which can be called as path planning algorithms. Path planning plays an integral part in robot automation because most of the robots have to plan a path. Even in the case of robotic arms, moving the end effector from a given spatial coordinate to another given spatial coordinate requires "planning of a trajectory" the arm must follow. However, the constraints and dimensions for planning the path or trajectory are different from that used to plan in a ground robot. Read more over [here](https://erc-bpgc.github.io/handbook/automation/PathPlanners/intro/).

Most of the old planning algorithms have many implementations. Check out this [book](http://lavalle.pl/planning/) for an in-depth introduction. The best way to learn about any planning algorithm is to look for the research paper and go through it. Read about Graph based algorithms like [A Star](https://erc-bpgc.github.io/handbook/automation/PathPlanners/Astar/) and [Dijkstra](https://erc-bpgc.github.io/handbook/automation/PathPlanners/Dijkstra/) here. Some information about a Sampling based algorithm - [RRT](https://erc-bpgc.github.io/handbook/automation/PathPlanners/RRT/) can be found here.

However, to find some implementations of the algorithms, you can refer to the [Open Motion Planning Library](https://ompl.kavrakilab.org/) for industry-level implementations of the algorithms. (OMPL is written in C/C++, beware!!). For a better understanding and visualisation of how various algorithms work, take a look at [this](https://github.com/zhm-real/PathPlanning) repository. It’s written in python!

### Simultaneous Localization and Mapping (SLAM)

As the name suggests, what SLAM achieves is simultaneously map and localise in an environment. Historically, mapping and localization were done individually. Doing both of them simultaneously poses some difficulties. Check out the [playlist](https://www.youtube.com/playlist?list=PLgnQpQtFTOGQrZ4O5QzbIHgl3b1JHimN_) by Cyrill Stachniss on SLAM for an in-depth course. Linear algebra and Probability and Statistics are quite important for a better understanding.

### Robot Perception

Robot Perception is something that is really underappreciated by beginners as the difficulties behind it are not properly understood. It’s quite hard to comprehend how hard can seeing, analysing and extracting useful data from a 3D world can be for a robot, as we as humans are quite comfortable in picking and placing objects that are in front of us with utmost precision. It’s easy for us to avoid tripping over a branch while walking(of course if we see it). But the same is very complex for robots.  Robot Perception specifically deals with this aspect of making intelligent robots.

To understand how a robot perceives the environment, you need to know about [the depth map](https://www.omnivirt.com/blog/depth-map/), how we create it and what are its uses (this is a resource using which you can make a depth map yourselves. Generally, depth maps are made by using two cameras, each giving a different perspective of the same scene, thus creating a depth image, just like our eyes). Using depth maps is one of the classical methods of analysing a 3D environment.

Sensors play an important role in any robotic task. High-quality Cameras, LiDARs etc are used. To get started with perception by using images, OpenCV is a good starting point. For perception using Point Clouds, [Point Cloud Library](https://pointclouds.org/) is a good starting point(PCL can only be used using C++).

There are many advancements that are taking place. With the advent of Neural Networks, Convolution Neural Networks(CNN’s) are used to extract and analyse important information from depth maps thus enabling image and point cloud [segmentation](https://towardsdatascience.com/semantic-segmentation-with-deep-learning-a-guide-and-code-e52fc8958823), [classification](https://www.analyticsvidhya.com/blog/2019/01/build-image-classification-model-10-minutes/) tasks etc.

### Machine Learning / AI

Much of the computer based tools we use follow the same principle - they are a collection of  straightforward instructions for the computer to follow so that it can solve a task. Machine Learning on the other hand, is about how the computer can learn to solve a task from examples, much like we humans learn.

* Courses
    * Andrew Ng's classic [machine learning course](https://www.coursera.org/learn/machine-learning) is generally a good place to start.Note that the exercises are in Octave/MATLAB but it's recommended to try them out in python. [This](https://github.com/dibgerge/ml-coursera-python-assignments) repository has a translated version of the exercises.
    * [Deep Learning](https://www.coursera.org/specializations/deep-learning) by deeplearning.ai is a more advanced course by Andrew NG focusing on Deep Learning.
    * After completing one of the above, to explore more advanced subfields within machine learning, Stanford has a good set of courses
        - [Computer Vision](http://cs231n.stanford.edu/) (recommended to do this before the other two)
        - [Natural Language Processing](http://web.stanford.edu/class/cs224n/)
        - [Reinforcement Learning](https://www.youtube.com/watch?v=FgzM3zpZ55o&list=PLoROMvodv4rOSOPzutgyCTapiGlY2Nd8u) (also check out [this](https://web.stanford.edu/class/psych209/Readings/SuttonBartoIPRLBook2ndEd.pdf) book)

* Software Tools
    * *Numpy*: Mathematics and Linear Algebra library for python. Essential to know. [YouTube Tutorial](https://www.youtube.com/watch?v=QUT1VHiLmmI) | [Documentation](https://numpy.org/doc/stable/)
    * *Matplotlib*: Plotting library for python. Essential to know. [YouTube Tutorial](https://www.youtube.com/watch?v=3Xc3CA655Y4) | [Documentation](https://matplotlib.org/)
    * *SciKitLearn*: Machine Learning toolkit in python. [YouTube Tutorial](https://www.youtube.com/watch?v=pqNCD_5r0IU) | [Documentation](http://scikit-learn.org/stable)
    * *OpenCV*: Computer vision toolkit [YouTube Tutorial](https://www.youtube.com/watch?v=oXlwWbU8l2o) | [Documentation](https://docs.opencv.org/master/)
    * *Pytorch*: Deep Learning framework [YouTube Tutorial](https://www.youtube.com/watch?v=GIsg-ZUy0MY) | [Documentation](https://pytorch.org/docs/stable/)
    * *Tensorflow*: Deep Learning framework [YouTube Tutorial](https://www.youtube.com/watch?v=tPYj3fFJGjk) | [Documentation](https://www.tensorflow.org/)

### Control Systems

Control systems help to control the movements and functions of the robot. We need the controllers because the dynamics vary with the time. When the robot moves up in a slope and then down in the slope, or first travels on smooth concrete, then on a carpeted floor. So physical modelling of the “System” becomes crucial for designing a good controller.

We give a reference state to a controller. The controller also has sensor feedback, using the reference state and sensor feedback controller generates a control signal needed to reach the reference state. This control signal is fed to the “System”. The system dynamics determine how the system behaves to this control input. If the controller is good, hopefully, the “System” will reach our desired reference state. For more check [this](https://erc-bpgc.github.io/handbook/automation/ControlTheory/Control_Theory/).

* To get started with control systems and theory - [Control of Mobile Robots](https://www.youtube.com/playlist?list=PL2jykFOD1AWYvdLW6Alr55IydU_qFVe31) course by Magnus Egerstedt (Georgia Tech), also on Coursera by the same name.
* [Understanding PID Control](https://www.youtube.com/playlist?list=PLn8PRpmsu08pQBgjxYFXSsODEF3Jqmm-y) - Playlist by MATLAB explains PID control in detail. Also read about the controller over [here](https://erc-bpgc.github.io/handbook/automation/ControlTheory/PID_Controller/).
* Read about more advanced controllers like Linear-Quadratic Regulator [(LQR)](https://erc-bpgc.github.io/handbook/automation/ControlTheory/LQR/) and Model Predictive Control [(MPC)](https://erc-bpgc.github.io/handbook/automation/ControlTheory/MPC/) here.
* [This](https://www.youtube.com/playlist?list=PLn8PRpmsu08pFBqgd_6Bi7msgkWFKL33b) playlist teaches some more basic concepts of Control Theory and how to practically apply them.
* [This](https://www.youtube.com/playlist?list=PLn8PRpmsu08podBgFw66-IavqU2SqPg_w) playlist teaches State space equations, pole placement and concepts like controllability. These become essential when dealing with the math behind Control Theory.

## Mechanical Design

### CAD

Fusion360 is a good starting point to get yourself familiar with 3D modelling to model anything you can think of! This is the [link](https://www.autodesk.com/education/edu-software/overview?sorting=featured&page=1) from where it can be downloaded. Make sure you have an Autodesk account linked with your institute id for free access.

To get started with it check out [official tutorials](https://help.autodesk.com/view/fusion360/ENU/courses/) on Autodesk website.

SOLIDWORKS by Dassault Systems is a major CAD platform that is used for 3D design and basic simulations. It has slightly more functionalities than F360 and is very good for the design of manufactured goods and design engineering. You can easily find SW tutorials on Youtube, however, this Lynda tutorial series on SW is very nice- [Lynda Tutorials SolidWorks](https://drive.google.com/drive/folders/1j9J3IEnAwjRMRvQAYGQYorKHM698ScX9?usp=sharing). [Use BITS mail]

SW is generally a paid software, but you may use this link [(Solidworks)](https://drive.google.com/drive/folders/1z8KxkTZAbILNORRtlUxhGIA0RFSRERb-?usp=sharing) to get a crack version ;) [Use BITS mail and also make sure that you have 12 to 13 GBs of data before you start the download process ^_^].

This youtube video can help you with the installation process [How to Install Solidworks 2018 | 100% works](https://www.youtube.com/watch?v=mZGWI6tAPgQ)
