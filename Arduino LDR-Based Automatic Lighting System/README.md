# 💡 Arduino LDR-Based Automatic Lighting System

## 🔗 Tinkercad Project
[View My Circuit on Tinkercad](https://www.tinkercad.com/things/6IEvBgmuwwg-cool-luulia-rottis/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=4jR2LNjjJpiFhuQsrIIlSQVT1YWpxbIJoTP_D9V_Wls)

---

## 🛠 Equipment List
1. **Arduino Uno board**
2. **USB cable** (for programming and power)
3. **Light Dependent Resistor (LDR)**
4. **Red LED**
5. **220Ω resistor** (for LED)
6. **10kΩ resistor** (for LDR voltage divider)
7. **Jumper wires** (Male-to-Male)

---

## 📄 Experiment Description
This experiment demonstrates how to control an LED based on the ambient light level using an LDR. The LDR detects the amount of light and sends an analog value to the Arduino. When the light intensity falls below a set threshold (darker environment), the Arduino turns the LED on. When the light is above the threshold (brighter environment), the LED remains off. This setup is commonly used for automatic lighting systems, such as streetlights that turn on at night.

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
  
  if (x < 300)
  {
    digitalWrite(13, HIGH);
  }
  else
  {
    digitalWrite(13, LOW);
  }
  
  delay(500);
}

