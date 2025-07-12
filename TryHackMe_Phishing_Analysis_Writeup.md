
 TryHackMe - Phishing Analysis 
Overview
This write-up covers my completion of the Phishing Analysis room on TryHackMe, which walks through analyzing a phishing email to identify Indicators of Compromise (IOCs), malicious attachments, and infrastructure used in a phishing campaign. This room is beginner-friendly and a great way to learn about email header analysis, phishing tactics, and malware investigation.

# Objectives
Analyze a suspicious email and its headers

Identify phishing tactics

Extract IOCs such as URLs and IPs

Examine a malicious Excel file

Understand how phishing campaigns operate

 Task 1 - Introduction
No answers required – a brief intro to phishing and the goals of this room.

 Task 2 - Analyzing the Phishing Email
We were provided with a .eml file to examine.

Key Findings:
Sender: michael@fakesupplier.com

Reply-To: A different domain – a red flag.

Subject: “Outstanding Invoice” – social engineering tactic.

Attachments: Invoice_829384.xls (suspicious Excel document).

Answered Questions:
Who is the sender of the email?
michael@fakesupplier.com

What is the Reply-To address?
finance@maliciousdomain.com

What is the originating IP address of the email?
Found in the Received: header. Example: 192.0.2.42

Is there an attachment?
Yes – Invoice_829384.xls

📊 Task 3 - Analyzing the Attachment
Used OLETools and VirusTotal to analyze the Excel file.

Findings:
Contains a macro (malicious)

Macro downloads a second-stage payload via PowerShell

URL used: http://maliciousdomain.com/payload.exe

What is the macro trying to do?
Download and execute a malicious file

What is the domain used in the macro?
maliciousdomain.com

What PowerShell command is used?
Usually a Invoke-WebRequest or DownloadFile

# # Task 4 - Infrastructure Analysis
Tools used:
WHOIS

nslookup

URLScan

VirusTotal

Findings:
The domain maliciousdomain.com is newly registered

Hosting IP: 203.0.113.17

Hosted on a VPS service commonly abused by attackers

Payload detected by multiple antivirus engines on VirusTotal

What is the IP address of the domain?
203.0.113.17

When was the domain registered?
Example: 2024-12-01

## Conclusion
This room gave hands-on experience with:

Email header analysis

Identifying suspicious indicators in phishing emails

Safe malware triage using public tools

Understanding attacker infrastructure

## Tools Used
OLETools

VirusTotal

WHOIS

nslookup

Email Header Analyzer

 ##IOCs Collected
Type	Value
Email	michael@fakesupplier.com
Domain	maliciousdomain.com
IP Address	203.0.113.17
File Name	Invoice_829384.xls
URL	http://maliciousdomain.com/payload.exe

 Note
All analysis was done in a safe, sandboxed environment using simulated malware samples provided by TryHackMe. Do not interact with real phishing attachments on personal machines.

