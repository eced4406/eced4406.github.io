---
layout: default
title: 0x000 - Binary Decoder
parent: Assignments
nav_order: 1
has_children: false
has_toc: true
permalink: /assignments/0x000-binary-decoder
---

# 0x000 - Binary Decoder

Binary file decoders are historically a great source of computer security vulnerabilities.
Decoders fall into a perfect storm as they:
* are often written in low-level programming languages,
* have to manage many edge cases and failure modes inherent to the format, and
* have to accept untrusted user input.

To experience the challenges of implementing a decoder first hand, you are going to write one!
In this assignment, you'll use C to implement a decoder for the QOI image format.
The goal here isn't to write an absolutely perfect decoder with no bugs or vulnerabilities.
In fact, you'll actually have more fun in Lab 0x001 (zero-indexed) if your decoder has some problems (more on that later).
For this assignment, you'll only be evaluated on:
* Can you open the provided test images? These will be provided shortly.
* Is your code well organized, documented, and readable?

One important learning outcome for this course is getting exposure to modern tools that will help you be productive while writing secure software or firmware.
I've provided a starter project for you to use [here](https://github.com/eced4406/qoi-starter-project).
Please follow the instructions on the project's README to get started.
It is important that you use this starter project as a subsequent lab will build on it.
I also expect you to submit your assignment as a patch against the starter project.
I'll provide instructions on how to use Git to achieve this closer to the assignment due date.

You can find the specification for the QOI image format [here](https://qoiformat.org/qoi-specification.pdf).
You'll of course be able to find implementations of the QOI decoder online.
You won't get much out of this assignment if you just copy one.
If you're stuck, lean on your classmates for ideas, or post a message in our discussion board.
Please submit your own work.
