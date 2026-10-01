
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
| **+12 V**[cite: 13] | Fuse | Cigarette Litter | Motors, fans, high-current DC loads |
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

## 5. Engineering Calculations & Thermal Sizing

* **Overcurrent Protection Sizing:** Fast-acting inline fuses were integrated to protect the conductors, binding posts, and internal switching circuitry. The primary positive rails (+3.3V, +5V, +12V) are restricted to 10 A to prevent binding post heat damage, while the sensitive -12V rail is protected using a 0.5 A fuse to respect the PSU source threshold (0.8 A).

* **Conductor Ampacity Verification:** The internal ATX wire harness uses standard 18 AWG copper conductors rated up to 16 A for chassis wiring. By capping line currents at 10 A via fuse selection, the operating margin remains well below the thermal limits of the insulation.

* **Buck-Boost Converter Current Draw:** Powered from the +12V bus, the step-up/down regulator delivers variable output voltages. Assuming a full-load demand of 24 V at 1.5 A with a typical conversion efficiency ($\eta$) of 85%:

$$I_{in} \approx \frac{V_{out} \times I_{out}}{\eta \times V_{in}}$$

$$I_{in} \approx \frac{24 \times 1.5}{0.85 \times 12} \approx 3.53\text{ A}$$

* **Connector Contact Power Dissipation:** Considering a nominal contact resistance ($R$) of $0.01\ \Omega$ at the banana terminals under a 10 A continuous load, terminal heat loss is determined by:

$$P_{loss} = I^2 R$$

$$P_{loss} = 10^2 \times 0.01 = 1\text{ W}$$

---

##6.Photographs
* **Chang Potentiometer **

<img width="1706" height="960" alt="94069" src="https://github.com/user-attachments/assets/887c2e54-95ca-44a7-9d93-0be7aaab2510" />

* **Include all equipment in case **

 <img width="960" height="1706" alt="94065" src="https://github.com/user-attachments/assets/cbee89f0-12fe-46a1-940c-9fcd1487fd08" />


* **Test voltage and Meter **

<img width="960" height="1706" alt="94061" src="https://github.com/user-attachments/assets/022bc891-a8cc-4c35-b653-92ee4c2970ef" />
