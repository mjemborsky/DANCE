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

## Phase 1: DSP Core & Digital Filtering (Week 1)
* [ ] **Teensy Audio Library Setup:** Configure Teensyduino / PlatformIO environment for Teensy 4.x + Audio Shield.
* [ ] **De-Esser Logic:** Implement sidechain high-pass filter feeding a band-passed dynamic threshold attenuator (~5kHz–8kHz).
* [ ] **Dynamic Peak Clipper:** Write a low-latency soft/hard clipping function with configurable knee curves.
* [ ] **Benchmarking:** Measure DSP cycle counts and audio pass-through latency in microsecond buffers.

## Phase 2: Active Noise Cancellation Prototype (Week 2)
* [ ] **Dual-Microphone Input Pipeline:** Configure reference (ambient) and error (internal) mic input streams on the audio shield.
* [ ] **Phase Inversion & LMS Filter:** Implement a normalized Least Mean Squares (NLMS) adaptive filter algorithm for active noise cancellation.
* [ ] **Frequency Response Calibration:** Map phase shifts and group delays to avoid unwanted constructive interference at higher frequencies.

## Phase 3: Mode Switching & Control Interface (Week 3)
* [ ] **State Machine Architecture:** Build smooth crossfade state logic between Standby (Clipper/De-Esser) and Active (ANC) modes to prevent audio pops/clicks.
* [ ] **Hardware I/O Mapping:** Wire up rotary encoders and toggle switches for threshold/gain adjustments and mode toggling.
* [ ] **OLED / LED Status Feedback:** Add lightweight visual feedback for current operational mode and gain reduction metering.

## Phase 4: Calibration, Enclosure Prep & Tuning (Week 4)
* [ ] **Acoustic Calibration:** Fine-tune adaptive filter convergence speeds against real ambient noise profiles.
* [ ] **Clipping & Sibilance Pass-Through Tests:** Profile audio quality across various mic and line-level sources.
* [ ] **Hardware Enclosure Wiring Prep:** Document final pinouts, pot values, and power requirements for final PCB/enclosure assembly.