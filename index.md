---
layout: default
title: Home
nav_order: 0
description: "Course notes for ECED 4406 - Computer Security"
permalink: /
---

# ECED 4406 - Computer Security

This site contains the course notes for Dalhousie University's ECED 4406 - Computer Security course.

## Course Description

Design of secure embedded systems is critical for deploying and connected technology today.
This class covers methods used to secure computer systems in general, and then applies them to embedded systems.
Many attacks specific to embedded systems are covered, and students will be performing their own tests and development of attacks.
Attacks specific to embedded systems including invasive and non-invasive attacks will be covered in detail, both theoretically and in labs.

## Learning Outcomes

The course's learning outcomes can be organized into four core areas:
- Cryptography
- Software and firmware security
- Hardware security
- Reverse engineering

### Cryptography

Topics covered in this area will include:
- History and applications of cryptography
- Basic ciphers
- Symmetric encryption
- Asymmetric encryption

Labs and assignments in this area will expose students to:
- Python (for analyzing and visualizing data)
- Command line utilities
- Cryptographic libraries

### Software & Firmware Security

Topics covered in this area will include:
- Testing
- Memory safety
- Undefined behaviour
- Fuzzing

Labs and assignments in this area will expose students to:
- Testing frameworks (Catch2)
- Compilers (GCC & Clang)
- Buildsystems (CMake, Make, Ninja)
- Sanitizers (address, thread, undefined behaviour)
- Fuzzers (libfuzzer)

### Hardware Security

Topics covered in this area will include:
- Non-invasive and semi-invasive attacks
  - Side-channel
  - Power analysis
  - ROM readout
  - Voltage glitching

Labs and assignments in this area will expose students to:
- ARM microcontrollers (Raspberry Pi Pico)
- Side-channel capture tools (ChipWhisper Nano)
- Debuggers (OpenOCD and GDB)
- Python

### Reverse Engineering

Topics covered in this area will include:
- ARM assembly
- Function calls and stack frames
- Decoding binary formats

Labs and assignments in this area will expose students to:
- Compiler explorer (godbolt)
- Command line utilities
  - objdump
  - readelf
  - strings
- Ghidra
