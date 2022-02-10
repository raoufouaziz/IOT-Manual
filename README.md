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

<img width="1440" alt="Schermafbeelding 2021-10-28 om 10 58 42" src="https://user-images.githubusercontent.com/70513682/139223228-75b055f4-8307-463d-b74c-429bbf8ae41f.png">

# Step 2: Download and install USB drivers 

<img width="1440" alt="Schermafbeelding 2021-10-28 om 11 00 47" src="https://user-images.githubusercontent.com/70513682/139223618-7d93d51f-1fef-47fd-abf5-818185be1569.png">

Install the CP210x VCP Driver at: https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers
# Step 3: Install the NodeMCU Board 
1. Open the Arduino software
2. Go to Arduino > preferences and set the 'Editor language' to English
3. Copy and paste this sentence into the 'Additional Boardmanager URL's': http://arduino.esp8266.com/stable/package_esp8266com_index.json
4. Press the 'OK' button and restart Arduino

<img width="797" alt="Schermafbeelding 2021-10-28 om 11 03 52" src="https://user-images.githubusercontent.com/70513682/139224181-af361407-0dd1-44f4-b2fb-7e228be82809.png">


# Step 4: Add NodeMCU Board
1. Once Arduino has restarted go to Tools > Board > Boards manager...
2. Type in the searchbar 'ESP'
3. Select the 'esp8266 by ESP8266 Community' and install the newest version
4. Restart Arduino once again 
 
<img width="1439" alt="Schermafbeelding 2021-10-28 om 11 04 39" src="https://user-images.githubusercontent.com/70513682/139224285-4efef40b-828e-443b-aa48-27b6c533a305.png">

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
(Put this code under the trigger and echo pins())

The 'CM_TO_INCH' variable allows us to convert distance from centimeters to inches. 

<img width="233" alt="Schermafbeelding 2021-10-28 om 01 29 00" src="https://user-images.githubusercontent.com/70513682/139161859-8a7d93e4-4321-4b7d-b184-714f480661c0.png">

Then, initialize the following variables.

<img width="227" alt="Schermafbeelding 2021-10-28 om 01 35 51" src="https://user-images.githubusercontent.com/70513682/139162312-c54632ac-d3f3-4344-8cfc-39de428f3c05.png">

# Step 8: Setup()
(Every code that is shown now needs to be put inside the setup())

In the Setup(), put the serial communication to 115200 so that the measurment is able to be shown in the serial monitor

<img width="470" alt="Schermafbeelding 2021-10-28 om 01 40 41" src="https://user-images.githubusercontent.com/70513682/139162680-59eb234f-8b88-4422-b5f9-1d9bcb649d9b.png">

Define the trigger pins as the output, they send out the soundwave. Define the echo pins as the input, they receive the reflected soundwave and send the signal to the board

<img width="482" alt="Schermafbeelding 2021-10-28 om 01 43 11" src="https://user-images.githubusercontent.com/70513682/139162875-a21d332b-fac4-46af-bf89-bd855b64ec63.png">

# Step 8: Loop()
(Every code that is shown now needs to be put inside the loop())

In the Loop(), the following line 'LOW' will give out a short pulse to ensure that the 'High' will send out a clean pulse. The 'High' pulse will send out a ultrasound

<img width="433" alt="Schermafbeelding 2021-10-28 om 01 52 57" src="https://user-images.githubusercontent.com/70513682/139163559-f7b8380f-1a33-4033-9276-9b7aafd4f083.png">

After this the following line below will calculate the distance of a object while using the speed that the sound travels in as variable

<img width="331" alt="Schermafbeelding 2021-10-28 om 01 57 12" src="https://user-images.githubusercontent.com/70513682/139163837-6c7ba717-4e4f-4d52-9423-0b0e5ec49ffe.png">

to convert the ouput in CM instead of only outputting it in inch, use the following line

<img width="322" alt="Schermafbeelding 2021-10-28 om 01 58 28" src="https://user-images.githubusercontent.com/70513682/139163932-c0eba53d-31c5-45d0-a3b4-04fd93e437f3.png">

as last this line will put out the variables into the serial monitor as distance in cm and inch

<img width="325" alt="Schermafbeelding 2021-10-28 om 02 01 02" src="https://user-images.githubusercontent.com/70513682/139164091-03219cc7-45e7-444b-9532-8fd8f0f5b16b.png">

after this the setup is finished and de ultrasonic sensor should be emitting the distance recored in cm and inch!
# Step 9: Errors
## Serial Monitor Issues
- If you get a lot of weird characters in your serial monitor make sure that the baudrate of the monitor is the same number as in the Serial.begin(). Changing the baudrate tot the exact same number as the Serial.begin() will fix this problen quite some time. 
![weird characters](/img/questionmark.png)
- When changing the baudrate does not remove the weird characters in the serial monitor you should try to reset the Arduino, resetting the Arduino is quite easy. On the Arduino board a small button can be found below the letters "RTS", clicking on this button will make the Arduino reset itself.

![Reset button](/img/reset.png)
## WIFI Issues
- If you have any problems with connecting to your 2.4GHZ internet connection try using your mobile hotspot, i dont recommend using a mobile hotspot coming from an Apple Device (This will result in no connection at all, try using a Android device)
- If the first solution does not fix the error try to follow the steps listed on this forum https://create.arduino.cc/projecthub/neverofftheinternet/esp8266-setup-and-first-wifi-connection-76fc3c

## General Issues
- When you get an error that the board is not connected check if the board is damaged, connected to a power source or try updating the software (running an old software version can result in many other errors). 
![Board not conected](/img/Board.png)
- Make sure to close every () and [] tag that exists within your code, this small mistake can result in your code not working.
![Code error](/img/reset2.png)

# Step 10: Sources
- https://randomnerdtutorials.com/esp8266-nodemcu-hc-sr04-ultrasonic-arduino/
- https://www.youtube.com/watch?v=LIiFVYXuwTU
- https://www.instructables.com/Distance-Measurement-Using-HC-SR04-Via-NodeMCU/
- https://imdb-api.com/api/#IMDbList-header
