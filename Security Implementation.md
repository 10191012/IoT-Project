<img width="1919" height="389" alt="Screenshot 2025-12-19 135400" src="https://github.com/user-attachments/assets/2cf5250b-4a19-4ab8-b38f-7c0f21d58598" />
<img width="1917" height="1001" alt="Screenshot 2025-12-19 135724" src="https://github.com/user-attachments/assets/81564693-3bf4-45fe-984c-6e6af1726635" />

# SECURITY MECHANISM

Security is a critical component of IoT systems since sensor data is sent over the internet. In this project, the Internet of Things node is an Arduino Uno.
The Arduino Uno's limited processing power and memory constraints prevent it from directly handling TLS encryption and HTTPS communication. As a result, the Arduino 
transmits sensor data to the ThingSpeak cloud platform via HTTP. 

Security is an important consideration in IoT systems due to the transmission of sensor data over the internet. In this project, the Arduino Uno is used as the IoT node. 
Due to its limited processing power and memory constraints, the Arduino Uno is unable to directly handle TLS encryption or HTTPS communication. As a result, sensor data 
is transmitted from the Arduino to the ThingSpeak cloud platform using HTTP.

Access to the ThingSpeak channel is protected using API keys, which act as a form of authentication. Only devices with the correct Write API Key are allowed to upload
data to the channel, while Read API Keys control who can view the data. This prevents unauthorized users or devices from accessing or modifying the system data. 
To reduce the risk of credential exposure, Wi-Fi network credentials like SSID and password are not directly hard coded within the main application logic.

The use of HTTPS can be verified when accessing the ThingSpeak dashboard through a web browser, where encrypted communication is indicated by the secure connection protocol. 
Additionally, data uploads are accepted only when valid API keys are provided, demonstrating effective authentication and controlled access to the system.
