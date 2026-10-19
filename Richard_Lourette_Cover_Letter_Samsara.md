<style>
body { font-size: 11pt; line-height: 1.45; padding: 0; }
h1 { font-size: 1.9em; margin: 0 0 0.15em; padding-bottom: 0.15em; }
p { margin: 0.2em 0 0.8em; }
</style>
# RICHARD LOURETTE

rlourette@gmail.com | 1.585.953.5309 | Rochester/Oswego, New York | Available for Remote Work

October 2026

Samsara Hiring Team  
Staff or Senior Firmware Engineer (JR11960)

Dear Samsara Hiring Team,

I create new products, and the one I am proudest of right now is the firmware foundation of Point One Navigation's new STM32N6 GNSS/inertial platform. I brought up its Cortex-M55 board and built its multi-stage boot chain, serial update path and manufacturing load, in C and C++ on FreeRTOS, with a 167-case hardware-in-the-loop suite behind them. The update path recovers a unit that an interrupted update would otherwise strand, and the boot chain is ready for secure boot when a customer requires it.

That foundation paid off in a five-day hackathon. Provisioning each board took a PC, a vendor Windows tool and a technician holding a reset button. I made the board install itself instead: one 3.2 MB flash write, then power on and walk away while it stages its application, reprograms its GNSS chip and verifies every partition. I reimplemented the vendor's programming protocol in about 46 KB of firmware, replacing a 6.15 MB Windows tool. Five days was enough because I had built the boot chain to be extended this way. It ran end to end on real hardware, and all of it is now in the production codebase.

I analyze before I build. Profiling the navigation engine on the board, I cut Doppler-update CPU 45 to 55 percent, and built the bit-identical regression check over 61,000 epochs that tells intended changes from unintended ones. I then used parallel AI investigations to survey moving the engine's 64-bit math to single precision, labeled every finding as measured on the board, simulated or modeled, and turned them into a staged plan.

Earlier products follow the same pattern. At Tokenize I joined as hands-on VP of Engineering while production of a biometric hardware wallet was blocked, and restored it by correcting the manufacturing issues and redesigning the antenna. For the Token Ring wearable I built the firmware, proposed and adopted MCUboot A/B updates so a failed update falls back to the previous image, integrated FIPS 140-validated secure elements, and designed its 6.78 MHz wireless charging. At Panasonic I led firmware for primary-cell BLE tags designed for five years of life, characterized with a Joulescope, led architecture of IoT gateways using protocol buffers, and personally analyzed the logs that revealed the root cause of RF failures across a 2,000-device deployment. I have been awarded more than 20 US patents along the way.

I love this work, and I enjoy teaching it. I have managed and mentored more than a dozen engineers across firmware, RF, QA and hardware, and I write down what I learn in design documents and root-cause write-ups. I use AI every day as a multiplier, backed by tests and measurement: a third of the code I have written this year is Google Test units and hardware-in-the-loop suites.

This posting reads like a description of the work I do best: being the first to make a new board do anything at all, and chasing every microamp. I would welcome the chance to talk about how I can help create Samsara's next devices.

Sincerely,

Richard Lourette
