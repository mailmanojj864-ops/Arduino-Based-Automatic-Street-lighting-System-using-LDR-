# Arduino-Based-Automatic-Street-lighting-System-using-LDR-
An automatic street lighting system using LDR and Arduino, simulated in Tinkercad
# 🌃 Automatic Street Light Using LDR

## 📌 Project Overview
This project demonstrates an *automatic street light system* using an *LDR (Light Dependent Resistor)* and *Arduino UNO*.  
The street light automatically *turns ON during darkness* and *turns OFF during daylight*, helping in energy conservation.

---

## ⚙️ Components Used
- Arduino UNO
- LDR (Photoresistor)
- LED
- 10kΩ Resistor
- 220Ω Resistor
- Breadboard
- Jumper Wires

---

## 🔌 Circuit Description
The LDR and 10kΩ resistor are connected as a *voltage divider* to the Arduino analog pin A0.  
The LED is connected to a digital pin through a current-limiting resistor.

- *Dark condition* → LDR resistance increases → LED ON  
- *Bright condition* → LDR resistance decreases → LED OFF  

---

## 🧠 Working Principle
An LDR changes its resistance based on light intensity.  
Arduino reads this change using analogRead() and controls the LED accordingly.

---

## 💻 Arduino Code
```c
int ldrPin = A0;
int ledPin = 9;
int ldrValue = 0;

void setup()
{
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  ldrValue = analogRead(ldrPin);

  if (ldrValue < 500)
  {
    digitalWrite(ledPin, HIGH);  // LED ON in darkness
  }
  else
  {
    digitalWrite(ledPin, LOW);   // LED OFF in light
  }

  delay(2000);
}
