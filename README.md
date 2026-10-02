
## Project Summary & Requirements

* **Project Revision:** v1.0
* **Team Members:**
  * Theerasit Khlaysamniang (6809107660130)
  * Ploypeataii Khumphongphan (680910766005)
---

# ATX Bench Power Supply

## 1. System Overview & Design Specifications

### Power Supply Used
* Lemel 500 W ATX Computer Power Supply

---

### Project Concept
The original ATX power supply is redesigned into a compact bench-top DC power source. The existing voltage rails are brought to an accessible front panel, while an additional DC-DC converter provides adjustable output capability.

---

### Main Design Features
* Accessible Terminals: Route fixed DC voltages (+3.3 V, +5 V, +12 V, and −12 V) to dedicated front-panel binding posts.
* Overcurrent Protection: Add separate fuse protection to all usable output rails.
* Variable Regulation: Include an external buck-boost DC-DC converter for adjustable voltage and current control.
* Power Control: Provide a dedicated PS_ON power-control switch for operating the ATX supply externally.
* Status Indication: Integrate LED indicators to distinguish between standby and active operating states.
* Front Panel Layout: Arrange all output terminals, controls, protection fuses, and visual indicators on an ergonomic, compact front panel.

---

### Target Output Specifications

* Fixed Rail 1: +3.3 V DC (Regulated ATX Rail)
* Fixed Rail 2: +5.0 V DC (Regulated ATX Rail)
* Fixed Rail 3: +12.0 V DC (Regulated ATX Rail)
* Fixed Rail 4: −12.0 V DC (Low-Current Reference Rail)
* Variable Rail: 0–30.0 V DC (Buck-Boost Module Controlled)

---

## 2. Safety & Protection

### Electrical Safety
* Enclosure Integrity: Keep the original ATX power unit enclosed during normal operation.
* Mains Isolation: Disconnect the AC mains power cable before carrying out any wiring, inspection, or internal modification.
* Inspection Protocol: Thoroughly verify all polarity, grounding, and wiring connections before reconnecting the primary AC power source.

---

### Protection Measures
* Identified Operational Risks: Potential hazards include short circuits, excessive load current, incorrect fuse selection, and component overheating.
* Overcurrent Protection: Individual fuse protection is integrated on all accessible output channels to protect both the internal power supply circuitry and connected external loads.

---

### Testing Precautions & Emergency Shutdown
Testing must be stopped immediately if any of the following abnormal operating conditions occur:
* Unstable or fluctuating output voltage
* Unexpected or uncontrolled current flow
* Blown protection fuse
* Unusual smell or evidence of burning components
* Excessive temperature rise on heat sinks, wiring, or terminals

## 3. Power Supply Specifications

The original power supply is a **Lemel ATX500W** unit with a maximum combined power rating of 500 W[cite: 13].

| Output Rail | Protection | Output Terminal | Application / Purpose |
| :--- | :--- | :--- | :--- |
| **+3.3 V**[cite: 13] | Fuse | Banana Jack | Microcontroller circuits (ESP32, ARM) |
| **+5 V**[cite: 13] | Fuse | Banana Jack | Logic circuits, Arduino, USB power |
| **+12 V**[cite: 13] | Fuse | Cigarette Lighter Socket   | Motors, fans, high-current DC loads |
| **-12 V**[cite: 13] | Fuse | Banana Jack | Op-Amp and audio circuits |
| **+5 VSB**[cite: 13] | Internal | Indicator LED | Standby indicator power |
| **0 - 30 V (Adj.)** | Fuse + V/A Meter | Banana Jack | Variable regulated bench output |
| **GND (0 V)** | Common Return | Banana Jack (Black) | Common ground reference |
* **Nameplate Specifications:**
  * Maximum Output Capacity: 500 W
* **Connector Pin Configuration & Enclosure:**
<img width="719" height="334" alt="image" src="https://github.com/user-attachments/assets/36330599-e2db-4249-946e-5fd3748ff83c" />

* **Reference Source:** [Cirkit Designer ATX Component Documentation](https://docs.cirkitdesigner.com/component/1ce54fb2-2242-415e-a64d-dcc2a715ca80/atx-power-supply)



---

## 4. Schematic & Circuit Design
* **Final System Schematic Diagram:**
<img width="1601" height="1111" alt="image" src="https://github.com/user-attachments/assets/2b4a6b02-8c2c-4569-a396-172b2e771dfc" />
**Enclosure Mechanical & Panel Layout:**

  <img width="1076" height="1521" alt="94070" src="https://github.com/user-attachments/assets/4518c9d0-7536-4d54-8f71-afbc8ccae4fd" />

---

## 5. Photographs
* **Replacing Potentiometer 

<img width="1706" height="960" alt="94069" src="https://github.com/user-attachments/assets/887c2e54-95ca-44a7-9d93-0be7aaab2510" />

* **Include all equipment in case 

 <img width="960" height="1706" alt="94065" src="https://github.com/user-attachments/assets/cbee89f0-12fe-46a1-940c-9fcd1487fd08" />


* **Test voltage and Meter 

<img width="960" height="1706" alt="94061" src="https://github.com/user-attachments/assets/022bc891-a8cc-4c35-b653-92ee4c2970ef" />
