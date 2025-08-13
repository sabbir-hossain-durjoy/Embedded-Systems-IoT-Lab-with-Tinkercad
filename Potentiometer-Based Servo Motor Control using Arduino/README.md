# 🎛 Arduino Potentiometer Controlled Servo Motor

## 🔗 Tinkercad Project
[View My Circuit on Tinkercad](https://www.tinkercad.com/things/i2juSegqQ2Z-surprising-uusam-gogo/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard&sharecode=z1EjPT-Ak8ASgNdSXkn8TEvZnx_nm2NVCKenv0httRE)

---

## 🛠 Equipment List
1. **Arduino Uno board**
2. **USB cable** (for programming and power)
3. **Potentiometer (10kΩ)**
4. **Servo motor** (SG90 or similar)
5. **Jumper wires** (Male-to-Male)

---

## 📄 Experiment Description
This experiment demonstrates how to control the position of a servo motor using a potentiometer. The potentiometer acts as a variable resistor, providing an analog input to the Arduino based on its rotation. The Arduino reads this analog value, maps it to a servo angle range (0° to 90°), and moves the servo accordingly. This setup is commonly used in projects requiring manual control of servo position, such as robotic arms, camera gimbals, or steering mechanisms.

---

## 💻 Arduino Code
```cpp
#include <Servo.h>
Servo myservo;
int value;

void setup()
{
  myservo.attach(10);
  pinMode(A0, INPUT);
}

void loop()
{
  value = analogRead(A0);
  value = map(value, 0, 1023, 0, 90);
  myservo.write(value);
}

