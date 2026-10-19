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

I create new products. I take an ambiguous problem, analyze it down to what really constrains it, and synthesize a design I can prove on hardware, quickly. That is how I have worked for more than 30 years, from digital cameras at Kodak to biometric wearables, industrial IoT and GNSS navigation, and it is the work I want to do at Samsara.

My most recent example was a five-day hackathon. Provisioning our navigation boards meant a PC, a vendor Windows tool and a technician holding a reset button at every station. I made the board install itself instead: one 3.2 MB flash write, then power on and walk away while it stages its application, reprograms its GNSS chip, verifies every partition and reboots into normal operation. I reimplemented the vendor's programming protocol to run on the board in about 46 KB, against the 6.15 MB tool it replaced. Five days was enough because the boot chain and update path I had already built for the platform were designed to be extended this way. It ran end to end on real hardware, and all of it is now in the production codebase.

The analysis comes first. Most recently I directed parallel AI investigations into fitting a navigation engine's 64-bit floating-point math onto a Cortex-M55 that runs double precision at about 40 cycles per multiply-add. I held every finding to whether it was measured on the board, simulated or modeled, and synthesized a staged plan for which filters can safely move to single precision.

I have done the same across product lifecycles. At Tokenize I restored blocked production of a biometric hardware wallet by correcting its manufacturing issues and redesigning its antenna, then developed the Token Ring biometric wearable with MCUboot A/B updates, FIPS-certified secure elements and my own 6.78 MHz wireless charging. At Panasonic I measured primary-cell BLE tags with a Joulescope against a five-year battery target, and found the root cause of RF failures across a 2,000-device deployment from its logs. I hold more than 20 US patents.

Embedded systems have been my passion throughout, and I enjoy passing that on. I have mentored engineers across my career, from the more than a dozen I managed across firmware, RF, QA and hardware to the engineers who now learn the platform from my design documents and reviews. I use AI every day as a multiplier, backed by tests and measurement rather than trust.

I fell in love with this job description. Shaping the hardware, being the first to make a new board do anything at all, chasing every microamp, and owning the layers that decide whether a device in the field recovers on its own: that is the work I have been doing, and the work I want to keep doing. Samsara's devices keep fleets and industrial sites running, and each one starts as someone's new product. I would welcome the chance to talk about how I can help create the next ones.

Sincerely,

Richard Lourette
