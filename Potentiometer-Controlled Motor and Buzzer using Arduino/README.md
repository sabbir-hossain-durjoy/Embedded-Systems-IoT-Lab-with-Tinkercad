# 🔊 Arduino DC Motor & Buzzer Control Using Potentiometer

## 🔗 Tinkercad Project
[View My Circuit on Tinkercad](https://www.tinkercad.com/things/1ZKEKGgpvFi-grand-amberis/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard&sharecode=b5rUwyfypB58dK43ML3XztYc2rewS8eIF38UeaI3H7U)

---

## 🛠 Equipment List
1. **Arduino Uno board**
2. **USB cable** (for programming and power)
3. **DC motor**
4. **Piezo buzzer**
5. **Potentiometer (10kΩ)**
6. **220Ω resistors** (for motor and buzzer control)
7. **Jumper wires** (Male-to-Male)

---

## 📄 Experiment Description
This experiment controls both a DC motor and a buzzer using a potentiometer. The potentiometer sends an analog input to the Arduino, representing its rotation position. If the potentiometer value falls below a set threshold (in this case, 500), the Arduino turns on both the motor and the buzzer. If the value is above the threshold, both devices are turned off. This setup can be used in warning or alert systems where a certain adjustable level triggers multiple outputs simultaneously.

---

## 💻 Arduino Code
```cpp
void setup()
{
  pinMode(12, OUTPUT);
  pinMode(13, OUTPUT);
}

void loop()
{
  int x = analogRead(A0);
  
  if (x < 500)
  {
    digitalWrite(12, HIGH);
    digitalWrite(13, HIGH);
  }
  else
  {
    digitalWrite(12, LOW);
    digitalWrite(13, LOW);
  }
  
  delay(500);
}

