<style>
body { font-size: 10.5pt; line-height: 1.3; padding: 0; }
h1 { font-size: 1.9em; margin: 0 0 0.15em; padding-bottom: 0.15em; }
h2 { font-size: 1.15em; margin: 0.9em 0 0.35em; padding-bottom: 0.15em; }
h3 { font-size: 1.0em; margin: 0.8em 0 0.15em; }
p { margin: 0.2em 0 0.45em; }
ul { margin: 0.15em 0 0.4em; padding-left: 1.2em; }
li { margin: 0.1em 0; }
</style>
# RICHARD LOURETTE
**Staff Firmware Engineer**

rlourette@gmail.com | 1.585.953.5309 | Rochester/Oswego, New York | Available for Remote Work

## PROFESSIONAL SUMMARY

Staff Firmware Engineer with 30+ years taking connected, resource-constrained devices from first power-on to shipped product: board bring-up, bootloaders, device firmware update and the drivers everything else depends on, most recently on a new Cortex-M55 GNSS/inertial platform at Point One Navigation. Measures power to the microamp, from BLE tags designed for five years on a primary cell to ultra-low-power biometric wearables. Has restored blocked production, fixed field failures across a 2000-device deployment, managed and mentored 13+ engineers across firmware, RF, QA and hardware, and holds 20+ issued US patents.

**Core Competencies:** Board Bring-Up · Bootloaders & Device Firmware Update · Peripheral Drivers · Power Management & Low-Power Design · BLE · FreeRTOS & Bare Metal · C/C++ · Embedded Linux · Hardware-in-the-Loop Test Automation · On-Target Profiling & Optimization · Field & Production Failure Resolution · Root-Cause Analysis · Design Documentation · Technical Leadership & Mentoring

## TECHNICAL EXPERTISE

**Languages & RTOS:** C, C++ (30+ years), Python, C#, Assembly; FreeRTOS (task priorities, mutexes, semaphores, stream and message buffers), bare metal, RTEMS, embedded Linux, BalenaOS

**Platforms:** STM32N6 (Cortex-M55), STM32L4, Nordic BLE SoCs, Ambiq Apollo, i.MX 8, TI ARM A9

**Wireless, Interfaces & Security:** BLE, NFC, Wi-Fi, proprietary mesh, Zigbee, LoRa, radio modems; SPI, I2C, UART, CAN/CAN-FD, ADC, XSPI/OSPI, Ethernet; protocol buffers, MQTT, CoAP, gPTP/PTP; FIPS-certified secure elements

**Bench & Debug:** Joulescope, oscilloscopes, network and spectrum analyzers, logic and protocol analyzers, Wireshark, SEGGER J-Link and RTT, JTAG/SWD, GDB, ARM PMU counters, linker maps

**Build, Test & Cloud:** GCC, LLVM/Clang, CMake, Bazel, Docker, Jenkins, Git, perf, Google Test, Unity, pytest, hardware-in-the-loop, fault injection, AWS S3

## PROFESSIONAL EXPERIENCE

### POINT ONE NAVIGATION | Staff Embedded Firmware Engineer
**January 2026 – Present | Remote**

*STM32N6 GNSS/Inertial Navigation Platform (Cortex-M55, FreeRTOS)*
- Brought up a new Cortex-M55 navigation platform and architected its multi-stage boot chain: boot-ROM launch of a first-stage bootloader built in ST's signed-image format, ready for boot-ROM authentication when a customer requires secure boot; a second-stage loader that hash-verifies and stages payloads; and execute-in-place start of the application from external octal-SPI flash. The stages share versioned, frozen-layout contracts
- Defined the firmware memory map: flash partitioning between the bootloader stages and the application, internal RAM allocation, and the linker-script architecture behind both
- Built the serial firmware-update path that retired a JTAG-and-buttons procedure: compressed, hash-verified scatter-gather transfers over the unit's existing serial port update the bootloader, application and GNSS receiver firmware with no debugger, and bootloader-resident factory-reset and recovery applets bring back a unit an interrupted update would otherwise strand. Weighed A/B image partitions against limited flash and chose the staged first-stage bootloader for robustness, with the MCU's boot ROM as the last-resort fallback. Releases ship as versioned firmware packages published to AWS S3, with a host update tool for customers
- Built the manufacturing load that programs blank boards and their GNSS receiver firmware in two stages, proven on hardware-in-the-loop before handoff
- Designed the bootloader-loaded maintenance applets: flash programmer, factory reset, GNSS receiver passthrough, an on-device GNSS firmware programmer that removed a vendor host-PC tool from the update path, and MicroPython and Forth REPLs exposing flash, memory and watchdog primitives, so bring-up and anomaly work proceed without a rebuild-and-reflash cycle
- Owned the hardware-in-the-loop test infrastructure: 167 automated pytest cases driving real hardware over J-Link and serial, a software model of the GNSS receiver used in place of the chip, recorded-drive replay, randomized byte-level stress, and fault injection of corrupted configuration and flash
- Profiled the navigation engine on target with ARM PMU counters and a lightweight instrumentation layer, then cut Doppler-update CPU 45–55% by selecting measurements per satellite rather than per signal; established the bit-identical regression check over 61,000 paired epochs that separates intended algorithm changes from unintended ones
- Root-caused release-blocking anomalies on hardware, each confirmed by reproduction and instrumented proof: a reset that left external flash in octal mode so the boot ROM could not reload the bootloader; a boot loop traced to silent object-pool exhaustion, now guarded by pool-sizing analysis; data-cache coherency faults in RAM-resident code; and an LLVM code-generation defect isolated and worked around at the toolchain level, each written up as a root-cause analysis the team could act on
- Used AI daily as an engineering multiplier for architecture, design, code review and test frameworks: 1,560+ commits across four repositories in nine months, with a third of the new code in Google Test units and pytest hardware-in-the-loop suites
- Authored the boot-chain and update-path design documents that reviewers and new engineers work from

*Atlas GPS/PTP Timing Platform (STM32L4 + i.MX 8 Linux)*
- Led IEEE 802.1AS (gPTP) Grandmaster support split across STM32L4 MCU firmware (FreeRTOS, C++) and i.MX 8 embedded Linux (C++/Python, BalenaOS): GNSS-disciplined PTP Hardware Clock synchronization, 1PPS GPIO timestamping, AF_NETLINK-based watchdog recovery from link-bounce resets, and a calibration bench with custom on-the-wire analysis
- Re-architected the services layer, moving GNSS receiver initialization from MCU to host with asynchronous command/response so host and firmware evolve independently; contributed upstream BalenaOS device-tree pull requests and built Docker cross-builds and Google Test CI for the STM32 firmware

### RL TECH SOLUTIONS LLC | President & Chief Technology Officer
**October 2022 – Present | Rochester, NY**  
*Independent consulting practice; client engagements ended December 2025 and the practice is closing*

**D3/L3Harris Aerospace – Chief Engineer Consultant**  
*Oct 2022 – Dec 2023; Oct 2025 – Dec 2025*
- Designed the payload flight software architecture for five radiation-hardened MCUs communicating over SpaceWire, on NASA Core Flight System (cFS) over RTEMS, decomposed into independently testable and patchable applications
- Architected the payload processor hardware and software around Zynq UltraScale+ and Versal ACAP devices, selecting the radiation-tolerant devices, and was instrumental in memory selection and partitioning
- Authored and presented the gate review that contributed to award of an eight-figure payload contract, and mentored engineers on embedded and space-qualified software practices

**Topcon Positioning Systems – Senior Embedded Software Consultant**  
*October 2023 – April 2025*
- Architected and implemented multi-threaded Linux C++ subsystems for next-generation GNSS receivers with integrated radio modems, on TI ARM A9 processors, tuned for battery-powered, resource-constrained operation
- Delivered 150,000+ lines of production C++ with test suites targeting 100% coverage in Python, pytest and Google Test, driven by white-box test plans derived from systematic source analysis
- Cut CPU load 40% through profiling with perf and flame graph analysis
- Built real-time CPU and thread-utilization debugging tools, and debugged receiver networking with Wireshark

### PANASONIC INDUSTRIAL IOT DIVISION | Engineering Group Manager
**February 2021 – October 2022 | Rochester, NY**
- Led firmware for primary-cell intelligent tags on Nordic BLE SoCs, designed to a five-year battery-life target; characterized standby and active current with a Joulescope precision energy analyzer to hold standby in the low tens of microamps
- Led architecture of connected IoT gateway products integrating Wi-Fi, BLE and proprietary mesh networking, with protocol buffers structuring device data and RESTful interfaces for enterprise and cloud integration
- Resolved critical RF protocol failures in a 2000+ device customer deployment under COVID-19 travel limits: directed the team to adapt a product into a remote instrument, personally analyzed the logs to find the root cause, and directed the RF protocol refinements that restored communication between legacy and new products
- Replaced manual verification with full automation, cutting the test cycle from weeks to three days
- Managed and mentored engineers across firmware, RF, antenna, protocol, QA and hardware, and led the roadmap for the next-generation industrial IoT portfolio

### TOKENIZE INC. (formerly Case Wallet) | Vice President of Engineering
**September 2015 – February 2021 | Rochester, NY**
- Joined as hands-on VP of Engineering while production of the Case biometric Bitcoin hardware wallet was blocked, and restored it: corrected the manufacturing issues, redesigned the antenna to fix a bad layout, and worked with the firmware team to make the device handle brown-out resets. The wallet combined fingerprint authorization, Qi wireless charging, and a GSM link straight to the company's secure servers, so no phone or PC sat in the path for a man-in-the-middle attack
- Proposed and adopted the open-source MCUboot fail-safe bootloader with A/B image partitions for the Token Ring, so a failed firmware update falls back to the previous image
- Integrated FIPS-certified NXP and STMicroelectronics secure elements into the Token Ring for financial transactions, with fingerprint templates encrypted and held inside the secure element
- Built firmware for the Token Ring biometric wearable on an Ambiq Apollo ultra-low-power MCU, running Ambiq's BLE host stack against an external BLE controller, with NFC, under a strict battery budget
- Designed the Token Ring's 6.78 MHz inductive wireless charging, characterizing it, the RF striplines and the NFC antenna network with network analyzers
- Directed hardware bring-up and validation with oscilloscopes, logic analyzers and spectrum analyzers, working with hardware engineers on power management and sensor interface design
- Developed real-time signal processing algorithms and visualization tools for capacitive fingerprint sensing

### GEOSPATIAL SYSTEMS DIVISION: KODAK, ITT, EXELIS, HARRIS (now L3Harris) | Chief Scientist/Principal Investigator
**May 2002 – September 2015 | Rochester, NY**
- Lead architect for GPS-III satellite program test equipment, from system requirements to FPGA-based hardware architecture; designed airborne surveillance payload processing electronics and a 7-slot high-altitude VPX computing cluster

### EASTMAN KODAK COMPANY | Chief Firmware Architect
**1995 – 2002 | Rochester, NY**
- Led international firmware teams for hybrid digital cameras, integrating new image sensors and Bluetooth on object-oriented frameworks and drivers shared across product lines; co-architected the USB drivers and PIMA 15740 protocol implementation

## SELECTED PUBLICATIONS

Available at github.com/rlourette/ArticlesPapers  
- **Hybrid BLE-Thread Warehouse Asset Tracking System** (2025): multi-year coin-cell tags, microamp power budgets, and detection probability at 100,000-asset scale
- **Ubiquitous Location: Extending GNSS from Outdoor to Indoor and Asset-Level Visibility** (2025)
- Also: *Why I Don't Want the Heap in My Embedded C++* (2025); *Precision Time Protocol: The Unsung Hero of Autonomous Systems* (2026)

## EDUCATION AND LICENSE

**B.S. Electrical Engineering**, University of Dayton, Dayton, Ohio · FCC Amateur Extra Class license (AB2MD)
