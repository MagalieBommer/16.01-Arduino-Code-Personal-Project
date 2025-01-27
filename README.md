# 16.01-Arduino-Code-Personal-Project

// Define the PIR sensor pin
const int pirPin = 2;    // PIR sensor output connected to digital pin 2
const int ledPin = 13;   // Onboard LED connected to digital pin 13

void setup() {
// Initialize the PIR sensor pin as an input
pinMode(pirPin, INPUT);

// Initialize the LED pin as an output
pinMode(ledPin, OUTPUT);

// Start the Serial Monitor for debugging
Serial.begin(9600);
Serial.println("PIR Sensor Test Initialized");
}

void loop() {
// Read the state of the PIR sensor
int motionDetected = digitalRead(pirPin);

// Check if motion is detected
if (motionDetected == HIGH) {
Serial.println("Motion Detected!");
digitalWrite(ledPin, HIGH); // Turn on the LED
} else {
Serial.println("No Motion");
digitalWrite(ledPin, LOW);  // Turn off the LED
}

// Small delay to avoid spamming the Serial Monitor
delay(100);
}
