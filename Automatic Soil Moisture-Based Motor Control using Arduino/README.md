# 🌱 Arduino Soil Moisture Sensor with Automatic Motor Control

## 🔗 Tinkercad Project
[View My Circuit on Tinkercad](https://www.tinkercad.com/things/dyZDKjSBcBr-smooth-kasi/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=-LY5jgBhchdDuMA4NMLcpSNxFpIWDXM4KN-f_dI8SMg)

---

## 🛠 Equipment List
1. **Arduino Uno board**
2. **USB cable** (for programming and power)
3. **Soil moisture sensor module**
4. **DC motor (or water pump)**
5. **220Ω resistor**
6. **Jumper wires** (Male-to-Male)

---

## 📄 Experiment Description
This experiment automatically turns on a motor when the soil is dry and turns it off when the soil is sufficiently moist. The soil moisture sensor measures the water content in the soil and sends an analog signal to the Arduino. If the moisture level drops below a threshold (500 in the code), the motor connected to pin 13 is turned ON; otherwise, it remains OFF. This is useful for automated irrigation systems.

---

## 💻 Arduino Code
```cpp
void setup()
{
  pinMode(13, OUTPUT);
}

void loop()
{
  int x = analogRead(A0);
  
  if (x < 500)
  {
    digitalWrite(13, HIGH);
  }
  else
  {
    digitalWrite(13, LOW);
  }
  
  delay(500);
}

