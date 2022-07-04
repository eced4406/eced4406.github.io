---
layout: default
title: 0x101 - Vulnerabilities
parent: 0x100 - Software Security
grand_parent: Lectures
nav_order: 0
has_children: false
has_toc: false
permalink: /lectures/0x100-software-security/0x101-vulnerabilities 
---

# 0x101 - Vulnerabilities

Vulnerabilities are weaknesses that attackers can exploit to cause harm.
OWASP enumerates dozens of vulnerabilities applicable to software.[^1]
There are many interesting categories of software vulnerabilities, but we'll focus on the ones most applicable to embedded systems.

Traditionally, C and/or assembly are the most common programming languages used to develop software for embedded systems. 
These languages give engineers precise control over the systems they are developing.
This level of control comes at a cost.
Engineers are responsible for meeting the functional requirements of their system, but they must also handle errors, manage dynamic memory, cleanup resources, and consider edge cases.
Low level programming languages generally don't assist engineers with these tasks, so they are a common sources of vulnerabilities.

## Error Handling

Frequently, designers and engineers fail to consider all the possible failure conditions and error states that a system can find itself in. It's not surpsising given that there are generally only a few possible "happy" paths and many possible "sad" paths.

```
char input = getc();
switch (input) {
  case 'y':
	  doSomething();
	case 'n':
	  abort();
};
```

## Memory Safety

## Input Parsing

[^1]: [https://owasp.org/www-community/vulnerabilities/](https://owasp.org/www-community/vulnerabilities/)

