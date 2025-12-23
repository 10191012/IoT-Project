![System Diagram](https://github.com/user-attachments/assets/b5a9df77-3320-4874-8393-ff57d434966f) 

Figure 1

# HARDWARE DESCRIPTION
1.	Arduino UNO R3
-	It is a central microcontroller.
-	Reads sensor inputs, processes the data, and controls actuators (fan and lights).
-	Handles communication with the cloud server (ThingSpeak) over Wi-Fi.

2.	PIR Motion Sensor
-	Detects the movement in the range.
-	Outputs a digital HIGH signal when motion is detected, LOW when no motion.
-	Help to wake up lights and record the motion events to the cloud.

3.	LM35 Temperature Sensor
-	Measures ambient temperature 
-	Connected to the analog input of the microcontroller.
-	DC fan ON or OFF is controlled by temperature readings based on predefined temperature limits.

4.	Relay Module
-	Electronic switch to control high-voltage or current devices using low-voltage signals from the microcontroller.
-	Used only to control the DC motor fan in this system.
-	Protects the microcontroller from high current drawn by the fan.

5.	DC Motor Fan
-	Controlled through the relay module.

6.	LED Indicators
-	Visual feedback for motion detection and system condition.
-	Lights up when motion is detected to indicate the PIR sensor has been 

7.	Power Supply
-	Supplies regulated voltage to the microcontroller, sensors, and actuators.
-	Arduino UNO, 5V and 3.3V via USB.

8.	Wi-Fi Module (Embedded in Shield for Arduino)
-	Connect the microcontroller (Arduino UNO) to the internet.
-	Sends sensor data to ThingSpeak for storage, visualization, and remote monitoring.

# COMUNICATION PROTOCOL
The Wi-Fi connection signals and HTTP requests data are transferred between the Arduino UNO and Cytron ESP8266 WiFi Shield through UART serial communication using TX and RX
pins. The ESP8266 is connected to the internet through a Wi-Fi router based on the IEEE 802.11 b/g/n standards because the ESP8266 only supports the 2.4 Ghz, which is secured by WPA/WPA2 encryption. The ThingSpeak dashboard through HTTPS is secured by the cloud server TLS, the data from sensors is transferred from the ESP8266 side to the ThingSpeak cloud server through HTTP/TCPIP port 80 authenticated by the API key.

# FDATA FLOW
## Step 1: Data Acquisition (Perception Layer)
-	The PIR motion sensor detects movement and outputs a digital signal (HIGH or LOW), LED ON or OFF.
-	The LM35 temperature sensor measures ambient temperature and outputs an analog voltage proportional to temperature.
-	Arduino microcontroller continuously reads:
    *	Digital input from the PIR sensor, Analog input from the LM35 sensor.

## Step 2: Local Processing and Control
-	The Arduino processes the sensor data:
    *	Motion status is determined (0 = no motion, 1 = motion detected).
    *	LM35 voltage output is used to measure the temperature.
-	Based on predefined thresholds:
    *	Relay module is activated to turn the fan ON or OFF
    *	LED indicators are switched to reflect motion detection
-	The processed values are prepared for cloud transmission.

## Step 3: Data Transmission to Wi-Fi Module
-	Arduino sends processed sensor data to the Cytron ESP8266 WiFi Shield via UART serial communication implemented through the SoftwareSerial library.
-	Cytron ESP8266 WiFi shield handles:
    *	Wi-Fi communication
    *	HTTP request generation
-	Two Arduino digital pins are configured as:
    *	TX (Transmit) – sends data from Arduino to ESP8266
    *	RX (Receive) – receives responses from ESP8266
-	Using serial (TX/RX) communication, the Arduino UNO sends sensor and control data to the Cytron ESP8266 WiFi Shield, which then processes it to control internet and          Wi-Fi access.

## Step 4: Cloud Communication (Network Layer)
-	Cytron ESP8266 connects to the local Wi-Fi router using WPA2 security.
-	Sensor data is uploaded to ThingSpeak cloud server using:
    *	HTTP POST method
    *	ThingSpeak Write API Key for authentication
-	Data is sent at a fixed interval (every 15 seconds).

## Step 5: Cloud Processing and Storage (Application Layer)
-	ThingSpeak receives the data and:
    *	Authenticates the request using the API key
    *	Stores data into corresponding fields:
        -	Field 1 → PIR Motion
        -	Field 2 → Temperature
        -	Field 3 → Fan state
-	ThingSpeak cloud platform processes and timestamps the data.

## Step 6: Data Visualization and User Access
-	Users access ThingSpeak dashboard through a web browser.
-	Data is visualized as:
    *	Motion detection graph
    *	Temperature change graph
    *	Fan ON/OFF status
-	Dashboard access is protected using HTTPS and user authentication.
