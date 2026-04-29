# ✅ **EXPERIMENT 6 – FINAL EXAM WRITE-UP**

---

## 🎯 **Aim**

To implement a **smart railway gate system using Arduino**.

---

## 🔧 **Components Required**

* Arduino UNO
* Ultrasonic Sensor (HC-SR04)
* Servo Motor (SG90)
* Jumper wires

---

## 📘 **Theory (WRITE SHORT ONLY)**

* **Ultrasonic sensor** detects the train by measuring distance.
* When an object (train) comes close, Arduino sends signal to **servo motor**.
* Servo motor rotates to **close/open the gate automatically**.

👉 (Optional line)
Used for **automatic railway crossing systems**.

---

## ⚙️ **Procedure (SHORT & CLEAR)**

### 🔹 Connections:

* Ultrasonic Sensor:

  * VCC → 5V
  * GND → GND
  * TRIG → Pin 9
  * ECHO → Pin 10

* Servo Motor:

  * VCC → 5V
  * GND → GND
  * Signal → Pin 7

---

### 🔹 Steps:

1. Connect all components as above
2. Open Arduino IDE
3. Install **Servo library**
4. Upload the code
5. Run the circuit
6. When object is near → gate closes
7. When object is far → gate opens

---

## 💻 **Code**

```cpp id="sr6kq2"
#include <Servo.h>

Servo myservo;

#define TRIG_PIN 9
#define ECHO_PIN 10

long duration;
int distance;

void setup() {
  myservo.attach(7);
  pinMode(TRIG_PIN, OUTPUT);
  pinMode(ECHO_PIN, INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(TRIG_PIN, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIG_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG_PIN, LOW);

  duration = pulseIn(ECHO_PIN, HIGH);
  distance = duration * 0.034 / 2;

  if (distance <= 10) {
    myservo.write(90); // close gate
  } else {
    myservo.write(0);  // open gate
  }

  delay(500);
}
```

---

## 📊 **Output**

* If object detected (train near) → **Gate closes (servo rotates)**
* If no object → **Gate opens**

---

## ✅ **Result**

Thus, **smart railway gate system was successfully implemented using Arduino**.

---

# 🧠 **EXAM TIPS**

* Draw diagram:

  * Ultrasonic → Pins 9,10
  * Servo → Pin 7
* Write keyword: **automation**
* Mention **distance detection**

---

