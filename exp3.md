

# ✅ **EXPERIMENT 3 – FINAL EXAM WRITE-UP**

---

## 🎯 **Aim**

To detect **water level using ultrasonic sensor and Arduino**.

---

## 🔧 **Components Required**

* Arduino UNO
* Ultrasonic Sensor (HC-SR04)
* Breadboard
* Jumper wires
* Power supply (5V)

---

## 📘 **Theory (WRITE SHORT ONLY)**

* **Ultrasonic sensor** measures distance using sound waves.
* It sends a signal and receives the echo back.
* Distance is calculated using:

[
\text{Distance} = \frac{\text{Time × Speed of Sound}}{2}
]

* Water level is calculated as:

[
\text{Water Level} = \text{Tank Height} - \text{Distance}
]

👉 (Optional line)
Used for **non-contact measurement of water level**.

---

## ⚙️ **Procedure (SHORT & CLEAR)**

1. Place ultrasonic sensor on breadboard
2. Connect:

   * VCC → 5V
   * GND → GND
   * TRIG → Pin 9
   * ECHO → Pin 10
3. Write code in Arduino IDE
4. Upload code to Arduino
5. Open Serial Monitor
6. Observe distance and water level

---

## 💻 **Code**

```cpp id="wl8kq2"
#define TRIG_PIN 9
#define ECHO_PIN 10

const int tankHeight = 30;

void setup() {
  pinMode(TRIG_PIN, OUTPUT);
  pinMode(ECHO_PIN, INPUT);
  Serial.begin(9600);
}

void loop() {
  long duration;
  int distance;

  digitalWrite(TRIG_PIN, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIG_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG_PIN, LOW);

  duration = pulseIn(ECHO_PIN, HIGH);
  distance = duration * 0.034 / 2;

  int waterLevel = tankHeight - distance;

  Serial.print("Water Level: ");
  Serial.print(waterLevel);
  Serial.println(" cm");

  delay(1000);
}
```

---

## 📊 **Output**

* Distance displayed in **cm**
* Water level displayed in **cm**
* If no water → **“Tank Empty”**

---

## ✅ **Result**

Thus, **water level was successfully measured using ultrasonic sensor and Arduino**.

---

# 🧠 **EXAM TIPS (VERY IMPORTANT)**

* Draw diagram: **HC-SR04 → Arduino (Trig-9, Echo-10)**
* Write formula → guaranteed marks
* Mention **echo + time of flight** → important keyword

---

