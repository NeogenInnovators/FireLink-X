# 🔥 FireLink-X

> **A Smart Fire Detection & Long-Range Alert System using ESP32 and LoRa (SX1278)**

FireLink-X is an IoT-based fire detection system designed to provide real-time fire alerts over long distances using LoRa communication. The system continuously monitors the environment using a flame sensor. When a fire is detected, an alert is transmitted wirelessly from the sender node to the receiver node, where a buzzer and LED notify the user instantly.

---

## 📌 Features

- 🔥 Real-time Fire Detection
- 📡 Long-Range LoRa Communication (SX1278)
- ⚡ ESP32-based Sender and Receiver Nodes
- 🚨 Instant Audio and Visual Alerts
- 🔋 Low Power Consumption
- 🌐 Internet Independent Communication
- 🛠️ Easy to Build and Expand

---

## 🏗️ System Architecture

```text
           Flame Detected
                  │
                  ▼
         ESP32 + Flame Sensor
                  │
        LoRa (SX1278 Transmission)
                  │
                  ▼
          ESP32 Receiver Node
                  │
        LED + Active Buzzer Alert
```

---

## 🧰 Hardware Components

| Component | Quantity |
|-----------|----------|
| ESP32 DevKit V1 | 2 |
| SX1278 LoRa Module (RA-02) | 2 |
| Flame Sensor Module | 1 |
| Active Buzzer | 1 |
| LED | 1 |
| 330Ω Resistor | 1 |
| Jumper Wires | As Required |
| Breadboard / PCB | 1 |

---

## 🔌 Pin Connections

### Sender Node

| ESP32 Pin | Connected Device |
|-----------|------------------|
| GPIO27 | Flame Sensor (DO) |
| GPIO5 | LoRa NSS |
| GPIO18 | LoRa SCK |
| GPIO19 | LoRa MISO |
| GPIO23 | LoRa MOSI |
| GPIO14 | LoRa RST |
| GPIO2 | LoRa DIO0 |
| 3.3V | LoRa + Flame Sensor |
| GND | Common Ground |

### Receiver Node

| ESP32 Pin | Connected Device |
|-----------|------------------|
| GPIO5 | LoRa NSS |
| GPIO18 | LoRa SCK |
| GPIO19 | LoRa MISO |
| GPIO23 | LoRa MOSI |
| GPIO14 | LoRa RST |
| GPIO2 | LoRa DIO0 |
| GPIO26 | LED |
| GPIO25 | Active Buzzer |
| 3.3V | LoRa |
| GND | Common Ground |

---

## ⚙️ Working Principle

1. The flame sensor continuously monitors the environment.
2. When fire is detected, the ESP32 sender reads the sensor output.
3. An alert message is transmitted using the LoRa SX1278 module.
4. The receiver ESP32 receives the message.
5. The LED turns ON and the buzzer sounds to indicate the fire alert.
6. If no fire is detected, the system remains in the SAFE state.

---

## 📷 Circuit Diagrams

### Sender Node

![Sender Circuit](images/Sender.png)

### Receiver Node

![Receiver Circuit](images/Reciever.png)

---

---

## 🎥 Working Demo

Watch the complete working demonstration here:

**▶️ Add your YouTube or GitHub video link here**

Example:

https://youtu.be/your-video-link

---

## 💻 Software Requirements

- Arduino IDE
- ESP32 Board Package
- LoRa Library by Sandeep Mistry

---

## 🚀 Installation

1. Clone the repository.

```bash
git clone https://github.com/yourusername/FireLink-X.git
```

2. Open the sender and receiver code in Arduino IDE.
3. Install all required libraries.
4. Select the ESP32 board.
5. Upload the sender code to the sender ESP32.
6. Upload the receiver code to the receiver ESP32.
7. Power both nodes and test the system.

---

## 📂 Project Structure

```
FireLink-X/
│
├── code/
│   ├── Sender/
│   └── Receiver/
│
├── docs/
│
├── images/
│
├── hardware/
│
├── videos/
│
└── README.md
```

---

## 🔮 Future Enhancements

- Smoke Detection (MQ-2 / MQ-135)
- Temperature Monitoring
- GPS Location Tracking
- GSM / SMS Alerts
- Mobile Application
- Cloud Dashboard
- Multi-Node LoRa Network

---

## 👨‍💻 Team

**NeoGen Innovators**

---


## ⭐ Support

If you found this project useful, please consider giving it a **⭐ Star** on GitHub.
