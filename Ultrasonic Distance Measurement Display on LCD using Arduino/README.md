# 📏 Arduino Ultrasonic Sensor with I2C LCD Display

---

## 🛠 Equipment List
1. **Arduino Uno board**
2. **USB cable** (for programming and power)
3. **Ultrasonic sensor** (PING))) or HC-SR04)
4. **I2C LCD module** (16x2)
5. **Jumper wires** (Male-to-Male)

---

## 📄 Experiment Description
This experiment measures the distance of an object using an ultrasonic sensor and displays the value on an I2C-based 16x2 LCD screen. The ultrasonic sensor emits a sound pulse and calculates the distance by measuring the time taken for the echo to return. The Arduino processes this duration into a distance in centimeters and shows the result on the LCD in real time. This setup is widely used in applications like parking sensors, obstacle detection in robotics, and distance monitoring systems.

---

## 💻 Arduino Code
```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27, 16, 2);

const int sigPin = 3;
long duration;
int distance;

void setup() {
    pinMode(sigPin, OUTPUT);
    lcd.init();
    lcd.backlight();
    lcd.setCursor(0, 0);
    lcd.print("Ultrasonic");
    delay(1000);
    lcd.clear();
}

void loop() {
    pinMode(sigPin, OUTPUT);
    digitalWrite(sigPin, LOW);
    delayMicroseconds(2);
    digitalWrite(sigPin, HIGH);
    delayMicroseconds(10);
    digitalWrite(sigPin, LOW);

    pinMode(sigPin, INPUT);
    duration = pulseIn(sigPin, HIGH);

    distance = duration * 0.034 / 2;

    lcd.setCursor(0, 0);
    lcd.print("Distance: ");
    lcd.print(distance);
    lcd.print(" cm ");

    delay(500);
}

