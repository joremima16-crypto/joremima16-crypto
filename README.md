# Mark Joseph

**Embedded Systems & Edge ML** · Patent Co-Inventor (Adaptive IoT Comms) · Bare-Metal ARM & FreeRTOS · Final-year B.Tech (E&I), MIT Manipal '27

[mrkjosp@gmail.com](mailto:mrkjosp@gmail.com) · [LinkedIn](https://www.linkedin.com/in/mark-joseph-5ba355319) <!-- confirm this is the current LinkedIn URL --> · Manipal, Karnataka, India

---

## About

I build embedded systems that make real-time decisions under real-world constraints — interrupt-driven firmware, resource-constrained ML inference, and communication protocols that adapt when conditions change.

- Completed a research internship at **IIT (BHU) Varanasi**, working on edge computing and federated learning for UAV-assisted systems
- Co-inventor on **Indian Patent Application No. 202641010901** (published April 2026, pending examination) — an ML-driven adaptive LoRa/BLE protocol-switching system for IoT, filed by Manipal Academy of Higher Education
- Comfortable writing register-level firmware with no HAL/framework, designing RTOS-based pipelines, and integrating ML inference on constrained hardware
- Graduating 2027 — looking for full-time Embedded / Firmware Engineer roles

---

## Tech Stack

- **Languages:** C, C++, Embedded C, Python, Shell/Bash
- **Embedded / Firmware:** Bare-metal & register-level programming, memory-mapped I/O, interrupt handling (ISR), NVIC, linker scripts, fixed-point (Q15), FreeRTOS (tasks, queues, semaphores)
- **Protocols:** UART, SPI, I2C, GPIO, CAN 2.0B, MQTT
- **ML / Edge:** scikit-learn (Random Forest, probability calibration), TinyML, TensorFlow Lite, model quantization
- **Tools:** arm-none-eabi-gcc, Make, QEMU, Git, NumPy, Pandas, PyTorch

---

## Featured Projects

### ML-Based Adaptive Communication System
*Patent Application No. 202641010901 — co-inventor*

An ESP32-based two-tier on-device decision system for real-time LoRa/BLE protocol selection.

- Platt-scaled Random Forest classifier on live link metrics (RSSI, SNR, battery level, neighbour density), with a deterministic fallback for low-confidence or oscillatory ("flapping") predictions
- Accuracy measured honestly under realistic conditions: 91.6% on clean synthetic data → 68.7% with injected sensor noise and multipath fading; derived a calibrated confidence threshold (α = 0.65) for protocol switching
- Simulated a ~22% reduction in transmit energy and airtime relative to an all-LoRa baseline, using datasheet-derived radio parameters

*(Not a standalone repository — full specification publicly viewable on the [India Patent Office's InPASS portal](https://iprsearch.ipindia.gov.in/PublicSearch/PublicationSearch/ApplicationStatus): search Application No. 202641010901.)* <!-- once you've pulled the published spec PDF from the portal, consider hosting it directly in this repo and linking that instead — the portal search itself isn't a stable deep link -->

### [Bare-Metal STM32F405 Peripheral Drivers](https://github.com/mrkjosp/stm32-baremetal-drivers)

GPIO, UART, SPI, and I2C drivers for the STM32F405 (ARM Cortex-M4), written directly from the ST reference manual (RM0090) — no HAL, no CubeMX.

- Interrupt-driven UART RX through a lock-free single-producer/single-consumer ring buffer; zero-drop communication verified end-to-end in QEMU
- Direct register access, custom RCC clock configuration, hand-written linker script and startup code (vector table, `.data` init, `.bss` zeroing)
- SPI and I2C transaction sequences — including I2C repeated-start reads — validated against the reference manual

<!-- optional: embed a terminal-recording GIF here of the QEMU UART echo test (ISR -> ring buffer -> main loop). Tools: vhs (charmbracelet) or asciinema + agg. Real evidence > decorative animation. -->


### [Embedded Fault Detection System with SCADA Monitoring](https://github.com/mrkjosp/scada-fault_detection)

A three-task FreeRTOS pipeline on ESP32 for industrial machine-health monitoring.

- ISR-triggered data acquisition into a circular buffer, followed by Q15 fixed-point DSP processing (accurate to ≤0.0001% vs. a float reference)
- Five-layer deterministic fault detection framework (range checking, rate-of-change, frozen-value detection, cross-sensor voting) integrated with a Random Forest classifier — 90.8% accuracy / 0.90 macro-F1 on the CWRU bearing dataset
- CRC32-protected MQTT telemetry, a Flask REST API for inference, and a live SCADA HMI for real-time visualization

---

## Experience

**Research Intern — Indian Institute of Technology (BHU), Varanasi** (Dec 2025 – Jan 2026)
UAV-based edge computing prototype under a Federated Learning framework. Profiled and optimized a CNN inference pipeline on a Raspberry Pi 4, reducing peak memory footprint to ≤512 MB via INT8 quantization. Designed a Python-based greedy matching algorithm for constrained assignment problems across distributed compute nodes.

---

## Patents & Publications

**Patent (pending):** Indian Patent Office Application No. 202641010901 — "Machine Learning-Driven Hybrid Mesh Switching Communication System for an IoT Device and Method Thereof," co-inventor; filed by Manipal Academy of Higher Education; published April 2026, pending examination.

**Paper:** *ML-Driven Hybrid Mesh Switching for Coverage-Aware IoT Applications* <!-- add venue / status once finalized -->

---

## Education

**B.Tech, Electronics & Instrumentation Engineering** — Manipal Institute of Technology, MAHE (2023 – 2027)

---

Open to full-time embedded/firmware roles from 2027 — reach out at [mrkjosp@gmail.com](mailto:mrkjosp@gmail.com).
