# NETWORKING AND DATA MANAGEMENT

## a.	Communication Protocol (HTTP) 
The method of communication between the IoT node based on Arduino and the cloud platform ThingSpeak is via Hypertext Transfer Protocol (HTTP). The main reasons for 
selecting this protocol are due to its simplicity, reliability and ease of implementation with the ThingSpeak cloud platform.

The Arduino acts as a client that sends readings to the ThingSpeak server by sending POST requests via HTTP (HyperText Transfer Protocol). For example, the Arduino sends 
a POST request for the sensor readings of temperature, light intensity, and motion status, to different fields of the ThingSpeak channel (which are defined before). 
The architecture of this communication model is between two machines in a client-server setup; therefore, the incoming data will be saved and processed on the cloud server.

The main communication method is from the Arduino to the server (client-to-server) as ThingSpeak does not push downwards control commands to the Arduino directly. 
Any control logic, such as threshold-based activation of the fan or lighting, is implemented locally on the Arduino.

## b.	Communication Direction and Control Logic
The protocol defined in this project for communicating between Arduino devices and the ThingSpeak cloud-based service uses both POST and GET methods but relies solely 
on POST requests to transfer sensor data from the Arduino device to ThingSpeak. Arduino devices can optionally use GET requests periodically to obtain configuration 
parameters such as threshold values from a ThingSpeak channel.

ThingSpeak does not initiate commands to any of the Arduino devices; they instead have to poll the ThingSpeak server whenever they require information, thereby creating a 
predicable pattern to have the devices and the server communicate, and preventing extra layers of complexity from being introduced.

Real-time decision making is done locally on the Arduino device and allows for the quickest response time possible should any delays occur in a network connection. 
For example, when it detects motion from the motion sensor it will turn the LED light and fan on.

## c.	Network Topology
The system follows the point to cloud topology using a single node. Each node consists of an Arduino sensor and actuator, and it is directly connected to the 
ThingSpeak cloud server using Wi-Fi and no intermediate access server or gateway is used.

This topology would be applicable in a small-scale prototype in a single room and has a few benefits:
-	Lower hardware price and simplicity of the system.
-	Simple installation and support.
-	Direct remote access to sensor data through the cloud dashboard.
Nonetheless, this design can be optimized to offer more substantial deployments of many nodes in IoT.

## d.	Data Management and Graphical representation.
Sensor data is uploaded to ThingSpeak at regular time intervals of say 5-10 seconds. The data is generated in the cloud platform and stored in ordered fields relating to 
temperature, intensity of light, and motion status. ThingSpeak automatically creates real-time graphical visualizations, such as the line graphs that illustrate the 
environmental trends with time.

Local processing with the Arduino is mandatory to provide instant actuation of devices and remote monitoring, historical data analysis, and evaluation of the system 
performance is possible with cloud-based visualization.
