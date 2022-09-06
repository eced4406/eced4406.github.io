---
layout: default
title: Home
nav_order: 0
description: "Course notes for ECED 4406 - Computer Security"
permalink: /
---

# ECED 4406 - Computer Security

This is the course website for Dalhousie's ECED 4406 - Computer Security (Fall 2022).

## Course Description

Design of secure embedded systems is critical for deploying and connected technology today.
This class covers methods used to secure computer systems in general, and then applies them to embedded systems.
Many attacks specific to embedded systems are covered, and students will be performing their own tests and development of attacks.
Attacks specific to embedded systems including invasive and non-invasive attacks will be covered in detail, both theoretically and in labs.

## Assessments

The course is designed with an emphasis on hands-on labs.
Lab reports, assignments, learning journals, and materials related to your final project must be submitted via Brightspace.
Submission templates will be provided.
Bi-weekly quizzes and the final exam will be in-person.

### Grading

The table below shows the weights for each evaluation type.

| Evaluation | Weight |
| --- | --- |
| Quizzes | 15% |
| Assignments | 15% |
| Labs | 20% |
| Learning Journals | 10% |
| Project | 15% |
| Final Exam | 25% |

### Quizzes

Bi-weekly quizzes (closed-book) will be completed during the last ~20 minutes of lecture on the day they are scheduled.
Your worst quiz mark will be dropped.
More information can be found [here]({% link quizzes/README.md %}).

### Assignments

There will be three assignments over the term.
Some assignments are closely related to labs, whereas other assignments are to reinforce topics covered in lectures.
Assignments must be completed individually and submitted via Brightspace.

### Labs

Labs will be completed in groups of three.
One grade will be assigned per-submission (i.e. partners get the same mark).
Lab reports must be submitted via Brightspace.

### Learning Journals

Students must complete a bi-weekly learning journal.
The journal entries are an opportunity to reflect on aspects of computer security that you've recently learned about - in or out of classroom.
Make connections between topics covered in this course and the broader world.
Talk about a tool that you think is interesting or useful.
Describe what stands out to you in a podcast you've listened to or or blog post that you've read.
These aren't meant to be long; two or three paragraphs is fine. 

### Project

There will be a group project due at the end of the term.
You will work in groups to analyze and demonstrate a real-world computer security attack.
You will primarily be evaluated on a presentation that you will deliver to the rest of the class and a report that you will submit.

### Final Exam

Your final evaluation will be a written exam.
It will take place during the standard exam period.
It will be open-book, although I recommend consolidating your notes into a cheatsheet.

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
