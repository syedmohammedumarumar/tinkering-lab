
# ✅ **EXPERIMENT 4 – FINAL EXAM WRITE-UP**

---

## 🎯 **Aim**

To design an **automatic plant watering system using Arduino**.

---

## 🔧 **Components Required**

* Arduino UNO
* Soil Moisture Sensor
* Water Pump / Motor
* Relay Module
* Breadboard
* Jumper wires
* Power supply

---

## 📘 **Theory (WRITE SHORT ONLY)**

* **Soil moisture sensor** detects water content in soil.
* It gives **analog output** based on moisture level.
* Arduino reads this value and compares with a threshold.
* If soil is dry → motor turns ON → water supplied
* If soil is wet → motor turns OFF

👉 (Optional line)
Used in **smart irrigation systems**.

---

## ⚙️ **Procedure (SHORT & CLEAR)**

### 🔹 Connections:

* Soil Sensor:

  * VCC → 5V
  * GND → GND
  * A0 → Arduino A0

* Relay Module:

  * IN → Pin 7
  * VCC → 5V
  * GND → GND

* Motor:

  * Connected through relay

---

### 🔹 Steps:

1. Connect all components properly
2. Open Arduino IDE
3. Write and upload code
4. Place sensor in soil
5. Observe readings
6. Dry soil → motor ON
7. Wet soil → motor OFF

---

## 💻 **Code (EXAM STYLE)**

```cpp
int sensorPin = A0;
int motorPin = 7;
int threshold = 400;

void setup() {
  pinMode(motorPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int moisture = analogRead(sensorPin);

  Serial.print("Moisture: ");
  Serial.println(moisture);

  if (moisture > threshold) {
    digitalWrite(motorPin, HIGH); // Motor ON
    Serial.println("Soil Dry - Motor ON");
  } else {
    digitalWrite(motorPin, LOW);  // Motor OFF
    Serial.println("Soil Wet - Motor OFF");
  }

  delay(1000);
}
```

---

## 📊 **Output**

* Displays moisture value
* Dry soil → **Motor ON**
* Wet soil → **Motor OFF**

---

## ✅ **Result**

Thus, **automatic plant watering system was successfully implemented using Arduino**.

---

# 🧠 **EXAM TIPS**

* Write keyword: **threshold value**
* Mention **automatic irrigation**
* Draw diagram:

  * Sensor → A0
  * Relay → Pin 7
  * Motor

---
