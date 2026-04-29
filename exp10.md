# ✅ **EXPERIMENT 10 – FINAL EXAM WRITE-UP**

---

## 🎯 **Aim**

To implement an **RFID based attendance system using Arduino**.

---

## 🔧 **Components Required**

* Arduino UNO
* RFID Reader (RC522)
* RFID Tags/Cards
* Jumper wires

---

## 📘 **Theory (WRITE SHORT ONLY)**

* **RFID (Radio Frequency Identification)** is used to identify objects using radio waves.
* It consists of **RFID tag and reader**.
* The reader sends signals and the tag responds with a **unique ID**.
* Arduino reads this ID and matches with stored data to mark attendance.

👉 (Optional line for extra marks)
Provides **automatic, accurate, and secure attendance system**.

---

## ⚙️ **Procedure (SHORT & CLEAR)**

### 🔹 Connections (RC522 → Arduino UNO):

* SDA → D10
* SCK → D13
* MOSI → D11
* MISO → D12
* RST → D9
* GND → GND
* 3.3V → 3.3V

---

### 🔹 Steps:

1. Connect RFID module to Arduino
2. Install required libraries (**MFRC522, SPI**)
3. Upload the code
4. Place RFID card near reader
5. Arduino reads UID
6. If UID matches → attendance marked
7. Else → access denied

---

## 💻 **Code (AS PER PDF)**

```cpp id="exp10final"
#include <SPI.h>
#include <MFRC522.h>

#define SS_PIN 53
#define RST_PIN 5

MFRC522 rfid(SS_PIN, RST_PIN);

String knownUIDs[][2] = {
 {"A307DBD9", "Suhail"},
 {"BD202D5B", "Tharun"},
 {"FA01B3AB", "Ganesh"},
 {"8E68973F", "Rafi"},
 {"36B0C693","Borah"},
 {"E67EC593","Arivarasu"}
};

const int numUsers = sizeof(knownUIDs) / sizeof(knownUIDs[0]);

void setup() {
  Serial.begin(9600);
  SPI.begin();
  rfid.PCD_Init();

  Serial.println("RFID Attendance System Initialized");
}

void loop() {
  if (!rfid.PICC_IsNewCardPresent() || !rfid.PICC_ReadCardSerial()) {
    return;
  }

  String uid = "";
  for (byte i = 0; i < rfid.uid.size; i++) {
    if (rfid.uid.uidByte[i] < 0x10) uid += "0";
    uid += String(rfid.uid.uidByte[i], HEX);
  }
  uid.toUpperCase();

  Serial.print("Card UID: ");
  Serial.println(uid);

  bool known = false;

  for (int i = 0; i < numUsers; i++) {
    if (uid == knownUIDs[i][0]) {
      known = true;
      Serial.print("Welcome, ");
      Serial.println(knownUIDs[i][1]);
      break;
    }
  }

  if (!known) {
    Serial.println("Access Denied");
  }

  delay(2000);
  rfid.PICC_HaltA();
  rfid.PCD_StopCrypto1();
}
```

---

## 📊 **Output**

* If card matches → **Name displayed + Attendance marked**
* If not matched → **Access denied**

---

## ✅ **Result**

Thus, **RFID based attendance system was successfully implemented using Arduino**.

---

# 🧠 **EXAM TIPS (VERY IMPORTANT)**

* Write keyword: **UID (Unique ID)**
* Mention **RFID tag + reader**
* Draw diagram:

  * RC522 → Arduino (SPI pins)
* Write **matching condition** clearly

