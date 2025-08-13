# 🌱 Arduino Soil Moisture Sensor with Servo Motor Control

## 🔗 Tinkercad Project
[View My Circuit on Tinkercad](https://www.tinkercad.com/things/cfCBNDNSxjA-tremendous-inari-bigery/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=Lorxf4x6OjPsGNuf4kDVu9l6zt9mohwKjP9KICW5f9U)

---

## 🛠 Equipment List
1. **Arduino Uno board**
2. **USB cable** (for programming and power)
3. **Soil moisture sensor module**
4. **Servo motor** (SG90 or similar)
5. **Jumper wires** (Male-to-Male)

---

## 📄 Experiment Description
This experiment demonstrates how to control a servo motor based on the moisture level of the soil. The soil moisture sensor measures the water content in the soil and sends an analog value to the Arduino. The Arduino then maps this value to a servo motor angle (0° to 90°). As the soil becomes wetter or drier, the servo position changes accordingly. This setup can be used for automated systems such as opening or closing a valve in irrigation, depending on the moisture condition of the soil.

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

