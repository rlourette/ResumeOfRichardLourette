<style>
@page { size: letter portrait; }
</style>
# RICHARD LOURETTE
**Principal Embedded Software Engineer | Consulting CTO**

📧 rlourette@gmail.com | 📱 1.585.953.5309 | 📍 Rochester/Oswego, New York  
🔗 Available for Full-Time Remote or Hybrid Roles

## PROFESSIONAL SUMMARY

Principal Embedded Software Engineer and Consulting CTO with 30+ years of experience architecting, developing, and optimizing embedded software for systems that demand absolute reliability, deterministic real-time performance, and fault tolerance across aerospace, defense, industrial IoT, automotive, and consumer electronics. Founder of RL Tech Solutions LLC, delivering advanced embedded systems architecture and consulting services to Fortune 500 clients and high-tech innovators.

Expert in **C/C++ development**, **embedded Linux**, **RTOS**, and **bare-metal programming**, with proven leadership in technical architecture, team mentorship, and cross-disciplinary collaboration. Most recently led PTP/gPTP (IEEE 802.1AS) Grandmaster development at Point One Navigation, spanning STM32L4 MCU firmware, iMX8 embedded Linux host software, and PHC synchronization infrastructure, while driving a major re-architecture of the platform's services layer to improve modularity, testability, and firmware/host independence.

Recognized innovator with **20+ issued patents** in embedded systems and image processing. Trusted for designing and deploying ultra-reliable, fail-operational systems that perform flawlessly in the most demanding and regulated environments where failure is not an option. Excel at hardware-software co-design, leading rigorous technical reviews, and championing modern CI/CD pipelines, static analysis, and high-assurance development practices.

**Core Competencies:** Embedded Systems Architecture · C/C++ · Python · C# · Real-Time Systems · Embedded Linux · RTOS · PTP/gPTP & Precision Timing · GNSS Integration · Hardware-Software Integration & Co-Design · Services Architecture · Performance Optimization · Fault-Tolerant Design · Technical Leadership · Consulting

## TECHNICAL EXPERTISE

**Programming Languages:** C/C++ (30+ years), Python, C#, Java, Assembly Language, Shell Scripting, HTML/CSS, Forth

**Processor & SoC Architectures:**
- ARM Cortex-A/M/R (including A53/A72 in Zynq UltraScale+ and Versal ACAP)
- STM32L4 (Cortex-M4), iMX8
- NVIDIA Carmel ARM v8.2 64-bit CPU
- Zynq UltraScale+, Versal ACAP
- TI ARM/DSP families
- Radiation-hardened MCUs
- 8/16/32-bit microcontrollers

**Operating Systems & Runtimes:** Embedded Linux, BalenaOS, FreeRTOS, RTEMs, Nucleus/Nucleus++, Bare Metal

**Communications & Timing Protocols:** IEEE 802.1AS (gPTP), IEEE 1588 (PTP), SpaceWire, SpaceFibre, CAN/CAN-FD, I²C, SPI, UART, Ethernet, TCP/UDP, RESTful APIs

**Testing Frameworks & Practices:** Google Test, Unity, Pytest, Hardware-in-the-Loop (HIL) Testing, automated white-box testing, code coverage, regression suites, CI/CD-integrated test pipelines

**Tools & Workflows:** GCC, GDB, JTAG, Git, CI/CD (Jenkins, GitLab CI), Docker (custom base images, cross-compilation in containers, CI pipeline integration, BalenaOS service deployment), Bazel, linuxptp/ptp4l, Wireshark/tshark, AF_NETLINK, perf, Valgrind, static analysis

**Hardware Integration & Specialties:** FPGA/SoC co-design, PCB collaboration, PHC synchronization, 1PPS timing, containerized embedded service deployment via Docker and BalenaOS, real-time image/signal processing, sensor fusion, power optimization

**Methodologies:** Agile/Scrum, Test-Driven Development (TDD), code reviews, requirements analysis, system architecture, high-assurance practices

**Key Domains:** Spacecraft flight software · GNSS receivers · PTP/gPTP timing systems · Real-time 3D imaging · Biometric wearables · Industrial IoT · Airborne surveillance · High-reliability & fail-operational systems

## PROFESSIONAL EXPERIENCE

### POINT ONE NAVIGATION | Staff Embedded Firmware Engineer
**January 2026 – Present | Remote**

- Led PTP/gPTP (IEEE 802.1AS) Grandmaster support on the Atlas GPS/PTP timing platform, working across both STM32L4 MCU firmware (FreeRTOS C++) and embedded Linux host software (C++/Python, BalenaOS)
- Implemented GNSS-disciplined PTP Hardware Clock (PHC) synchronization on the iMX8 Linux host, including 1PPS GPIO timestamping on the STM32 MCU, AF_NETLINK-based PHC watchdog recovery from link-bounce resets, and IEEE 802.1AS gPTP profile configuration via REST API
- Driving a major re-architecture of the Atlas Services layer, transitioning Septentrio GNSS receiver initialization from MCU to host and introducing asynchronous command/response processing with a shared I/O worker model — improving modularity, testability, and the ability to evolve host and firmware independently
- Refactored Septentrio GNSS receiver initialization with a robust six-phase sequence covering baud-rate auto-detection, RTCM escape handling, SBF stream configuration, and non-volatile config save
- Built a PTP test bench using the Dart platform to calibrate and validate the Grandmaster design; developed custom validation tools alongside tshark/Wireshark to verify protocol correctness and timing accuracy on the wire
- Contributed upstream BalenaOS pull requests for device tree customization to support Atlas hardware requirements
- Established Linux cross-build infrastructure for the STM32 firmware and maintained Google Test-based CI test suites, enabling reliable automated validation across firmware and host software changes

### RL TECH SOLUTIONS LLC | President & Chief Technology Officer
**October 2022 – Present | Rochester, NY**

**Client Engagements:**

**D3/L3Harris Aerospace – Chief Engineer Consultant**  
*Oct 2022 – Dec 2023; Oct 2024 – Present*
- Designed spacecraft payload systems integrating 5 radiation-hardened MCUs via SpaceWire communication
- Architected embedded software using NASA Core Flight System (cFS) on RTEMS RTOS
- Implemented microservices architecture to enhance reliability, maintainability, and modularity of flight software
- Led technical design reviews and mentored engineers on embedded systems and space-qualified software practices
- Authored and presented gate review, contributing to award of eight-figure payload contract
- Returned post-sabbatical to develop embedded software architecture for advanced real-time time-of-flight 3D imaging system

**Topcon Positioning Systems – Senior Embedded Software Consultant**  
*Oct 2023 – Apr 2025*
- Architected and implemented Linux C++ subsystems for next-generation GNSS receivers on embedded ARM A9 TI processors
- Built high-performance multi-threaded applications optimized for battery-powered, resource-constrained devices
- Delivered 150,000+ lines of production C++ code with full test coverage using Python, pytest, and Google Test
- Designed advanced white box testing strategies with systematic source analysis for comprehensive test plan generation
- Improved system performance by 40% through CPU profiling with perf and flame graph analysis
- Developed custom loopback filesystem and Python curses monitoring tools for real-time CPU/thread utilization debugging
- Utilized modern Git workflows and CI/CD pipelines aligned with industry best practices to ensure high-quality, reliable software delivery

**Professional Sabbatical**  
*May 2025 – Sep 2025*
- Focused on renewal and independent research, returning with published articles and refreshed technical perspective

### PANASONIC INDUSTRIAL IOT DIVISION | Engineering Group Manager
**Feb 2021 – Oct 2022 | Rochester, NY**
- Managed cross-functional engineering teams spanning RF Engineering, protocol design, antenna development, mesh networking, and embedded firmware
- Directed development of industrial IoT devices with integrated RESTful interfaces for enterprise system integration
- Resolved critical RF communication protocol issues for 2000+ device customer deployment during COVID-19 constraints
- Transformed testing processes from manual to fully automated, reducing test cycle time from weeks to 3 days
- Led technology roadmap development for next-generation industrial IoT product portfolio

### TOKENIZE INC. | Vice President of Engineering
**Sep 2015 – Feb 2021 | Rochester, NY**
- Spearheaded R&D for biometric wearable devices incorporating NFC technology and capacitive fingerprint scanning
- Designed ultra-low-power embedded electronics meeting strict battery life requirements for wearable applications
- Developed real-time signal processing algorithms and visualization tools for capacitive sensing systems
- Collaborated with hardware teams on power optimization strategies for resource-constrained wearable devices

### L3HARRIS GEOSPATIAL SYSTEMS | Chief Scientist/Principal Investigator
**May 2002 – Sep 2015 | Rochester, NY**
- Developed advanced in-situ telescope wavefront correction algorithms using Python for space-based optical systems
- Served as lead architect for GPS-III satellite program test equipment, defining system requirements and FPGA-based hardware architecture
- Designed onboard payload processing electronics for Wide Area Airborne Surveillance (WAAS) systems
- Led development of 7-slot high-altitude VPX supercomputing cluster for Advanced Geospatial Processing applications
- Architected electronic payload systems for visual and infrared sensor platforms

### EASTMAN KODAK COMPANY | Chief Firmware Architect
**1995 – 2002 | Rochester, NY**
- Led international firmware development teams for hybrid consumer digital camera products
- Integrated emerging sensor technologies and wireless capabilities (Bluetooth) into embedded camera systems
- Designed application frameworks and device drivers for memory-constrained embedded systems
- Co-architected USB device drivers and PIMA 15740 application layer protocol implementation
- Developed real-time image processing algorithms for laser printer marking systems
- Created calibration algorithms for non-linear laser marking engine components

## KEY ACHIEVEMENTS

- **Patent Portfolio:** 20+ issued US patents plus international patents in embedded systems and image/signal processing
- **Performance Optimization:** Achieved 40% gains via systematic profiling and refactoring
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
- **Consulting Expertise:** Proven track record as technical consultant for Fortune 500 companies
- **Industry Recognition:** Subject matter expert in embedded systems with 30+ years of deep technical expertise
- **Continuous Learning:** Active in embedded systems community and emerging technology adoption
