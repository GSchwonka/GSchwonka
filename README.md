<h1 align="center">Guilherme Schwonka</h1>

<p align="center">
  <strong>Firmware Engineer</strong> · Embedded Systems · Real-Time Firmware · IoT Connectivity
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/gschwonka/"><img src="https://img.shields.io/badge/LinkedIn-gschwonka-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:guischwonka@gmail.com"><img src="https://img.shields.io/badge/Email-guischwonka%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://img.shields.io/badge/Based%20in-Curitiba%2C%20Brazil-2E7D32?style=flat-square" alt="Location">
  <img src="https://img.shields.io/badge/Languages-English%20%7C%20Portuguese-555555?style=flat-square" alt="Languages">
</p>

---

## About Me

I'm a firmware engineer with 3+ years of experience building embedded software for microcontrollers, from
low-level peripheral drivers and RTOS task design to device connectivity, OTA updates, and the gateway and cloud
services around them. I work mostly in **C and C++** on **ESP32** and **STM32** platforms with **FreeRTOS** and
**Zephyr**, and I focus on firmware that is deterministic, memory-efficient, and reliable across a whole device fleet.

I like the hard debugging problems: decoding panic backtraces, tracking down interrupt-latency stalls, recovering
heap on constrained parts, and measuring where the milliseconds go across the full path from browser to MCU.

- 🔧 **Currently:** Firmware Engineer at **Shaw and Partners**, building real-time LED firmware on ESP32
- 🎓 **Education:** B.Eng. Electronic Engineering (UTFPR). Now studying for a B.Eng. in Computer Engineering (Cruzeiro do Sul)
- 🌎 **Remote experience** with US-based engineering teams (Wyoming and California)

---

## Technical Skills

**Languages**

![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)

**Microcontrollers & Hardware**

![Espressif](https://img.shields.io/badge/ESP32%20(C6%20%7C%20S3%20%7C%20P4)-E7352C?style=for-the-badge&logo=espressif&logoColor=white)
![STM32](https://img.shields.io/badge/STM32-03234B?style=for-the-badge&logo=stmicroelectronics&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-A22846?style=for-the-badge&logo=raspberrypi&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00878F?style=for-the-badge&logo=arduino&logoColor=white)

**RTOS, Tooling & Platforms**

![FreeRTOS](https://img.shields.io/badge/FreeRTOS-5A9B3C?style=for-the-badge)
![Zephyr](https://img.shields.io/badge/Zephyr%20RTOS-7929D2?style=for-the-badge&logo=zephyrproject&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)

| Area | Technologies |
| --- | --- |
| **Protocols & Buses** | UART · SPI · I2C · I3C · Parallel · TCP · WebSockets · MQTT · Wi-Fi · Ethernet |
| **Firmware** | HAL and low-level drivers · ISRs · RTOS multitasking and IPC · ring buffers · memory optimization |
| **Boot & Deployment** | OTA updates · MCUboot · STM32CubeProgrammer · boot sequences |
| **Data & Integrity** | Custom binary protocols · CRC16-CCITT · LZ4 compression · LittleFS |
| **Debugging** | Panic backtrace decoding · interrupt-latency analysis · end-to-end latency instrumentation |

---

## Professional Experience

### Firmware Engineer · Shaw and Partners
*Casper, WY, USA (remote) · 05/2026 – Present*

- **Real-time LED firmware:** C++/FreeRTOS firmware on ESP32 driving **11 addressable WS2812/SK6812 strips (1,881 pixels)** per board, streaming LZ4-compressed frames at **20–60 FPS** over TCP through a bounded, self-recycling frame queue.
- **Stability:** Fixed a production crash (a reboot every ~11 min) by decoding ESP32 panic backtraces. Reclaimed **15.7 KB of heap** on a PSRAM-less ESP32-WROOM-32, taking frame-allocation failures from **173+ to zero**.
- **Interrupt latency:** Traced LED corruption to ISR stalls. Added a stream-idle gate and a UART TX ring buffer, cutting logging overhead **30× (53 ms → 1.7 ms)**.
- **Binary protocol:** Fixed a decoder bug in a CRC16-CCITT length-prefixed TCP protocol that was silently dropping **~90%** of ACK and flow-control messages. This restored back-pressure across the fleet.
- **Gateway and cloud:** Built a Go rendering service on Raspberry Pi and fixed concurrency and state bugs in a NestJS/TypeScript API on AWS.
- **Latency analysis:** Measured the full browser → cloud → MQTT → gateway → MCU path and identified an AWS region migration worth **~120 ms**, about 5× the gain from any code optimization.

### Firmware Engineer · Binho LLC
*San Francisco, CA, USA (remote) · 08/2025 – 03/2026*

- Firmware in C/C++ for **ESP32 (C6, S3, P4)** and **STM32N6**: low-level drivers, peripheral configuration, and HALs.
- Real-time applications on **FreeRTOS** and **Zephyr RTOS**, including task scheduling and inter-task communication design.
- Implemented and debugged **SPI, I2C, I3C, and UART** interfaces to external peripherals and sensors.
- Worked on boot and deployment workflows: **MCUboot** integration, STM32CubeProgrammer flashing, and MCU boot sequences.
- Contributed to an internal serial communication tool for device commands, logging, and firmware validation.

### Firmware Engineer · Shaw and Partners
*Casper, WY, USA (remote) · 06/2024 – 08/2025*

- Designed and implemented **OTA firmware updates** and real-time command delivery over **MQTT**.
- Built Wi-Fi and Ethernet network management for ESP32, plus an asynchronous on-device web server.
- Built a Raspberry Pi local server that talks to the ESP32 over **WebSockets** for low-latency control.
- **Led a multidisciplinary team** that built a web platform where clients send commands and monitor devices.

### Firmware Engineer · Blue Circuits
*Curitiba, PR, Brazil · 06/2023 – 06/2024*

- Embedded software focused on buffer handling for efficient data processing.
- Implemented and optimized UART, I2C, SPI, and parallel communication protocols.
- Programmed and tested Arduino and ESP32 microcontrollers from datasheet specifications.

---

## Education

| Degree | Institution | Period |
| --- | --- | --- |
| **B.Eng., Computer Engineering** | Universidade Cruzeiro do Sul | 04/2026 – Present |
| **B.Eng., Electronic Engineering** | Universidade Tecnológica Federal do Paraná (UTFPR) | 08/2021 – 08/2025 |

---

## GitHub Stats

<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=GSchwonka&show_icons=true&hide_border=true&theme=transparent" alt="GitHub stats">
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=GSchwonka&layout=compact&hide_border=true&theme=transparent" alt="Top languages">
</p>

---

<p align="center">
  <em>Open to firmware and embedded systems opportunities. Feel free to reach out.</em>
</p>
