# ✅ **EXPERIMENT 7 – FINAL EXAM WRITE-UP**

---

## 🎯 **Aim**

To design a **fire detection system using gas sensor and Arduino**.

---

## 🔧 **Components Required**

* Arduino UNO
* Gas Sensor (MQ-6)
* Breadboard
* Jumper wires
* Power supply

---

## 📘 **Theory (WRITE SHORT ONLY)**

* **MQ-6 sensor** detects gas/smoke present in fire.
* It gives **analog output** based on gas concentration.
* Arduino reads this value and compares with a **threshold value**.
* If value exceeds threshold → **fire is detected**.

👉 (Optional line for extra marks)
Used in **fire safety and alarm systems**.

---

## ⚙️ **Procedure (SHORT & CLEAR)**

1. Place MQ-6 sensor on breadboard
2. Connect:

   * VCC → 5V
   * GND → GND
   * A0 → Arduino A0
3. Write code in Arduino IDE
4. Upload the code
5. Open Serial Monitor
6. Observe sensor values
7. If value > threshold → Fire detected

---

## 💻 **Code**

```cpp id="exp7exam"
#include<SoftwareSerial.h> 

int smokeA0 = A0; 
int sensorThres=350; 

void setup() 
{ 
  pinMode(smokeA0,INPUT); 
  Serial.begin(9600); 
} 

void loop()  
{ 
  int analogSensor = analogRead(smokeA0); 

  Serial.print("Pin A0: "); 
  Serial.println(analogSensor); 

  if (analogSensor>sensorThres) 
  { 
    Serial.println("Fire Detected"); 
  } 
  else 
  { 
    Serial.println("Fire not Detected"); 
  } 

  delay(100); 
}
```

---

## 📊 **Output**

* Displays sensor value on Serial Monitor
* If value > threshold → **“Fire Detected”**
* Else → **“Fire not Detected”**

---

## ✅ **Result**

Thus, **fire detection system was successfully implemented using Arduino and gas sensor**.

---

# 🧠 **EXAM TIPS (VERY IMPORTANT)**

* Write keyword: **threshold value**
* Mention **analog output**
* Draw diagram:

  * MQ-6 → A0 → Arduino
* Don’t forget **condition (>350)**

---
