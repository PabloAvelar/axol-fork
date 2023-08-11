# AXOL

<img src="images/axol_system.jpeg">

```
   █████╗ ██╗  ██╗ ██████╗ ██╗     
  ██╔══██╗╚██╗██╔╝██╔═══██╗██║     
  ███████║ ╚███╔╝ ██║   ██║██║     
  ██╔══██║ ██╔██╗ ██║   ██║██║     
  ██║  ██║██╔╝ ██╗╚██████╔╝███████╗
  ╚═╝  ╚═╝╚═╝  ╚═╝ ╚═════╝ ╚══════╝

  ᓬ(• - •)ᕒ

Andres Rico - MIT Media Lab - aricom@mit.edu

```

<h1>Axol sensing system. </h1>

Sensors for granular assessment of water usage patterns in informal settlements.

This repository contains all files needed to replicate a fully functional Axol sensing system.

The current version of the system is has four sensor types and a HomeHub communication device. The four sensing units include tank sensors, bucket sensors, quality sensors and environmental sensors.

<h1>Devices</h1>

<h2>Homehub</h2>
The Homehub acts as a user interface and as the centralized data relay for the system. All of the sensing units send the data directly to a Homehub. The Homehub formats and sends the infroamtion to a remote database. 

Note: It is advised to firstly manufacture a HomeHub device as all other sensors directly connect to the Homehub. 

<h2>Tank Sensor</h2>
The tank sensor uses Adafruits VXL ToF distance sensor. It measures the distance between a water tanks lid and the water line. With this information we can calculate a containers used volume to detemrine how much water is stored within the container. 

<h2>Bucket Sensor</h2>
The bucket sensor uses a simple tilt switch. The switch is closed whenever a bucket is flipped. Everytime that the switch is activated, the sensor sends a notice to the Homehub and the Homehub timestamps the information before sending it to the database. 

<h2>Quality Sensor</h2>
The quality sensor measures EC in water to get an estimate of Total Dissolved Solids. 

<h2>Environmental Sensor</h2>
The environmental sensor uses an STH sensor to measure enviroenmental temperature and humidity. The sensor can be a good way to evaluate system and battery performance. It can also be used to track environemetal variables of places were the other sensors are placed. 

<h1>Demos</h1>

<img src="images/Bucket_zoom.gif">


<h1>Viewing your systems data </h1>

You can register all devices at http://blindspot.media.mit.edu/homehubweb/registration.html
All devices must be paired with a Homehub that has been previously registered. 

You can check your systems data at http://blindspot.media.mit.edu/homehubweb/status_check.html
By just typing in your homehubs registered mac address. 

<h1>Data handling</h1>

The system uses the Homehub to send data to a server hosted @MIT. All of the data of registered devices is accessible by the developers of the platform. If you do not want developers to have access you will need to build backend infrstructure that will allow you to save data in a different server and modify the connect_send(), get_system_stats(), and server_send() function in the homehubs <a href="https://github.com/AndresRicoM/axol/blob/main/homehub/code/cs_homehub.ino">code</a>. 

Please contact aricom@mit.edu for historical access to data for your system. 

<h1>License</h1>