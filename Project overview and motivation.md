# ABSTRACT
This project presents the design and implementation of a smart home automation system based on Internet of Things (IoT) technology 
for real-time monitoring and automated control. The system employs an Arduino Uno microcontroller integrated with a PIR motion sensor 
and an LM35 temperature sensor to detect human presence and ambient temperature conditions. Lighting is activated upon motion detection, 
while a DC motor fan is automatically controlled through a relay module when the temperature exceeds a predefined threshold. 
Wireless connectivity is provided by an Arduino Wi-Fi Shield, enabling periodic transmission of sensor data to the ThingSpeak cloud platform for visualization 
and remote monitoring. The system software is developed using a modular programming approach to manage sensor data acquisition, actuator control, and cloud communication. 
The implemented prototype demonstrates reliable sensor-based automation, real-time cloud monitoring, and improved energy efficiency in a smart home environment.

# INTRODUCTION
With the increasing demand for energy efficiency, comfort, and safety in modern living environments, traditional home and building systems are no longer sufficient to meet 
current user expectations. Conventional lighting and temperature control systems often rely on manual operation, which can result in energy wastage, 
inconsistent environmental conditions, and reduced user convenience. In addition, the lack of real-time monitoring makes it difficult for users to track environmental conditions 
or device usage remotely. The main objective of this project is to design and implement an intelligent lighting and temperature control system using Internet of Things 
technologies. The system's goals are to automatically modify lighting based on motion detection and temperature using sensor-based thresholds. 
Another objective is to enable real-time data monitoring through cloud integration, allowing users to observe system behavior remotely. 
The expected outcome is a functional prototype that improves comfort, increases energy efficiency, and demonstrates how IoT concepts can be applied in actual smart homes 
and buildings.
