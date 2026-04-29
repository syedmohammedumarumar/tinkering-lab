
---

# ✅ **EXPERIMENT 2 – FINAL EXAM WRITE-UP**

---

## 🎯 **Aim**

To measure **temperature and humidity using DHT11 sensor and Arduino**.

---

## 🔧 **Components Required**

* DHT11 Sensor
* Arduino UNO
* Resistors (1kΩ, 4.7kΩ)
* Breadboard
* Connecting wires

---

## 📘 **Theory (WRITE SHORT ONLY)**

* **DHT11 sensor** measures temperature (°C) and humidity (%).
* It uses **single-wire communication** to send data to Arduino.
* Arduino reads the data and displays it on **Serial Monitor/LCD**.
* Data format is **digital**, so it is accurate and reliable.

👉 (Optional line for extra marks)
DHT11 sends **40-bit data** containing temperature and humidity values.

---

## ⚙️ **Procedure (SHORT & STEPWISE)**

1. Place DHT11 sensor on breadboard
2. Connect:

   * VCC → 5V
   * GND → GND
   * DATA → Digital Pin 2
3. Open Arduino IDE
4. Install **DHT library**
5. Write and upload code
6. Open Serial Monitor
7. Observe temperature and humidity values

---

## 💻 **Code**

```cpp
#include "DHT.h"

#define DHTPIN 2
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  float t = dht.readTemperature();
  float h = dht.readHumidity();

  if (isnan(t) || isnan(h)) {
    Serial.println("Sensor error");
    return;
  }

  Serial.print("Temperature = ");
  Serial.print(t);
  Serial.println(" °C");

  Serial.print("Humidity = ");
  Serial.print(h);
  Serial.println(" %");

  delay(1000);
}
```

---

## 📊 **Output**

* Temperature displayed in **°C**
* Humidity displayed in **%**
  (on Serial Monitor)

---

## ✅ **Result**

Thus, **temperature and humidity were successfully measured using DHT11 sensor and Arduino**.

---

# 🧠 **EXAM TIPS**

* Draw **simple diagram**:

  * DHT11 → Arduino (Pin 2)
* Write **“single-wire communication”** → important keyword
* Mention **°C and %** → easy marks

---

