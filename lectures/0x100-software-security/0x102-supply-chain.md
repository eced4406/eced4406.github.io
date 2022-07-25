---
layout: default
title: 0x102 - Supply Chain
parent: 0x100 - Software Security
grand_parent: Lectures
nav_order: 1
has_children: true
has_toc: true
---

# Supply Chain

Generally, supply chain attacks occur when an adversary infiltrates the processes between producers and consumers.
Traditionally, this has been a problem for hardware devices, but as software systems become more complex, it is increasingly a threat to software security.
NIST provides a succinct definition of software supply chain attacks:
> A software supply chain attack occurs when a cyber threat actor infiltrates a software vendor’s network and employs malicious code to compromise the software before the vendor sends it to their customers.
> The compromised software then compromises the customer’s data or system.
> Newly acquired software may be compromised from the outset, or a compromise may occur through other means like a patch or hotfix.
> In these cases, the compromise still occurs prior to the patch or hotfix entering the customer’s network.
> These types of attacks affect all users of the compromised software and can have widespread consequences for government, critical infrastructure, and private sector software customers. [^1]

## Common Attack Techniques
Every attack is unique, but they can be broadly grouped into three categories:
- Hijacking updates
- Undermining code signing
- Compromising open-source code

### Hijacking Updates

Software is significantly easier to update than hardware.
Businesses take advantage of this; it allows them to "move fast and break things" [^2].
Updates can also provide patches for critical vulnerabilities discovered in the software.
Unfortunately, the channels through which these updates are delivered can be exploited by attackers.
Adversaries can hijack the update, or the software that orchestrates the updates, to gain access to the user's data.

#### Examples

- An update to the Ukrainian tax software MeDoc was hijacked and used to distribute the Petya ransomware to an estimated 1 million computers in 2017. [^3]
- 

### Undermining Code Signing

Code signing is used to validate the authorship and integrity of a software package.
It is frequently used in closed software ecosystems like the iOS App Store.
Code signing helps software vendors defend against update hijacking, so attackers must thwart it if they intend on performing these kinds of attacks in secure environments.

Code signing is only as secure as the certificates used to sign the code.
If attackers manage to steal a vendor's code signing certificate, they can distribute malicious versions of software unbeknownst to users.

#### Examples

- The APT 41 hacking group[^4] have been involved in a number attacks involving stolen code signing certificates. They are wanted by the FBI.[^5]

[^1]: [Defending Against Software Supply Chain attacks](https://www.cisa.gov/sites/default/files/publications/defending_against_software_supply_chain_attacks_508_1.pdf)
[^2]: [Obligatory xkcd](https://xkcd.com/1428/)
[^3]: [2017 Ukraine ransomware attacks](https://en.wikipedia.org/wiki/2017_Ukraine_ransomware_attacks)
[^4]: [APT 41](https://en.wikipedia.org/wiki/Double_Dragon_(hacking_group))
[^5]: [APT 41 - WANTED BY THE FBI](https://www.fbi.gov/wanted/cyber/apt-41-group)