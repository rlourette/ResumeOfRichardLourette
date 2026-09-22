# RICHARD LOURETTE
**Principal Embedded Software Engineer**

rlourette@gmail.com | 1.585.953.5309 | Rochester/Oswego, New York | Available for Remote Work

## PROFESSIONAL SUMMARY

Principal Embedded Software Engineer with 30+ years delivering embedded software for spacecraft payloads, satellite ground test equipment, airborne surveillance, and precision GNSS and timing products. Experience spans concept and trade studies through detailed design, hardware integration, test, and anomaly resolution on real hardware. Flight software work includes NASA Core Flight System (cFS) on RTEMS across five radiation-hardened MCUs communicating over SpaceWire, and lead architect for GPS-III satellite program test equipment. Most recently, at Point One Navigation, architected the multi-stage boot chain and serial firmware-update path for a Cortex-M55 GNSS/inertial platform and owned the hardware-in-the-loop test infrastructure, device emulation, and on-target profiling behind it. Expert in C/C++, FreeRTOS and RTEMS, embedded Linux, and bare-metal development.

**Core Competencies:** Flight Software (NASA cFS, RTEMS) · Embedded Systems Architecture · C/C++ · Python · Real-Time Systems · FreeRTOS · Embedded Linux · Bootloaders & Firmware Update · Device Drivers & Hardware Interfaces · GNSS/INS Navigation · PTP/gPTP Precision Timing · Hardware-in-the-Loop Test Automation · Device Emulators & Simulation · On-Target Profiling & Optimization · Anomaly Resolution · Technical Leadership

## TECHNICAL EXPERTISE

**Languages:** C/C++ (30+ years), Python, C#, Java, Assembly, Shell, Forth

**Embedded Platforms:** ARM Cortex-A/M/R — STM32N6 (Cortex-M55, Helium/MVE), STM32L4, i.MX 8, TI ARM A9 — radiation-hardened MCUs, DSPs, Zynq UltraScale+, Versal ACAP, 8/16/32-bit microcontrollers

**Operating Systems & Runtimes:** RTEMS, FreeRTOS, Nucleus/Nucleus++, bare metal, embedded Linux, BalenaOS, NASA cFS, on-target MicroPython and Forth interpreters

**Interfaces & Protocols:** SpaceWire, SpaceFibre, IEEE 802.1AS (gPTP), IEEE 1588 (PTP), CAN/CAN-FD, I²C, SPI, UART, XSPI/OSPI, Ethernet, TCP/UDP, RESTful APIs, RTCM, NMEA, custom binary command/telemetry protocols

**Build, Debug & Profiling:** GCC and LLVM/Clang cross toolchains, CMake, Bazel, GDB, SEGGER J-Link and RTT, JTAG/SWD, ARM PMU counters, perf, flame graphs, Valgrind, linker map and stack-usage analysis, clang-tidy, Git, Jenkins, Docker CI

**Test & Validation:** Hardware-in-the-loop automation, device emulators and recorded-session replay, fault injection and randomized stress, Google Test, Unity, pytest, white-box test design, CI-integrated pipelines

**Hardware Integration:** FPGA/SoC co-design, PCB collaboration, boot ROM and external flash bring-up, memory-map and linker script architecture, MPU and cache coherency, watchdog and reset-domain design, PHC synchronization, 1PPS timing, signal processing, sensor fusion, power optimization

## PROFESSIONAL EXPERIENCE

### POINT ONE NAVIGATION | Staff Embedded Firmware Engineer
**January 2026 – Present | Remote**

*STM32N6 GNSS/Inertial Navigation Platform (Cortex-M55, FreeRTOS)*
- Architected the multi-stage boot chain for a new Cortex-M55 navigation platform: boot-ROM launch of a first-stage bootloader in ST's signed-image format, a second-stage loader that hash-verifies and stages payloads, and execute-in-place start of the application from external octal-SPI flash, with versioned, frozen-layout contracts between stages
- Built the serial firmware-update path that retired a JTAG-and-buttons procedure, carrying compressed, hash-verified scatter-gather image transfers over the unit's existing serial port to update bootloader, application, and GNSS receiver firmware with no debugger access
- Designed the bootloader-loaded maintenance applets — flash programmer, factory reset, GNSS receiver passthrough, an on-device GNSS firmware programmer that removed a vendor host-PC tool from the update path, and MicroPython and Forth REPLs exposing flash, memory, and watchdog primitives so bring-up and anomaly work proceed without a rebuild-and-reflash cycle
- Owned the hardware-in-the-loop test infrastructure: 167 automated pytest cases driving real hardware over J-Link and serial install, a software model of the GNSS receiver used in place of the chip, recorded-drive replay, randomized byte-level stress, and fault injection of corrupted configuration and flash
- Profiled the navigation engine on target with ARM PMU counters and a lightweight instrumentation layer, then cut Doppler-update CPU 45–55% by selecting measurements per satellite rather than per signal, leaving satellite geometry unchanged; established the bit-identical regression check over 61,000 paired epochs that now separates intended algorithm changes from unintended ones
- Root-caused release-blocking anomalies on hardware, each confirmed by reproduction and instrumented proof: a reset that left external flash in octal mode so the boot ROM could not reload the bootloader; a boot loop traced to silent object-pool exhaustion, now guarded by pool-sizing analysis; data-cache coherency faults in RAM-resident code; and an LLVM code-generation defect isolated and worked around at the toolchain level

*Atlas GPS/PTP Timing Platform (STM32L4 + i.MX 8 Linux)*
- Led IEEE 802.1AS (gPTP) Grandmaster support across STM32L4 MCU firmware (FreeRTOS, C++) and embedded Linux host software (C++/Python, BalenaOS), including GNSS-disciplined PTP Hardware Clock synchronization, 1PPS GPIO timestamping, AF_NETLINK-based watchdog recovery from link-bounce resets, and REST-configured gPTP profiles
- Led a re-architecture of the Atlas services layer, moving Septentrio GNSS receiver initialization from MCU to host and introducing asynchronous command/response processing over a shared I/O worker, so host and firmware can evolve independently; rebuilt receiver startup as a six-phase sequence covering baud auto-detection, RTCM escape handling, SBF stream configuration, and non-volatile save
- Built the PTP calibration and validation bench, with custom on-the-wire analysis tools alongside tshark/Wireshark, and established Linux cross-build infrastructure and Google Test CI suites for the STM32 firmware

### RL TECH SOLUTIONS LLC | President & Chief Technology Officer
**October 2022 – Present | Rochester, NY**

**D3/L3Harris Aerospace – Chief Engineer Consultant**  
*Oct 2022 – Dec 2023; Oct 2025 – Dec 2025*
- Designed the payload flight software architecture for a spacecraft payload of five radiation-hardened MCUs communicating over SpaceWire, on NASA Core Flight System (cFS) over RTEMS
- Architected the spacecraft payload processor around Zynq UltraScale+ and Versal ACAP devices
- Decomposed the payload software into independent cFS applications with software-bus interfaces, so subsystems could be developed, tested, and patched separately
- Led technical design reviews and mentored engineers on embedded and space-qualified software practices
- Authored and presented the gate review that contributed to award of an eight-figure payload contract
- Returned post-sabbatical to develop the embedded software architecture for a real-time time-of-flight 3D imaging system

**Topcon Positioning Systems – Senior Embedded Software Consultant**  
*October 2023 – April 2025*
- Architected and implemented multi-threaded Linux C++ subsystems for next-generation GNSS receivers on TI ARM A9 processors, tuned for battery-powered, resource-constrained operation
- Delivered 150,000+ lines of production C++ with full test coverage using Python, pytest, and Google Test, driven by white-box test plans derived from systematic source analysis
- Improved system performance 40% through CPU profiling with perf and flame graph analysis
- Developed a custom loopback filesystem and Python curses tooling for real-time CPU and thread-utilization debugging

**Professional Sabbatical**
*May 2025 – Sep 2025*
- Focused on renewal and independent research, returning with published articles and refreshed technical perspective

### PANASONIC INDUSTRIAL IOT DIVISION | Engineering Group Manager
**February 2021 – October 2022 | Rochester, NY**
- Managed cross-functional teams spanning RF engineering, protocol design, antenna development, mesh networking, and embedded firmware, and led the roadmap for the next-generation industrial IoT portfolio
- Directed development of industrial IoT devices with RESTful interfaces for enterprise integration
- Resolved critical RF protocol failures in a 2000+ device customer deployment under COVID-19 travel constraints
- Replaced manual verification with full automation, cutting the test cycle from weeks to three days

### TOKENIZE INC. | Vice President of Engineering
**September 2015 – February 2021 | Rochester, NY**
- Led R&D for biometric wearable devices combining NFC and capacitive fingerprint sensing
- Designed ultra-low-power embedded electronics to strict wearable battery-life budgets, working with hardware on power optimization
- Developed real-time signal processing algorithms and visualization tools for capacitive sensing

### L3HARRIS GEOSPATIAL SYSTEMS | Chief Scientist/Principal Investigator
**May 2002 – September 2015 | Rochester, NY**
- Developed advanced in-situ telescope wavefront correction algorithms using Python for space-based optical systems
- Served as lead architect for GPS-III satellite program test equipment, defining system requirements and FPGA-based hardware architecture
- Designed onboard payload processing electronics for Wide Area Airborne Surveillance (WAAS) systems
- Led development of 7-slot high-altitude VPX supercomputing cluster for Advanced Geospatial Processing applications
- Architected electronic payload systems for visual and infrared sensor platforms

### EASTMAN KODAK COMPANY | Chief Firmware Architect
**1995 – 2002 | Rochester, NY**
- Led international firmware teams for hybrid consumer digital camera products, integrating emerging sensor and Bluetooth technologies
- Designed application frameworks and device drivers for memory-constrained embedded systems
- Co-architected USB device drivers and the PIMA 15740 application-layer protocol implementation
- Developed real-time image processing and calibration algorithms for non-linear laser marking engines

## KEY ACHIEVEMENTS

- **Patent Portfolio:** 20+ issued US patents plus international patents in embedded systems and image/signal processing
- **Performance Optimization:** Cut Doppler-update CPU 45–55% on a Cortex-M55 navigation engine with satellite geometry unchanged; 40% CPU gain on a Linux GNSS receiver via perf and flame graphs
- **Boot Chain & Firmware Update:** Delivered a multi-stage boot chain and serial update path that retired a JTAG-based procedure
- **Test Automation:** Built a 167-case hardware-in-the-loop suite with GNSS receiver emulation and recorded-drive replay
- **Team Leadership:** Successfully managed and mentored 13+ engineers across multiple disciplines
- **Process Improvement:** Reduced verification cycles from weeks to days through automation implementation
- **High-Reliability Systems:** Delivered fault-tolerant, mission-essential embedded software for aerospace and defense programs
- **Technology Innovation:** Led adoption of emerging technologies in embedded systems across multiple industries
- **Contract Win:** Secured contract totaling $50M+ through technical leadership, customer engagement, and architecture excellence

## EDUCATION

**Bachelor of Science in Electrical Engineering**  
University of Dayton | Dayton, Ohio

## SECURITY CLEARANCES

- Previously held DoD Top Secret Clearance
- Completed Single Scope Background Investigation (SSBI) for Sensitive Compartmented Information (SCI) access
- Available for security clearance reinstatement

## ADDITIONAL QUALIFICATIONS

- **Amateur Radio License:** FCC Amateur Extra Class license holder (AB2MD)
- **Remote Work Experience:** 5+ years of successful remote collaboration and team leadership
- **Consulting Expertise:** Technical consultant to Fortune 500 aerospace, positioning, and industrial clients
