# 🛰️ Nmap: Live Host Discovery – TryHackMe Write-up

## 📘 Room Overview

This write-up documents my learning experience from the **“Nmap Live Host Discovery”** module on TryHackMe. The room focuses on practical techniques for discovering which devices are active (or "live") on a network, using different methods provided by **Nmap**, one of the most powerful and widely used network scanning tools in cybersecurity.

Host discovery is a **critical first step** in network reconnaissance. Before any vulnerability scanning or exploitation can begin, identifying which hosts are reachable is essential.

---

## 🔍 Techniques Practiced

In this room, I explored multiple ways Nmap can discover live hosts, even in networks where traditional ping is blocked or filtered.

---

### 1. ✅ ICMP Echo Request (`-PE`)

The most common form of host discovery — sending standard ping (ICMP Echo) requests.


nmap -PE <target>
How it works:

Sends an ICMP Echo Request to the target.

If an Echo Reply is received, the host is considered alive.

Pros:

Fast and lightweight.

Cons:

Often blocked by firewalls and endpoint security tools.

2. ✅ ICMP Timestamp Request (--script=icmp-timestamp)
An alternative ICMP-based method that sends ICMP Type 13 (Timestamp Request).

nmap --script=icmp-timestamp <target>

How it works:

Sends an ICMP Timestamp request.

If the host replies with its clock values, it's confirmed to be online.

Use case:

Helpful when Echo requests are blocked.

Can expose host uptime or timezone information.

3. ✅ TCP SYN Ping (-PS)
Performs host discovery by sending SYN packets to a specified TCP port (like port 23 for Telnet).


sudo nmap -PS23 <target>
How it works:

Sends a TCP SYN packet to the specified port.

If a SYN-ACK is received, the host is alive.

Why use Telnet (port 23)?

It’s often open on legacy systems.

Can bypass ICMP filtering if the firewall allows SYNs.

Privileges:

Requires root/admin privileges for ports < 1024.

4. ✅ TCP ACK Ping (-PA)
Sends TCP ACK packets instead of SYN, useful for evading stateless firewalls.


sudo nmap -PA80 <target>
How it works:

Sends TCP ACK packets to simulate part of an established connection.

Useful for discovering hosts behind firewalls that allow ACK packets but block others.

Privileges:

Also requires elevated privileges.

5. ✅ ARP Ping Scan (-PR)
ARP-based discovery is extremely accurate on local networks.

nmap -PR 192.168.1.0/24

How it works:

Sends ARP requests to all IPs in the subnet.

Any device that responds is recorded as live.

Use Case:

Only works within the same LAN (Local Area Network).

Ideal for home labs or internal network discovery.

Pros:

Cannot be blocked like ICMP or TCP scans.

🧠 Key Takeaways
Host discovery is the foundation of network reconnaissance.

ICMP-based scans are common, but easily filtered.

TCP SYN/ACK scans are useful for evading ICMP-blocking firewalls.

ARP scanning is the most reliable for local networks, as it cannot be filtered by firewalls.

The type of scan you choose depends on your privileges and network environment.

Nmap provides both privileged and non-privileged scanning options (e.g., -PS12345 does not require root, but -PA or -PS23 does).

🚀 Tools Used
Nmap (CLI)

Kali Linux / AttackBox (TryHackMe virtual machine environment)

Terminal for all command execution

Wireshark (optional) to analyze raw packets for educational purposes

# Example Commands Summary

nmap -PE 10.10.10.10               # ICMP Echo ping
nmap --script=icmp-timestamp 10.10.10.10     # ICMP Timestamp ping
sudo nmap -PS23 10.10.10.10        # TCP SYN ping to Telnet (privileged)
sudo nmap -PA80 10.10.10.10        # TCP ACK ping (privileged)
nmap -PR 10.10.10.0/24             # ARP scan for local network
nmap -PS12345 10.10.10.10          # Unprivileged SYN ping on high port

https://tryhackme.com/room/nmap01
