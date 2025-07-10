#  Unified Kill Chain – TryHackMe Writeup

> **Platform:** TryHackMe  
> **Room Name:** Unified Kill Chain  
> **Level:** Beginner – Intermediate  
> **Status:** = Completed

---

##  What is the Unified Kill Chain?

The **Unified Kill Chain (UKC)** is a modern threat modeling framework that combines:
- MITRE ATT&CK (focuses on post-compromise tactics)
- Lockheed Martin’s Cyber Kill Chain (focuses on pre-compromise)

It helps defenders understand the **full lifecycle of an attack** — from initial recon to exfiltration — and where to place defenses.

---

##  Key Takeaways from the Room

### 1.  **Understanding the Structure**
The UKC has **18 phases** grouped into 3 main sections:

| Stage           | Description |
|------------------|-------------|
| **Initial Foothold** | How attackers get in (e.g., phishing, drive-by download) |
| **Persistence & Control** | How they stay in and expand (e.g., privilege escalation, lateral movement) |
| **Action on Objectives** | What they actually do (e.g., data exfiltration, impact) |

---

### 2. 🕵️‍♂️ **Techniques Explored**
| Phase | Example Techniques |
|-------|---------------------|
| Initial Recon | DNS harvesting, passive scanning |
| Initial Foothold | Malicious email, fake websites |
| C2 | Remote Access Trojans (RATs), reverse shells |
| Lateral Movement | RDP, SMB, shared credentials |
| Exfiltration | Upload to cloud services, encrypted ZIP files |

---

##  Why This Matters

Understanding UKC allows defenders to:
- See **both sides** of an attack (initial entry + post-exploitation)
- Map out **defensive strategies**
- Connect detection rules to specific phases
- Identify **weak points** in their own security posture

---

## Tools Mentioned / Used

- MITRE ATT&CK Navigator
- Cyber Kill Chain Reference
- Burp Suite (for simulated attacks)
- Common malware techniques like reverse shells and file dropping

---

##  Summary

The Unified Kill Chain bridges the gap between **initial compromise** and **impact** by offering a unified view of attack paths. By studying it, I’m better equipped to:
- Recognize red flags earlier
- Build layered defense strategies
- Think like an attacker (to defend better)

---

## 
References

- [TryHackMe – Unified Kill Chain](https://tryhackme.com/room/unifiedkillchain)
- [MITRE ATT&CK](https://attack.mitre.org/)
- [Lockheed Martin Cyber Kill Chain](https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html)

---

> _"If you know the enemy and know yourself, you need not fear the result of a hundred battles."_ – **Sun Tzu**

---

**Writeup by Amoako Lloyd**  
Part of [Cybersecurity Labs](https://github.com/lloyd2608/Cybersecurity-Labs)
