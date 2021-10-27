# ESP8266 NodeMCU with HC-SR04 Ultrasonic Sensor
Ultrasonic Snesor manual for the ESP8266 NodeMCU. This project is commissioned by my IOT teachers, during this manual i will be working with the Arduino software.
At the end of this manual you will be able to measure the distance of a object using the HC-SR04 Ultrasonic Sensor.
# Supplies
- HC-SR04 Ultrasonic Sensor
- NodeMCU ESP8266 
- Breadboard
- Jumper wires
# Step 1: Download install the Arduino software
Install Arduino's latest version at: https://www.arduino.cc/en/Main/Software
# Step 2: Download and install USB drivers 
Install the CP210x VCP Driver at: https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers
# Step 3: Install the NodeMCU Board 
1. Open the Arduino software
2. Go to Arduino > preferences and set the 'Editor language' to English
3. Copy and paste this sentence into the 'Additional Boardmanager URL's': http://arduino.esp8266.com/stable/package_esp8266com_index.json
4. Press the 'OK' button and restart Arduino
# Step 4: Add NodeMCU Board
1. Once Arduino has restarted go to Tools > Board > Boards manager...
2. Type in the searchbar 'ESP'
3. Select the 'esp8266 by ESP8266 Community' and install the newest version
4. Restart Arduino once again 
# Step 5: Connect the Ultrasonic Sensor to the NodeMCU
(Use jumper wires to connect the pins together)
- Connect 'VCC' to 'VIN'
- Connect 'TRIG' to 'D5'
- Connect 'ECHO' to 'D6'
- Connect 'GND' to 'GND'

![ezgif com-webp-to-png](https://user-images.githubusercontent.com/70513682/139153130-7053bc1f-4f79-470c-98aa-474e856449f0.png)

(Picture above for illustration)
# Step 6: Define triggers and echo pins
Open the Arduino editor and define the echopins and triggerpins (Put this code before the setup()
 

<img width="250" alt="Schermafbeelding 2021-10-28 om 00 54 17" src="https://user-images.githubusercontent.com/70513682/139158880-9bda90f1-3262-426a-a7e7-9d46aa1790a6.png">

# Step 7: Define 'sound_speed' and 'CM_to_inch'
The 'CM_TO_INCH' variable allows us to convert distance from centimeters to inches. 

<img width="233" alt="Schermafbeelding 2021-10-28 om 01 29 00" src="https://user-images.githubusercontent.com/70513682/139161859-8a7d93e4-4321-4b7d-b184-714f480661c0.png">
