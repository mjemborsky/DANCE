# Dual-Mode Audio Hardware Processor - Project State

## Project Overview
An inline audio hardware signal processor designed for dynamic studio tracking and vocal control. The device operates in two distinct operational modes via an active toggle switch: a passive standby processing circuit and an active noise cancellation engine.

---

## Key Hardware Components
* **Mode Toggle Switch:** Switches the signal chain between Passive Standby Mode and Active Mode.
* **De-Essing Potentiometer:** Single continuous control knob adjusting the intensity of passive sibilance reduction.
* **Balanced I/O:** Standard XLR input and output stage.

---

## Operating Modes

### 1. Passive Standby Mode
Functions without requiring primary active power, providing transparent inline dynamic control.
* **Dynamic Peak Clipper:** Hard/soft transparent clipping to tame transient spikes prior to conversion or amplification.
* **Passive De-Esser:** Dedicated analog attenuation circuit targeting high-frequency sibilance (controlled via the top-panel potentiometer).

### 2. Active Mode
Engages active processing circuitry upon flipping the mode switch.
* **Active Noise Cancellation (ANC):** Real-time phase-inversion and filter-based cancellation engine to minimize environmental background noise and floor rumble.

---

## Signal Flow Diagram

[ Input Signal ]
|
v
[ Mode Switch ]
|
+---> (Standby / Off) ---> [ Soft Clipper ] ---> [ De-Esser Circuit ] ---> (Potentiometer) ---> [ Output ]
|
+---> (Active / On)   ---> [ Active Noise Cancellation (ANC) Engine ] -------------------------> [ Output ]

---

## Next Steps & Development
* **Circuit Design:** Schematics for passive RC filter design for the de-esser circuit tied to the potentiometer.
* **Clipping Stage:** Selecting diode configurations for ultra-transparent dynamic peak clipping.
* **Power Delivery:** Managing active power delivery routing exclusively when the toggle switch engages ANC mode.