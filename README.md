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
4. Restart once again Arduino
