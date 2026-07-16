# 🔥 FireLink-X

> **A Smart Fire Detection & Long-Range Alert System using ESP32 and LoRa (SX1278)**

FireLink-X is an IoT-based fire detection system designed to provide real-time fire alerts over long distances using LoRa communication. The system continuously monitors the environment using a flame sensor. When a fire is detected, an alert is transmitted wirelessly from the sender node to the receiver node, where a buzzer , send a mail to user of alert and LED notify the user instantly.

---

## 📌 Features

-Real-time fire detection using a digital flame sensor.
-Long-range wireless communication using LoRa (SX1278/RA-02).
-ESP32-based distributed sender and receiver architecture.
-Instant LED and buzzer alerts upon fire detection.
-Automatic email notification to registered users.
-Low-power operation suitable for continuous monitoring.
-Internet-independent communication between sensor nodes.
-Reliable long-distance data transmission with minimal latency.
-Modular architecture supporting future expansion.

---

## 🏗️ System Architecture
The FireLink-X system is divided into two primary modules: the Fire Detection Node and the Monitoring & Alert Node.

The Fire Detection Node consists of an ESP32 microcontroller connected to a digital flame sensor and an SX1278 LoRa transceiver. The ESP32 continuously monitors the sensor output and generates an emergency packet whenever a fire event is detected.

The Monitoring & Alert Node consists of another ESP32 connected to a LoRa receiver, an LED indicator, and an active buzzer. The receiver validates incoming LoRa packets and immediately activates both visual and audible alarms. Simultaneously, it establishes a Wi-Fi connection and sends an automated email notification containing the fire alert information to the registered recipient.

This dual-layer communication architecture combines the long-range capabilities of LoRa with the global accessibility of internet-based email notifications, providing both local and remote emergency awareness.

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
## Working Principle

The system continuously monitors the environment using a digital flame sensor connected to the sender ESP32. During normal operation, the sender remains in monitoring mode while periodically checking the sensor output.
When a flame is detected, the ESP32 immediately identifies the event as an emergency condition and constructs a predefined alert packet. This packet is transmitted through the SX1278 LoRa module using long-range wireless communication.
The receiver node continuously listens for incoming LoRa packets. Upon successfully receiving the emergency message, the receiver validates the packet and performs multiple actions simultaneously. It activates the LED indicator, sounds the buzzer to alert nearby personnel, and connects to the configured Wi-Fi network to transmit an email notification to the registered user.
Once the fire condition has been cleared, the system automatically returns to its monitoring state, ready to detect future events without requiring manual intervention.

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

---

## Project Image

<table>
  <tr>
    <td align="center">
      <b>Sender Node</b><br>
      <img src="FireLink-X/images/Sender .jpeg" width="400" alt="Sender Circuit">
    </td>
    <td align="center">
      <b>Receiver Node</b><br>
      <img src="FireLink-X/images/Reciever .jpeg" width="400" alt="Receiver Circuit">
    </td>
  </tr>
</table>

---
## Applications
FireLink-X can be deployed in numerous environments where early fire detection is essential, including industrial facilities, warehouses, manufacturing plants, agricultural fields, forests, electrical substations, oil and gas installations, commercial buildings, educational institutions, and disaster management systems. The system is particularly valuable in remote areas where conventional wired fire alarm systems are difficult or expensive to install.

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
## Advantages

FireLink-X offers several significant advantages over conventional fire detection systems. It provides reliable long-range wireless communication without requiring internet connectivity between sensor nodes, consumes very little power, and is highly scalable due to its modular architecture. The combination of local alarms and remote email notifications ensures rapid emergency response while maintaining a low deployment cost. The use of open-source hardware and software also makes the system suitable for educational, research, and industrial applications.

## 🔮 Future Enhancements

- Smoke Detection (MQ-2 / MQ-135)
- Temperature Monitoring
- GPS Location Tracking
- GSM / SMS Alerts
- Mobile Application
- Cloud Dashboard
- Multi-Node LoRa Network

---
## Conclusion

FireLink-X demonstrates an efficient and reliable approach to modern fire detection by integrating IoT technology, long-range LoRa communication, and embedded systems. The project successfully combines real-time flame detection with wireless emergency communication and remote email notifications, creating a practical solution for early fire warning in both urban and remote environments. Its scalable architecture, low power consumption, and cost-effective design make it a strong foundation for future smart safety systems and industrial monitoring applications.

--

## 👨‍💻 Team

**NeoGen Innovators**

---


## ⭐ Support

If you found this project useful, please consider giving it a **⭐ Star** on GitHub.
