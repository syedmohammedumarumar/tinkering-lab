# ✅ **EXPERIMENT 8 – FINAL EXAM WRITE-UP**

---

## 🎯 **Aim**

To design a **Bluetooth controlled door lock system using Arduino**.

---

## 🔧 **Components Required**

* Arduino UNO
* Bluetooth Module (HC-05)
* Servo Motor (SG90)
* Jumper wires
* Power supply

---

## 📘 **Theory (WRITE SHORT ONLY)**

* **HC-05 Bluetooth module** is used for wireless communication.
* It receives data from a mobile phone.
* Arduino reads the received data and controls the **servo motor**.
* Servo rotates to **lock or unlock the door**.

👉 (Optional line for extra marks)
Used in **smart home automation systems**.

---

## ⚙️ **Procedure (SHORT & CLEAR)**

### 🔹 Connections:

* Bluetooth Module:

  * VCC → 5V
  * GND → GND
  * TX → Arduino RX (Pin 0)
  * RX → Arduino TX (Pin 1)

* Servo Motor:

  * VCC → 5V
  * GND → GND
  * Signal → Pin 7

---

### 🔹 Steps:

1. Connect all components properly
2. Open Arduino IDE
3. Upload the code
4. Pair mobile with Bluetooth module
5. Send command (‘1’ or ‘0’)
6. Observe servo movement

---

## 💻 **Code (WRITE THIS)**

```cpp id="exp8exam"
#include <Servo.h>

Servo myservo;
char data = 0;

void setup() {
  myservo.attach(7);
  Serial.begin(9600);
}

void loop() {
  if (Serial.available() > 0) {
    data = Serial.read();

    if (data == '1') {
      myservo.write(90); // Lock
    }
    else if (data == '0') {
      myservo.write(0);  // Unlock
    }
  }
}
```

---

## 📊 **Output**

* Sending **‘1’** → Door **locks**
* Sending **‘0’** → Door **unlocks**

---

## ✅ **Result**

Thus, **Bluetooth controlled door lock system was successfully implemented using Arduino**.

---

# 🧠 **EXAM TIPS**

* Write keyword: **wireless communication**
* Mention **HC-05 module**
* Draw diagram:

  * HC-05 ↔ Arduino
  * Servo → Pin 7
* Write **‘1’ and ‘0’ condition** clearly

---
