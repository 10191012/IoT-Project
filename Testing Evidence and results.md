# TESTING AND RESULTS

## Testing Procedure
The smart home automation system was evaluated with the goal of verifying proper sensor execution, automated fan control, wireless data transfer, and cloud-based monitoring, 
the smart home automation system was assessed. The following steps made up the testing procedure:
## 1.	Hardware Verification
- Verified LM35 temperature sensor connection to the Arduino analog input.
-	Confirmed PIR motion sensor connection to the digital input pin.
-	Checked proper wiring of relay module, LED indicators, and DC motor fan to digital output pins via jumper wires and breadboards.
-	Ensured stable power supply through the USB connection to a laptop.

## 2.	Firmware and Software Testing
-	Verified successful initialization of the temperature sensor, motion sensor, and Wi-Fi Shield during system startup.
-	Tested temperature and motion data acquisition to ensure accurate sensor readings.
-	Confirmed periodic transmission of sensor data to the ThingSpeak platform using the programmed delay interval.

## 3.	Actuator Response Testing
-	LED indicators were tested to ensure they light up upon motion detection.
-	Tested fan activation through the relay module when the temperature exceeded the predefined threshold.
-	Observed system behaviour to ensure the fan remained off when temperature values were below the threshold.

## 4.	Wireless Communication and Cloud Monitoring
-	Tested Wi-Fi connectivity between the Arduino Uno and the ThingSpeak cloud platform.
-	Verified that temperature readings, motion status, and fan state were successfully uploaded and visualized in real time on the ThingSpeak dashboard.

## 5.	Security Verification
-	Verified Write and Read API key authentication to ensure only authorized devices could upload or view data.
-	Confirmed HTTPS access to the ThingSpeak dashboard, ensuring encrypted communication.
-	Checked that Wi-Fi credentials were not hard coded in the firmware to prevent unauthorized access.
-	Attempted uploads and dashboard access with invalid credentials to confirm effective blocking of unauthorized actions.

## 6.	System Integration Testing
-	Observed the interaction between the motion sensor, temperature sensor, fan control, and cloud visualization to ensure correct system operation.
-	Measured latency between sensor detection, fan activation, and data updates on the ThingSpeak platform.
<img width="373" height="600" alt="Screenshot 2025-12-15 233137" src="https://github.com/user-attachments/assets/fb322d40-347b-4723-8cf1-c49789c56f44" />
Figure 4.1
