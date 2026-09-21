# EXP 7 : INTERFACING A 16×2 LCD WITH ARDUINO USING AN I2C MODULE FOR SENSOR DATA DISPLAY


# AIM

To interface a **16×2 LCD display with Arduino using an I2C module** and display sensor data on the LCD.

# Objectives

- To understand the operation of a 16×2 LCD.
- To interface the LCD with Arduino using an I2C module.
- To reduce the number of GPIO pins required for LCD communication.
- To read sensor data using Arduino.
- To display the sensor readings on the LCD.

# Hardware / Software Tools Required

# Hardware

- Arduino UNO
- 16×2 LCD Display
- I2C LCD Module (PCF8574-based)
- DHT11 Temperature and Humidity Sensor
- Breadboard
- Jumper wires
- USB cable

# Software

- Arduino IDE
- Arduino C/C++ programming language
- LiquidCrystal_I2C library
- DHT sensor library

# Components

 - 16×2 LCD
 - I2C Module
 - Circuit Connections
 - I2C Communication
 - Working Principle

1. The DHT11 sensor measures temperature and humidity.
2. Arduino reads the sensor values through the digital data pin.
3. The Arduino processes the received sensor data.
4. The processed values are sent to the LCD through the I2C interface.
5. The LCD displays the temperature on one line.
6. The humidity is displayed on the second line.
7. The readings are periodically updated.

# Arduino Program
```c
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

// Ultrasonic sensor pins
int trigPin = 7;
int echoPin = 6;

// LCD address 0x20, 16 columns, 2 rows
LiquidCrystal_I2C lcd(0x20, 16, 2);

long duration;
float distance;

void setup()
{
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);

  Serial.begin(9600);

  lcd.init();
  lcd.backlight();

  lcd.setCursor(0, 0);
  lcd.print("Ultrasonic");
  lcd.setCursor(0, 1);
  lcd.print("Starting...");

  delay(2000);
  lcd.clear();
}

void loop()
{
  // Send ultrasonic trigger pulse
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  // Read echo time
  duration = pulseIn(echoPin, HIGH);

  // Calculate distance in cm
  distance = duration * 0.0343 / 2;

  // Display on LCD
  lcd.clear();

  lcd.setCursor(0, 0);
  lcd.print("Distance:");

  lcd.setCursor(0, 1);
  lcd.print(distance, 1);
  lcd.print(" cm");

  // Serial Monitor
  Serial.print("Distance: ");
  Serial.print(distance, 1);
  Serial.println(" cm");

  delay(500);
}
```

# Output

<img width="1482" height="762" alt="image" src="https://github.com/user-attachments/assets/97eb949d-717d-4dda-b1b3-dbc5319f5543" />


# Result

Thus, the **16×2 LCD was successfully interfaced with Arduino UNO using an I2C module**, and the temperature and humidity values obtained from the DHT11 sensor were successfully displayed on the LCD. The experiment demonstrates the use of **I2C communication for efficient sensor-data display** in embedded and IoT applications.
