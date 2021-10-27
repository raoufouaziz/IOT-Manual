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
# Step 6: Ultrasonic Sensor code
(Copy and paste this code in Arduino)
const int trigPin = 12;
const int echoPin = 14;

//define sound velocity in cm/uS
#define SOUND_VELOCITY 0.034
#define CM_TO_INCH 0.393701

long duration;
float distanceCm;
float distanceInch;

void setup() {
  Serial.begin(115200); // Starts the serial communication
  pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
  pinMode(echoPin, INPUT); // Sets the echoPin as an Input
}

void loop() {
  // Clears the trigPin
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  // Sets the trigPin on HIGH state for 10 micro seconds
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  // Reads the echoPin, returns the sound wave travel time in microseconds
  duration = pulseIn(echoPin, HIGH);
  
  // Calculate the distance
  distanceCm = duration * SOUND_VELOCITY/2;
  
  // Convert to inches
  distanceInch = distanceCm * CM_TO_INCH;
  
  // Prints the distance on the Serial Monitor
  Serial.print("Distance (cm): ");
  Serial.println(distanceCm);
  Serial.print("Distance (inch): ");
  Serial.println(distanceInch);
  
  delay(1000);
}
