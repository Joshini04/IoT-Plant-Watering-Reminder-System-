# IoT-Plant-Watering-Reminder-System-
Overview
The IoT Plant Watering Reminder System is a simple embedded/IoT
project designed to monitor the moisture level of soil and provide an
alert when a plant needs watering.
The system uses an Arduino microcontroller and a soil moisture
sensor. The sensor detects the moisture condition of the soil, and the
Arduino reads the sensor value and makes a decision based on a
predefined moisture threshold.

How It Works 
Soil
  ↓
Soil Moisture Sensor
  ↓
Arduino Microcontroller
  ↓
Embedded C Program
  ↓
Check Moisture Level
  ↓
If soil is dry → Trigger Alert


Basic Working
1. The soil moisture sensor detects the moisture level of the soil.
2. The sensor provides a signal to the Arduino.
3. The Arduino reads the sensor value through an input pin.
4. The Embedded C program compares the reading with a moisture
   threshold.
5. If the soil is sufficiently dry, the system triggers an
   alert/reminder to water the plant.


Hardware Used
- Arduino Uno
- Soil moisture sensor
- Breadboard
- Jumper wires
- LED  ( Alert indicator )

Software
- Embedded C 
- Arduino IDE

Code Used:

const int moistureSensor = A0;
const int alertPin = 13;

void setup() {
    pinMode(alertPin, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    int moistureValue = analogRead(moistureSensor);
    Serial.println(moistureValue);
    if (moistureValue < 500) {
        // Soil is considered dry
        digitalWrite(alertPin, HIGH);
    } else {
        // Soil has sufficient moisture
        digitalWrite(alertPin, LOW);
    }
    delay(1000);
}

Soil moisture sensor
A typical moisture sensor module has:
- VCC → Arduino 5V
- GND → Arduino GND
- AO (Analog Output) → Arduino A0
