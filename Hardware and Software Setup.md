<img width="289" height="268" alt="Picture1" src="https://github.com/user-attachments/assets/fdcc07e9-ae54-484e-9a62-9426fec67338" /> Figure 2

# IMPLEMENTATION DETAILS

The system is designed to operate utilizing an Arduino Uno, functioning as the central controller, which is connected to a laptop using a USB cable for power supply. 
For wireless communication, an Arduino Wi-Fi Shield (ESP8266) module is utilized, where the Wi-Fi shield connects to the Arduino using a serial connection, with the 
necessary pins appropriately connected based on the Wi-Fi shield layout. An analog temperature sensor is connected to the Arduino board’s analog input pin for 
temperature measurement. Additionally, a PIR motion sensor is connected to a digital input pin to detect any kind of motion. The relay module, LED, and DC motor fan 
output devices are connected to the digital output pins of the board using jumper wires and breadboards for a reliable connection. The system firmware is developed with 
the Arduino IDE. Several libraries are utilized to support wireless communication and cloud interaction, including cytronWifiShield.h, cytronWifiClient.h, SoftwareSerial.h, 
and ThingSpeak.h. The program is structured into functional modules to improve readability and maintainability. These modules include sensor initialization, Wi-Fi configuration, sensor data acquisition, data transmission, and timing control. During execution, the system initializes the connected sensors, establishes a Wi-Fi connection, 
reads sensor data, and periodically transmits the data to the cloud platform. A delay mechanism is implemented to regulate the data update interval. 
Software development and debugging are performed using Arduino IDE on a laptop. The data obtained from sensors is uploaded to the ThingSpeak platform, which provides a 
graphical interface in the form of charts to facilitate system analysis.
