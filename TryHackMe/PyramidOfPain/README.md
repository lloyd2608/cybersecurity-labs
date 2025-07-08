 TryHackMe: Pyramid of Pain

**Room Link**: [https://tryhackme.com/room/pyramidofpain](https://tryhackme.com/room/pyramidofpain)  
**Difficulty**: Easy  
**Topic**: Threat Intelligence, Detection Strategy  
**Focus**: Understanding the levels of adversary behavior and how defenders can respond effectively.

---

 What is the Pyramid of Pain?

The **Pyramid of Pain** is a cybersecurity concept developed by David Bianco. It helps analysts understand **which types of indicators are most valuable** in detecting and stopping threat actors.

The pyramid is arranged from **bottom (easiest for attacker to change)** to **top (hardest to change)**:

1. **Hash Values** – File hashes like MD5/SHA256  
2. **IP Addresses** – Can be changed or rotated easily  
3. **Domain Names** – Easily swapped out  
4. **Network/Host Artifacts** – Patterns left behind in logs  
5. **Tools** – Malware or utilities used by attackers  
6. **Tactics, Techniques, and Procedures (TTPs)** – The attacker’s habits and playbook

---

##  Objective of the Room

- Understand each layer of the Pyramid of Pain  
- Learn how threat intel is gathered  
- Identify which indicators are most impactful in threat detection  
- Strengthen cyber defense strategies

---

##  Tools & Skills Practiced

- Threat Intelligence Analysis  
- MITRE ATT&CK Framework  
- Blue Team Defense Thinking  
- Log Analysis Awareness  

---

##  Answers (Key Concepts Only – No Room Spoilers)

> This is a high-level educational summary and **does not contain flags** or direct answers from the room.

- **Why is detecting TTPs more valuable than hashes?**  
  Because TTPs represent behaviors and strategies, not just static data. Attackers can't change their habits easily like they can change a file hash.

- **What’s wrong with relying only on IP addresses and domains?**  
  These are easily rotated or obfuscated (via proxies, VPNs, or DGA domains), so they don't provide long-term protection.

- **What should defenders focus on most?**  
  Patterns in attacker behavior and common tools, rather than just surface-level indicators.

---

##  What I Learned

- Indicators like IPs and hashes are helpful but **limited**.
- Understanding **attacker behavior (TTPs)** is critical for building **long-term defenses**.
- The higher you go on the pyramid, the **harder it is for attackers to change**, making your detection more effective.

---

## Extra Reading

- [David Bianco’s Original Blog Post](https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html)  
- [MITRE ATT&CK Framework](https://attack.mitre.org/)  
- [Threat Hunting Guide - SANS](https://www.sans.org/white-papers/)

---

##  Tags

`#ThreatIntelligence` `#TryHackMe` `#PyramidOfPain` `#BlueTeam` `#CyberSecurity` `#MITRE`

---

> ✅ This writeup is for learning and documentation purposes only.
