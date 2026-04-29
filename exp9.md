# ✅ **EXPERIMENT 9 – FINAL EXAM WRITE-UP**

---

## 🎯 **Aim**

To implement a **smart dustbin using ultrasonic sensor and servo motor**.

---

## 🔧 **Components Required**

* Arduino UNO
* Ultrasonic Sensor (HC-SR04)
* Servo Motor (SG90/MG90)
* Jumper wires
* Power supply / USB cable

---

## 📘 **Theory (WRITE SHORT ONLY)**

* A **smart dustbin** uses an ultrasonic sensor to detect nearby objects.
* When a hand is placed near the sensor, it measures the distance.
* Arduino processes this signal and controls the **servo motor**.
* The servo motor opens the lid automatically and closes after some time.

👉 (Optional line for extra marks)
Used for **hygienic and touch-free waste disposal systems**.

---

## ⚙️ **Procedure (SHORT & CLEAR)**

### 🔹 Connections:

**Servo Motor:**

* VCC (Red) → 5V
* GND (Brown) → GND
* Signal → Pin 6

**Ultrasonic Sensor:**

* VCC → 5V
* GND → GND
* TRIG → Pin 9
* ECHO → Pin 10

---

### 🔹 Steps:

1. Connect all components properly
2. Install **Servo library** in Arduino IDE
3. Upload the code
4. Place hand near sensor
5. If object is near → lid opens
6. If object is far → lid closes

---

## 💻 **Code (AS PER PDF)**

```cpp id="exp9final"
#include <Servo.h>

// Define pins
const int trigPin = 9;
const int echoPin = 10;
const int servoPin = 6;

long duration;
int distance;

Servo myservo;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  myservo.attach(servoPin);
  myservo.write(0);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  if (distance > 0 && distance <= 15) {
    myservo.write(180);
  } 
  else if (distance >= 15) {
    myservo.write(0);
  }

  delay(100);
}
```

---

## 📊 **Output**

* If object distance ≤ 15 cm → **Dustbin lid opens (servo rotates 180°)**
* If object distance > 15 cm → **Dustbin lid closes (servo returns to 0°)**

---

## ✅ **Result**

Thus, **smart dustbin using ultrasonic sensor and servo motor was successfully implemented**.

---

# 🧠 **EXAM TIPS (VERY IMPORTANT)**

* Write keyword: **automatic / touch-free system**
* Mention **distance detection**
* Draw diagram:

  * Ultrasonic → Pins 9,10
  * Servo → Pin 6
* Write condition clearly (**≤15 cm**)

---

