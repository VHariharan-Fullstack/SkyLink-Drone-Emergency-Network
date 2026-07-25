# SkyLink – Drone-Based Emergency Mobile Network Restorer

SkyLink is a drone-assisted emergency communication system designed to restore basic connectivity when conventional communication infrastructure fails during floods, earthquakes, cyclones, landslides, and other disasters.

The system deploys a drone carrying communication and positioning hardware over an affected region. Victims or field nodes can transmit SOS messages and GPS coordinates through LoRa. The airborne SkyLink gateway receives these packets and forwards emergency information to a rescue coordination dashboard through available cellular, Wi-Fi, or local network connectivity.

## 🚨 Problem Statement

Natural disasters can damage mobile towers, power infrastructure, and communication networks. When connectivity disappears, affected people may be unable to:

* Contact emergency services
* Share their location
* Communicate with family
* Receive evacuation information
* Report injuries or dangerous conditions

SkyLink provides a rapidly deployable communication layer that can operate independently of normal local mobile infrastructure for essential emergency messaging.

## 🎯 Objectives

* Restore basic emergency communication quickly.
* Collect SOS messages from disaster victims.
* Transmit GPS coordinates to rescue teams.
* Provide an airborne LoRa communication gateway.
* Display emergency requests on a rescue dashboard.
* Support multiple drones for wider coverage.
* Use AI-assisted positioning to improve coverage.
* Reduce emergency response time.

## 🛠️ Hardware Components

| Component              | Purpose                                                   |
| ---------------------- | --------------------------------------------------------- |
| Quadcopter Drone       | Airborne platform                                         |
| Raspberry Pi           | Main gateway computer                                     |
| ESP32                  | Sensor/LoRa communication controller                      |
| Neo-6M GPS             | Location tracking                                         |
| LoRa SX1278            | Long-range emergency messaging                            |
| GSM/4G Module          | Backhaul communication when cellular service is available |
| Camera Module          | Disaster-area monitoring                                  |
| High-Capacity Battery  | System power                                              |
| Solar Charging Station | Ground-based renewable charging support                   |

## 💻 Software Technologies

* Python
* C/C++
* Arduino Framework
* Flask
* HTML
* CSS
* JavaScript
* REST API
* JSON
* GPS/NMEA processing
* LoRa communication
* SQLite

## 🏗️ System Architecture

Victim / Emergency Node
↓
GPS Location + SOS Message
↓
LoRa SX1278
↓
SkyLink Drone
↓
ESP32 LoRa Receiver
↓
Raspberry Pi Gateway
↓
Emergency Processing System
↓
Wi-Fi / Cellular Backhaul / Local Network
↓
Rescue Coordination Dashboard
↓
Emergency Response Team

## ⚙️ Working Principle

### 1. Disaster Detection

A flood, earthquake, cyclone, landslide, or other disaster damages existing communication infrastructure.

### 2. Drone Deployment

Emergency personnel deploy the SkyLink drone to the affected region.

### 3. GPS Navigation

The drone navigates toward the target disaster zone using GPS coordinates.

### 4. Emergency Communication Zone

The airborne LoRa gateway provides a long-range emergency messaging channel.

### 5. SOS Transmission

A field emergency node sends:

* Device ID
* SOS message
* Latitude
* Longitude
* Timestamp
* Emergency priority

Example:

```json
{
  "device_id": "SOS-001",
  "type": "MEDICAL",
  "latitude": 13.0827,
  "longitude": 80.2707,
  "message": "Person injured. Medical assistance required.",
  "priority": "HIGH"
}
```

### 6. Drone Reception

The LoRa module installed on the drone receives the emergency packet.

### 7. Gateway Processing

The Raspberry Pi processes the received information and stores the emergency request.

### 8. Rescue Dashboard

Emergency personnel can view:

* SOS requests
* Victim coordinates
* Emergency type
* Priority
* Time received
* Device identifier
* Current response status

### 9. Rescue Coordination

The information helps emergency teams determine where assistance is required and prioritize rescue operations.

## 🤖 AI-Based Drone Positioning

SkyLink can use an optimization algorithm to determine an effective drone position based on:

* Number of SOS nodes
* Geographic distribution
* Signal strength
* Drone altitude
* Remaining battery
* Communication range
* Disaster boundaries

A simplified objective can be represented as:

```text
Optimal Position =
Maximum User Coverage
+ Maximum Signal Quality
- Energy Consumption
```

Future implementations can use clustering, reinforcement learning, or optimization algorithms for multi-drone positioning.

## 📡 Multi-Drone Communication

For large disaster zones, several SkyLink drones can cooperate.

```text
Ground Node
     |
   Drone A
   /     \
Drone B  Drone C
   \     /
 Rescue Gateway
```

This architecture can extend coverage and provide redundancy if one drone becomes unavailable.

## 📂 Repository Structure

```text
SkyLink/
│
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
│
├── esp32/
│   ├── sos_transmitter/
│   │   └── sos_transmitter.ino
│   │
│   └── drone_receiver/
│       └── drone_receiver.ino
│
├── raspberry_pi/
│   ├── gateway.py
│   ├── gps_service.py
│   ├── emergency_processor.py
│   └── database.py
│
├── dashboard/
│   ├── app.py
│   ├── templates/
│   │   └── index.html
│   └── static/
│       ├── style.css
│       └── script.js
│
├── ai/
│   └── positioning.py
│
├── simulation/
│   └── emergency_simulator.py
│
├── config/
│   └── config.example.json
│
├── tests/
│   ├── test_gateway.py
│   └── test_positioning.py
│
└── docs/
    ├── architecture.md
    ├── hardware.md
    ├── communication.md
    └── deployment.md
```

## 🧠 Emergency Priority System

Emergency requests can be classified into different priority levels.

| Priority | Example                            |
| -------- | ---------------------------------- |
| CRITICAL | Life-threatening medical emergency |
| HIGH     | Injured or trapped person          |
| MEDIUM   | Food, water, or shelter request    |
| LOW      | General communication request      |

Critical requests appear first on the rescue dashboard.

## 🔋 Power Management

SkyLink is designed to reduce unnecessary power consumption.

Battery-saving strategies include:

* Adaptive communication intervals
* GPS sampling optimization
* LoRa sleep modes
* Raspberry Pi service management
* Mission-based drone deployment
* Return-to-base battery threshold

A solar-assisted **ground charging station** can be used to recharge batteries between missions.

## 🌱 Sustainability

SkyLink provides long-term value because the same system can be repeatedly deployed across different disaster scenarios.

Solar-assisted ground charging can reduce dependence on grid electricity during extended emergency operations. The modular architecture also allows individual communication, computing, or drone components to be replaced without rebuilding the complete system.

## 🌍 Applications

* Flood rescue
* Earthquake response
* Cyclone recovery
* Landslide rescue
* Forest operations
* Remote-area emergencies
* Search-and-rescue missions
* Temporary event communication
* Defense communication backup

## 📈 Expected Outcomes

* Faster emergency communication restoration
* Improved rescue-team coordination
* Accurate transmission of victim locations
* Better prioritization of emergency requests
* Reduced dependence on damaged terrestrial infrastructure
* Scalable disaster-area coverage

## 🚀 Future Enhancements

* Multi-drone autonomous coordination
* AI-based route planning
* Automatic victim detection using computer vision
* Voice-based SOS communication
* Offline emergency mobile application
* LoRa mesh networking
* Real-time disaster mapping
* Satellite backhaul
* Thermal camera integration
* Drone docking and automated charging
* Advanced network security
* Integration with official disaster-management systems

## ⚠️ Prototype Scope

SkyLink should not be represented as a replacement for a licensed commercial 4G/5G cellular base station.

The prototype demonstrates the core concept through an independent emergency communication network using LoRa and a drone-mounted gateway. Cellular modules can provide backhaul connectivity when an external cellular network remains reachable.

Deploying an actual LTE/5G airborne base station requires specialized radio hardware, spectrum authorization, telecom-core integration, aviation compliance, and coordination with network operators and government authorities.

## 🏆 Innovation

SkyLink combines:

**Drone Technology + IoT + LoRa + GPS + AI + Emergency Communication**

The project demonstrates how rapidly deployable aerial communication infrastructure could support disaster-management teams when conventional communication systems are unavailable.

## 👨‍💻 Author

**Hariharan V**

B.Tech – Artificial Intelligence and Data Science

## 📜 License

This project can be released under the MIT License for educational and research purposes.
