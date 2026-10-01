# ATX-Bench-Power-Supply
#Project 1: ATX Bench Power Supply

---

## 1. Project Summary & Requirements

* **Project Revision:** v1.0
* **Team Members:**
  * Theerasit Khlaysamniang (6809107660130)
  * Ploypeataii Khumphongphan (6809107660059)
* **Source PSU Make/Model:** Lemel computer power supply 500W
* **Project Summary:** Repurposing an enclosed standard ATX power unit into a multi-rail benchtop lab supply, integrating dedicated fixed DC voltage rails alongside a variable buck-boost regulator circuit.
* **Accepted Requirements:**
  * Route standard output voltages (+3.3V, +5V, +12V, -12V) to clearly marked output binding posts / banana sockets.
  * Implement individual fuse protection on each active positive and negative rail.
  * Integrate an external DC-DC buck-boost module for flexible voltage and current regulation.
  * Install an external power switch (PS_ON) with dedicated LED status indicators for standby and active operation.

---

## 2. Safety Considerations

Safety was strictly considered throughout the modification process:
* **Safety Boundary:** The original ATX enclosure remains closed at all times. All wiring work is performed only after physically disconnecting the AC power cable.
* **Risk Assessment:** Primary hazards include output short circuits, excessive current draw, incorrect fuse rating selection, and thermal overload. Fuses are installed on all accessible output branches.
* **Stop Conditions:** Immediately halt testing and remove AC power if unstable voltage, unexpected current, blown fuses, unusual odors, or excessive heat is detected.

---

## 3. Power Supply Specifications

The original power supply is a **Lemel ATX500W** unit with a maximum combined power rating of 500 W[cite: 13].

| Output Rail | Protection | Output Terminal | Application / Purpose |
| :--- | :--- | :--- | :--- |
| **+3.3 V**[cite: 13] | Fuse | Banana Jack | Microcontroller circuits (ESP32, ARM) |
| **+5 V**[cite: 13] | Fuse | Banana Jack | Logic circuits, Arduino, USB power |
| **+12 V**[cite: 13] | Fuse | Banana Jack | Motors, fans, high-current DC loads |
| **-12 V**[cite: 13] | Fuse | Banana Jack | Op-Amp and audio circuits |
| **+5 VSB**[cite: 13] | Internal | Indicator LED | Standby indicator power |
| **0 - 30 V (Adj.)** | Fuse + V/A Meter | Banana Jack | Variable regulated bench output |
| **GND (0 V)** | Common Return | Banana Jack (Black) | Common ground reference |

---

## 4. Schematic & Circuit Design

[Project.1_.ATX.Bench.Power.Supply.pdf](https://github.com/user-attachments/files/32916661/Project.1_.ATX.Bench.Power.Supply.pdf)



---

## 5. Controls & Indicator Implementation

* **Power Switch (`PS_ON#`):** Pulls the green ATX wire down to `GND` via a latching toggle switch (`SW1`) to turn on the main power rails.
* **Standby Indicator:** A dedicated LED powered from the `+5VSB` rail turns ON immediately once AC mains is connected.
* **Power OK Indicator:** Connected to `PWR_OK` (Pin 8) to indicate stable output rails across the system.
* **Variable Regulator:** Uses an `XY-SJVA-4X` buck-boost module:
  * **RV1 (50k):** Voltage regulation (CV)
  * **RV2 (1k):** Current limiting (CC)
