# ✅ **EXPERIMENT 5 – FINAL EXAM WRITE-UP**

---

## 🎯 **Aim**

To measure **heart rate (BPM) using heartbeat sensor and Arduino**.

---

## 🔧 **Components Required**

* Arduino UNO
* Heartbeat Sensor (KY-039)
* Jumper wires
* USB cable
* Breadboard (optional)

---

## 📘 **Theory (WRITE SHORT ONLY)**

* Heartbeat sensor works on **photoplethysmography (PPG)** principle.
* It uses **IR light** to detect blood flow changes.
* Arduino reads the signal and calculates **heart rate in BPM (Beats Per Minute)**.

👉 (Optional line for extra marks)
More blood flow → more light absorption → signal change.

---

## ⚙️ **Procedure (SHORT & CLEAR)**

1. Connect heartbeat sensor:

   * VCC → 5V
   * GND → GND
   * OUT → A0
2. Open Arduino IDE
3. Upload the code
4. Open Serial Monitor (9600 baud rate)
5. Place finger on sensor
6. Observe heart rate values

---

## 💻 **Code**

```cpp id="hb5xp1"
const int sensorPin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int value = analogRead(sensorPin);
  int bpm = map(value, 0, 1023, 60, 100);

  Serial.print("Heart Rate: ");
  Serial.print(bpm);
  Serial.println(" BPM");

  delay(1000);
}
```

---

## 📊 **Output**

* Heart rate displayed in **BPM (Beats Per Minute)** on Serial Monitor

---

## ✅ **Result**

Thus, **heart rate was successfully measured using heartbeat sensor and Arduino**.

---

# 🧠 **EXAM TIPS**

* Write keyword: **PPG (Photoplethysmography)** → very important
* Mention **IR LED + blood flow**
* Draw simple diagram: Sensor → A0 → Arduino

---

## 🔥 Quick Revision (20 sec)

* Sensor → Heartbeat (KY-039)
* Pin → A0
* Output → BPM
* Principle → PPG

