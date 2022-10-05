---
layout: default
title: 0x001 - Fuzzing
parent: Labs
nav_order: 2
has_children: false
has_toc: true
permalink: /labs/0x001-fuzzing
---

# 0x001 - Fuzzing

**Due at 11:59pm on TBD**

In this lab, you'll run static and dynamic analysis tools on your decoder from assignment 0x000 to find potential bugs and vulnerabilities.

## Setup

This lab involves setting up a cloud development environment in Azure.
Locally, all you'll need is Visual Studio Code and an SSH client.

### Create a virtual machine

The first step is to create a virtual machine in Azure.

### Setup development environment

Once your VM is running and accessible over SSH, you can run the setup script (available [here](https://gist.githubusercontent.com/thomasgt/5e958016d49085b6532df25fffdb4c4d/raw/f514f760340ef692e6cc4c97192d91854a6fa6b5/install-lab-0x001.sh)).

Before running any script you find on the internet, it is a good idea to manually inspect it to make sure it isn't doing anything nefarious. Here it is:
<script src="https://gist.github.com/thomasgt/5e958016d49085b6532df25fffdb4c4d.js"></script>

From the SSH shell for your virtual machine, run the following command:
```
$ curl https://gist.githubusercontent.com/thomasgt/5e958016d49085b6532df25fffdb4c4d/raw/f514f760340ef692e6cc4c97192d91854a6fa6b5/install-lab-0x001.sh | bash
```