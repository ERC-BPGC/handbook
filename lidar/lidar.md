# Lidar

Lidar is a method for calculating distances between objects with the help of a laser and measuring the amount of time taken for the reflected light to return back.

## Lidar Sensor

A Lidar sensor emits pulsed light waves into the surrounding environment. These pulses bounce off of    obstacles and the surrounding environment as a whole and then return to the sensor. The sensor then,   keeps a track of time it took for the light to bounce off and thus calculating the distance between   obstacles. Repeating this process constantly creates a real-time map of the environment.

### Types of Lidar Systems

1) Airborne Lidar - This is installed on aerial drones or vehicles like helicopters. It emits light towards the ground surface giving a fairly detailed and quick map of the terrain above which the vehicle or drone is flying. It is also used for topographic survey.

<center>![image](images/lidar-airborne_lidar.jpg){: style="height:200px"}</center>

2) Terrestrial Lidar - This is generally installed on vehicles moving on the earth's surface. These give a detailed map, and can be used to make a robot or a vehicle navigate through it's evironment. It is also used for observing highways, roads and infrastructure.

<center>![image](images/lidar-terrestrial_lidar.png){: style="height:200px"}</center>


### Components of a basic Lidar Sensor

<center>![](images/lidar-components_of_lidar.png){: style="height:350px"}</center>

A lidar sensor generally consists of 4 main components: 
1) Light source - Generally a laser (or anything that emits light in pulses)
2) Optical components - There are multiple optical components for example, the light through the sensor, falls on a rotating/oscillating mirror so as to change the direction of light to cover a 360 view. An optical lens helps to focus light on the photodetector.
3) photodector - The light is recieved by this photodetector and the signal is processed electronically like frequency of light (for speed measurements) and the time taken for the light to bounce.
4) GPS - These sensors need a GPS system to determine the exact position and orientation of the sensor in 3D space.

For a more indepth explaination of a Lidar sensor and the different factors that go into designing one, for example, the wavelength of light to use, the pulsing rate of the light or pulse repetition rate and more factors can be found [here.](https://www.newport.com/n/lidar)

## Lidar usage

For details on how to setup different types of lidar sensors, use [this link.](https://www.generationrobots.com/blog/en/lidar-integration-with-ros-quickstart-guide-and-projects-ideas) This shows a fairly detailed explaination on how to setup your lidar to interact with ROS and display the results in rviz. It also has some examples of implementation and different repositories that would help you to code.

You can also check out [this link](https://maker.pro/ros/tutorial/how-to-use-a-lidar-sensor-with-robot-operating-system-ros) which provides a simple explaination for setting up a YDLiDAR X4 Sensor.

## Applications of Lidar

1) Surveying land - Lidar sensors can generate a cost effective solution for generating a 3D digital terrain model of remote or rough areas which are difficult to assess otherwise. (Nasa used Lidar techonology to explore mars). For more information on Airborne Lidar and Topographic survey, check out [this research paper](https://www.isprs.org/proceedings/XXXVII/congress/3b_pdf/50.pdf).
2) Power line inspection - Power lines span very long distances and thus make the inspection of power lines very difficult. Lidar sensors can make the inspection easier, by identifying faults before they can cause any real damage.
3) Farming and Forest research - These can be deployed to large farms to help determine how to use resources in an efficient manner and boost productivity. They can also be used to research on the impact that humans have caused on natural life in forests, as Lidar sensors can penetrate tree cover.
4) Climate and weather change - Climate scientists use Lidar to study and track changes in the atmosphere. Lidar can also be used to warn people if there is a Tsunami incoming.
5) Robotics - Lidar is used to equip robots with Mapping and navigational capabilities. For example, self driving cars.

## Companies working on Lidar technologies

1) [tuSimple](https://www.tusimple.com/) - works on self driving cars which is almost commercial ready.
2) [AEye](https://www.aeye.ai/) - Develops advanced vision hardware, software and algorithms for autonomous vehicles.
3) [SiLC Technologies](https://www.silc.com/) - Is a leading provider of highly integrated FMCW (Frequency Modulated Continuous Wave) Lidar solutions, which include their FMCW integration chip.

Sources used - 
1) https://en.wikipedia.org/wiki/Lidar
2) https://oceanservice.noaa.gov/facts/lidar.html
3) https://velodynelidar.com/what-is-lidar/
4) https://www.sentech.nl/en/sensor-technology/revealing-science-behind-lidar-technology/
5) https://www.isprs.org/proceedings/XXXVII/congress/3b_pdf/50.pdf
6)https://www.geospatialworld.net/blogs/what-is-lidar-technology-and-how-does-it-work/
7) https://www.microdrones.com/en/content/5-compelling-applications-for-lidar-technology/
8) https://blog.cloudfactory.com/interesting-lidar-applications
