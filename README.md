# Stealth Attack Detection & Response Lab (Linux SOC Simulation)

## Overview
_This project simulates a stealth-focused attack against a Linux system and demonstrates how defensive monitoring tools can still detect suspicious activity despite attempts to evade visibility._

The lab covers:
- Initial access
- Persistence
- Defense evasion
- Detection
- Investigation
- Incident response

_The objective was to better understand how attackers hide activity and how SOC analysts investigate anomalies in Linux environments._

---

## Lab Architecture

 Kali Linux - Attacker VM \
 Ubuntu - Victim VM \
 Wazuh Server - Monitoring & Detection 

---

## Tools Used

- nc tools
- Git
- GCC
- Make
- Diamorphine
- Wazuh

---

## Attack Scenario

_An attacker gains remote access to a Linux system, establishes persistence, hides malicious activity using a rootkit, and attempts to avoid detection._

The SOC environment monitors the system for:
- Hidden processes
- Rootkit behavior
- Persistence mechanisms
- Suspicious network activity

---

## Key Skills Demonstrated

- Linux system monitoring
- Threat detection
- Rootkit analysis
- Process hiding
- Persistence techniques
- SOC investigation workflow
- Incident response

---


## 5️⃣ Defense Evasion — Diamorphine Rootkit

### Attack

The Diamorphine Linux rootkit was deployed to simulate:

* hidden processes
* hidden kernel module activity
* defense evasion behavior

### Detection

Detection methods included:

* hidden process detection
* kernel anomaly monitoring
* process visibility inconsistencies

### MITRE ATT&CK

| Technique      | ID    |
| -------------- | ----- |
| Rootkit        | T1014 |
| Hide Artifacts | T1564 |

---
