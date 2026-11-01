# 🛡️ OT Cyber Defense Simulator: Hybrid Power Plant (IEC 62443)

An interactive, browser-based cybersecurity training game and simulation built around a utility-scale **Hybrid Renewable Power Plant (Solar PV + Organic PV + BESS)**. 

The game challenges OT engineers, cybersecurity practitioners, and SCADA operators to enforce defense-in-depth segmentation following the **Purdue Model for Industrial Control Systems (ICS)** and **IEC 62443** standards.

![Game Banner](https://img.shields.io/badge/Standards-IEC_62443_SL--2-00f0ff?style=for-the-badge)
![Purdue Levels](https://img.shields.io/badge/Purdue_Model-Level_0_to_4-00ff66?style=for-the-badge)
![Platform](https://img.shields.io/badge/Deployment-GitHub_Pages-a855f7?style=for-the-badge)

---

## ⚡ Target Power Plant Infrastructure

The simulation models an active 80 MW hybrid generation facility comprising:
* **Solar PV Array (50 MW):** Ground-mounted bifacial silicon PV strings driven by single-axis tracker controllers (**PVH TBox/MBox/DBox**) and central/string inverters.
* **Organic Photovoltaics Array (10 MW):** Flexible printed OPV thin-film modules paired with wide-range MPPT string inverters on serial RS485 loops.
* **Battery Energy Storage System (20 MW / 40 MWh):** 1500V DC LFP battery containers, Master BMS controllers, and 4-quadrant bi-directional Power Conversion System (PCS) inverters.
* **High-Voltage Substation:** Main Step-Up Transformer (33 kV / 110–400 kV), HV Switchgear, Protection Relays & IEDs executing **IEC 61850 GOOSE/MMS**, and POI Class 0.2S Revenue Power Metering.

---

## 🎮 Game Modes & Objectives

### 1. Mode 1: Architecture & Topology Fix (Drag-and-Drop)
* **Goal:** Assign unallocated security appliances and network policies to their appropriate Purdue Level zone.
* **Mechanics:** Drag items from your inventory into designated drop zones. Placing items in incorrect zones triggers policy rejections; placing them correctly increases your Security Score.
* **Deployable Assets:**
  * **Level 4:** Enterprise ZTNA Firewall
  * **Level 3.5 (DMZ):** WALLIX PAM / MFA Vault, Unidirectional DMZ Reverse Proxy
  * **Level 3:** SIEM Log Collector Server, WSUS Patch & Firmware Server, EDR Console
  * **Level 2:** IEC 61850 Substation Protection VLAN Rule
  * **Level 1:** OPV RS485 Opto-Isolation Gateway

### 2. Mode 2: Real-Time Incident Response Simulator
* **Goal:** Detect and mitigate active cyberattacks across Level 0 to Level 4 before plant power output drops or equipment suffers physical damage.
* **Scenarios Included:**
  * **L1 Modbus TCP Spoofing:** Rogue field laptop injecting unauthorized inverter power limits.
  * **Direct RDP WAN Bypass:** Compromised IT contractor credentials attempting direct RDP to SCADA Masters.
  * **Lateral SMB Ransomware Worm:** Unpatched SMBv1 exploit spreading across Level 3 HMIs and Engineering Workstations.
  * **Substation GOOSE ARP Poisoning:** Man-in-the-Middle spoofing on the sub-4ms substation protection bus.

### 3. Mode 3: IEC 62443 / NIS 2 Audit
* **Goal:** Complete a regulatory compliance audit by answering technical OT/ICS security questions covering:
  * Perimeter protection & Industrial DMZ enforcement (IEC 62443-3-3).
  * Substation Layer-2 GOOSE multicast VLAN isolation vs routed IP networks.
  * Redundant Power Plant Controller (PPC Master A/B) encrypted heartbeat validation.

---

## 📊 Live HUD & Performance Metrics

* **Budget ($):** Start with **$100,000** capital allocation to purchase security equipment or emergency Deep Packet Inspection (DPI) shields.
* **Security Score (%):** Overall defense posture rating based on correct topology segmentation and audit accuracy. Target compliance is **85%+ (SL-2)**.
* **Plant Output (MW):** Real-time generation capacity (starts at **80.0 MW**). Failed incident responses or uncontained attacks trigger power curtailment or total plant trips.
* **SIEM Console Logs:** Real-time event logging terminal outputting timestamped audit trails and incident alerts.

---

## 🛠️ Tech Stack & Requirements

* **Frontend:** Single-file HTML5 application using **Tailwind CSS** (via CDN) and **Font Awesome 6**.
* **Fonts:** `Chakra Petch` (Industrial Cyber UI) and `JetBrains Mono` (Terminal Data Display).
* **Dependencies:** None! Zero build step required. Runs directly in any modern web browser or hosted via **GitHub Pages**.

---

## 🚀 How to Run & Host

### Local Execution:
Simply open `ot_cyber_defense_game.html` in Chrome, Firefox, Edge, or Safari.

### Hosting on GitHub Pages:
1. Copy `ot_cyber_defense_game.html` to your GitHub repository and rename it to `index.html`.
2. Go to **Settings > Pages** in your GitHub repository.
3. Under **Source**, select `Deploy from a branch` and choose `main` / root.
4. Save settings and launch your live URL!

---

## 📜 Standards & References

* **IEC 62443-3-3:** System Security Requirements and Security Levels.
* **Purdue Model:** Computer-Integrated Manufacturing (CIM) Reference Model for ICS.
* **IEC 61850-8-1:** Communication Networks and Systems for Power Utility Automation (GOOSE/MMS).
* **NIS 2 Directive:** Essential Entity Cybersecurity Capabilities for Energy Infrastructure.