# 🛡️ Threat Analysis & Incident Response: Humans as Attack Vectors

**Author:** [Kavindu Madhushan / kaviboy1718]   
**Platform:** TryHackMe  
**Category:** Defensive Security / SOC Operations / Security Awareness  
**Completion Status:** 100% Complete  

---

## 📋 Executive Summary

Human targets remain one of the most frequently exploited attack surfaces in enterprise environments. This lab simulated a SOC Analyst role tasked with triaging security incidents, investigating social engineering tactics, analyzing SIEM/Endpoint alerts, and implementing mitigating security controls to protect enterprise personnel.

---

## 🔍 Incident Triage & Analysis

### Summary Matrix

| Incident ID | Target Employee | Threat Vector | Tactic / Technique | Status |
| :--- | :--- | :--- | :--- | :--- |
| **INC-01** | Lucas Martinez (Software Eng.) | Drive-by Download / Fake Freeware | Malicious Executable (`Setup.exe`) | **Mitigated** |
| **INC-02** | Mark Phillips (Finance Dir.) | Spearphishing Attachment | Password-Protected Archive (`Invoice.rar`) | **Mitigated** |
| **INC-03** | Isabella (IT Support) | Voice Phishing (Vishing) / AI | Audio Deepfake Impersonating CEO | **Mitigated** |
| **INC-04** | Rose Lewis (HR Assistant) | Phishing / Typosquatting | Credential Harvesting Landing Page | **Mitigated** |

---

### Incident Breakdowns

#### Incident 01: Drive-by Download & Data Stealer Triage
* **Target:** Lucas Martinez *(Software Engineer)*
* **Description:** User requested support after failing to launch a 7-Zip installation downloaded from an untrusted third-party freeware repository (`best-freeapps-2025[.]top`).
* **Analysis & Findings:** Endpoint Protection blocked execution after 6 attempts. Static/dynamic analysis confirmed `Setup.exe` was an Infostealer/Data Stealer.
* **MITRE ATT&CK Mapping:** T1204.002 *(User Execution: Malicious File)*, T1189 *(Drive-by Compromise)*

![Lucas Martinez Quarantine Alert] 

<img width="670" height="640" alt="1" src="https://github.com/user-attachments/assets/5242c918-4c41-46d4-b413-a67ed52041c6" />


---

#### Incident 02: Financial Spearphishing via Encrypted Archive
* **Target:** Mark Phillips *(Finance Director)*
* **Description:** SIEM alert flagged an incoming email originating from `noreply@stripe-payments[.]xyz` referencing an invoice payment of $23,650.00.
* **Analysis & Findings:** Email spoofing detected; domain mismatch (`stripe-payments.xyz` vs official `stripe.com`). Attached archive `Invoice.rar` contained a password-protected malicious `.docx` payload designed to bypass email gateway filters.
* **MITRE ATT&CK Mapping:** T1566.001 *(Phishing: Spearphishing Attachment)*

![Mark Phillips Phishing Email Analysis]

<img width="673" height="638" alt="2" src="https://github.com/user-attachments/assets/66d575bd-d12f-4077-9a5b-ff6d89ed928f" />


---

#### Incident 03: Executive Impersonation via Audio Deepfake
* **Target:** Isabella *(IT Support)*
* **Description:** IT Support received a call from an unidentified number claiming to be CEO Ben, requesting an urgent Gmail password reset.
* **Analysis & Findings:** Logs showed a valid login from the CEO's routine geographical area (USA), but follow-up verification via secondary channels failed as the CEO did not confirm the call. Confirmed as an AI-generated voice deepfake targeting IT helpdesk authentication workflows.
* **MITRE ATT&CK Mapping:** T1566.003 *(Phishing: Spearphishing Voice / Vishing)*

![Isabella Vishing / Deepfake Incident]

<img width="677" height="643" alt="3" src="https://github.com/user-attachments/assets/a32768c3-1646-4a7a-a0dd-2b9d6f49bfbb" />


---

#### Incident 04: Credential Harvesting via Typosquatting
* **Target:** Rose Lewis *(HR Assistant)*
* **Description:** SIEM flagged an anomalous Microsoft 365 login location (London, UK vs typical Oxford, UK).
* **Analysis & Findings:** Web proxy logs revealed pre-login navigation to `login[.]micrsoft365-online[.]ru` and `hroyhiqtspqgkp[.]info`. The user fell victim to a typosquatting phishing page designed to harvest enterprise credentials.
* **MITRE ATT&CK Mapping:** T1566.002 *(Phishing: Spearphishing Link)*, T1078 *(Valid Accounts)*

![Rose Lewis Phishing Analysis]

<img width="679" height="646" alt="4" src="https://github.com/user-attachments/assets/f4ff8e20-8d4d-4ad3-a084-5e5fdfe82fb8" />


---

### Phase Completion Verification
![Phase 1 Completed]

<img width="678" height="644" alt="5" src="https://github.com/user-attachments/assets/d3e56994-af6c-46a2-be63-88a3bb065b42" />


---

## 🛡️ Defensive Mitigations & Policy Control Framework

To prevent similar incident vectors, the following enterprise security controls were evaluated and selected:

1. **Security Awareness Program:** Regular phishing simulations and employee education to reduce user susceptibility to social engineering.
2. **Access Management Policy:** Strict multi-factor authentication (MFA) and out-of-band verification requirements for IT password resets (mitigating voice deepfakes).
3. **Anti-Phishing & Gateway Solutions:** Advanced email filtering to inspect headers, domains, and analyze password-protected attachments.
4. **Antivirus / Endpoint Detection & Response (EDR):** Endpoint protection policies to quarantine unknown executables and block untrusted downloads.

![Policy Feedback & Assessment]

<img width="677" height="646" alt="6" src="https://github.com/user-attachments/assets/74f12b1f-b010-42d8-99fb-ea22a6ac6f71" />
  
![Policy Selection Complete]

<img width="664" height="647" alt="7" src="https://github.com/user-attachments/assets/f1706784-50c3-4e82-8e5f-1e0302f555ca" />


---

## 📊 Lab Artifacts & Proof of Completion

![Dashboard 100% Completion]

<img width="669" height="646" alt="8" src="https://github.com/user-attachments/assets/539bb386-965e-41ad-b481-7d8b98d6722f" />
  
![TryHackMe Badge]

<img width="1365" height="646" alt="9" src="https://github.com/user-attachments/assets/ff63af0d-b32c-4459-9df2-e835f78cdd94" />



# ⚙️ Threat Analysis & System Hardening: Systems as Attack Vectors

**Author:** [Kavindu Madhushan / kaviboy1718]   
**Platform:** TryHackMe  
**Category:** Defensive Security / SOC Operations / Vulnerability Management  
**Completion Status:** 100% Complete  

---

## 📋 Executive Summary

Unpatched software, weak authentication, legacy network appliances, and compromised software supply chains represent primary attack vectors targeting enterprise infrastructure. This lab simulated a SOC Analyst tasked with identifying system vulnerabilities, triaging active exploitation alerts, containing supply chain compromises, and establishing hardening policies to mitigate technical exposure.

---

## 🔍 Incident Triage & System Vulnerability Analysis

### Summary Matrix

| Incident ID | System Target | Threat Vector | Vulnerability / Root Cause | Mitigation Strategy |
| :--- | :--- | :--- | :--- | :--- |
| **SYS-01** | `HQ-MAIL-02` *(Exchange Server)* | Public Exploit Exposure | CVE-2024-49040 | Emergency Patching & Threat Hunting |
| **SYS-02** | Corporate Website *(WordPress)* | Password Spraying / Brute-Force | Weak Admin Credentials | Credential Reset & Backdoor Removal |
| **SYS-03** | London Edge Firewall *(Cisco)* | Legacy Hardware Vulnerability | Unpatched Firmware / EOL Device | Firmware Upgrade & Policy Auditing |
| **SYS-04** | `LPT-01518` *(Designer Workstation)*| Software Supply Chain Attack | Malicious Third-Party Update | Application Containment & Rollback |

---

### Incident Breakdowns

#### Incident 01: Exchange Mail Server Vulnerability (CVE-2024-49040)
* **Target System:** `HQ-MAIL-02` *(Microsoft Exchange)*
* **Description:** Penetration testing identified an internet-exposed Exchange server susceptible to CVE-2024-49040 exploitation.
* **Analysis & Findings:** Applied immediate patch management protocols to remediate the vulnerability at the root level, followed by threat hunting queries to detect post-exploitation indicators prior to patch application.
* **MITRE ATT&CK Mapping:** T1190 *(Exploit Public-Facing Application)*

![Exchange Vulnerability Triage]

<img width="667" height="647" alt="1" src="https://github.com/user-attachments/assets/e58f2f33-d786-4a61-9456-e4bb0fd646e8" />

---

#### Incident 02: CMS Defacement & Credential Compromise
* **Target System:** Corporate WordPress Web Server
* **Description:** Threat actors successfully brute-forced the WordPress administrative panel, replacing the landing page with malicious redirection links and gambling advertisements.
* **Analysis & Findings:** Mitigated compromised administrative credentials, initialized website restoration from secure backups, and initiated web shell / persistence sweeps to locate left-behind backdoors.
* **MITRE ATT&CK Mapping:** T1110 *(Brute Force)*, T1491 *(Defacement)*, T1505.003 *(Web Shell)*

![WordPress Brute Force Analysis]

<img width="666" height="642" alt="2" src="https://github.com/user-attachments/assets/401651e3-c641-4443-b8a0-a060cf1a365e" />

---

#### Incident 03: Proactive Threat Intel & Legacy Edge Hardening
* **Target System:** London Office Cisco Firewall Appliance
* **Description:** Threat Intelligence reported a neighboring organization compromised via ransomware originating from legacy Cisco firewall exploits.
* **Analysis & Findings:** Performed an emergency device audit, located an outdated edge firewall in the London branch, and applied current vendor security patches before weaponized exploitation occurred.
* **MITRE ATT&CK Mapping:** T1190 *(Exploit Public-Facing Application)*, T1595 *(Active Scanning)*

![Cisco Firewall Audit]

<img width="670" height="647" alt="3" src="https://github.com/user-attachments/assets/bb47cac4-48f0-4581-a14e-fac963d946c6" />

---

#### Incident 04: Software Supply Chain Compromise
* **Target System:** `LPT-01518` *(3D Designer Laptop)*
* **Description:** Endpoint telemetry flagged anomalous activity; a trusted 3D design application executed unauthorized Windows Command Shell (`cmd.exe`) commands following a routine vendor update.
* **Analysis & Findings:** Identified as a trusted vendor supply chain compromise (`T1195.002`). Isolated the workstation process to prevent lateral movement.
* **MITRE ATT&CK Mapping:** T1195.002 *(Supply Chain Compromise)*, T1059.003 *(Windows Command Shell)*

![Supply Chain Incident Analysis]

<img width="665" height="635" alt="4" src="https://github.com/user-attachments/assets/200171be-f0b2-4902-a3ba-e31844ba5493" />

---

### Phase Completion Verification
![Systems at Risk Completed]

<img width="667" height="647" alt="5" src="https://github.com/user-attachments/assets/b135c162-4569-45d2-a8ec-d33f48d58a27" />
---

## 🛡️ Enterprise Hardening & Remediation Framework

To secure enterprise systems against recurring attack vectors, the following remediation policies were implemented:

1. **Patch Management Policy:** Standardized vulnerability scanning and patch deployment cycles for public-facing assets and edge devices.
2. **Secure Password Policy:** Mandated complex passphrases and account lockout limits to prevent brute-force attacks against administrative consoles.
3. **Antivirus / Endpoint Protection:** Deployed host-based signatures and behavioral telemetry to detect data stealers, USB worms, and suspicious child process spawning.
4. **Security Training for IT Personnel:** Educated system administrators on secure configuration standards and backdoor threat hunting.

![Remediation Plan Feedback]

<img width="671" height="645" alt="6" src="https://github.com/user-attachments/assets/0ce86d64-970e-4c74-965c-9552c2d7fdac" />  

![Remediation Approved]

<img width="662" height="646" alt="7" src="https://github.com/user-attachments/assets/a25763d9-afa7-42f5-b5c0-82a41f645dfc" />
---

## 📊 Lab Artifacts & Proof of Completion

![Dashboard 100% Completion]

<img width="663" height="647" alt="8" src="https://github.com/user-attachments/assets/a632bca8-7f6e-4674-b4a7-009eb7e12a61" />  

![TryHackMe Completion Badge]

<img width="1364" height="645" alt="9" src="https://github.com/user-attachments/assets/2521ef3f-3e2d-40d5-870d-d0483f4a35c6" />



# 🛡️ Enterprise SIEM Alert Triage & Incident Response

## 📌 Overview
This repository documents the end-to-end triage, investigation, and disposition of security alerts processed within an enterprise Security Operations Center (SOC) SIEM environment. The objective is to evaluate real-time telemetry, differentiate baseline corporate noise (**False Positives**) from genuine threat vectors (**True Positives**), and execute appropriate incident containment and remediation playbooks.

---

## 🖥️ SOC Dashboard Initial State

![SOC Alert Dashboard Overview]

<img width="1218" height="641" alt="5 1" src="https://github.com/user-attachments/assets/338a46a6-a6a0-4401-98d5-7fa8820d08b3" />


---

## 📊 Shift Summary Matrix

| Alert Timestamp | Alert Name | Severity | Targeted Host / User | Verdict | Final Disposition | Assigned Analyst |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Mar 21, 11:53** | Bruteforce Attack from External | Medium | Gateway Perimeter | **True Positive** | Closed | J.Adams (L2) |
| **Mar 21, 12:40** | Unusual VPN Login Location | Medium | `M.Clark` | **False Positive** | Closed | T.Ross (L1) |
| **Mar 21, 13:02** | Download from GitHub Repository | Low | `LPT-IT-063` (`G.Chandler`) | **False Positive** | Closed | You (L1) |
| **Mar 21, 13:30** | Potential Data Exfiltration | Critical | `UK04/MEETINGROOM` | **False Positive** | Closed | You (L1) |
| **Mar 21, 13:58** | Double-Extension File Creation | High | `LPT-HR-009` (`S.Conway`) | **True Positive** | Closed / Contained | You (L1) |

---

## 🔍 Detailed Alert Investigations & Evidence

### 1. Potential Data Exfiltration
* **Timestamp:** Mar 21st 2025 at 13:30
* **Severity:** Critical
* **Source Network / IP:** `UK04/MEETINGROOM` | `192.168.45.66`
* **Destination:** `*.zoom.us`
* **Data Transferred:** 5.8 GB Sent / 5.2 GB Received
* **Verdict:** **False Positive**

#### Investigation & Summary
The SIEM triggered a threshold alert for sending >5 GB of data in a day. Forensic investigation revealed the traffic originated from an internal meeting room network (`UK04/MEETINGROOM`) and was directed exclusively to a trusted enterprise domain (`*.zoom.us`). The balanced ratio of uploaded to downloaded data (5.8 GB vs 5.2 GB) indicates high-definition video conferencing activity rather than malicious exfiltration.

![Potential Data Exfiltration Closed Ticket]

<img width="1218" height="425" alt="5 2" src="https://github.com/user-attachments/assets/5a7866fa-8ab8-42e2-a323-828d8e8a9bda" />


---

### 2. Double-Extension File Creation
* **Timestamp:** Mar 21st 2025 at 13:58
* **Severity:** High
* **Source Host / User:** `LPT-HR-009` | `S.Conway`
* **Process:** `chrome.exe`
* **Target File:** `C:\Users\S.Conway\Downloads\cats2025.mp4.exe`
* **File MotW / URL:** `https://freecatvideoshd.monster/cats2025.mp4.exe`
* **File MD5:** `14d8486f3f63875ef93cfd240c5dc10b`
* **Verdict:** **True Positive**

#### Investigation & Escalation
A user downloaded an executable file disguised with a double extension (`cats2025.mp4.exe`) via Google Chrome from a suspicious top-level domain (`.monster`). This represents a classic social engineering technique (T1036.007 Masquerading) to bypass user awareness and trigger arbitrary code execution.

1. **Initial Alert Snapshot:**
   ![Double Extension Alert Overview]

   <img width="1216" height="370" alt="5 3" src="https://github.com/user-attachments/assets/a0eef889-bfa1-4798-9a10-62a2096b423a" />


3. **Remediation & Closure:**
   Host `LPT-HR-009` was targeted for network isolation and endpoint containment to prevent payload execution. Active Directory credentials for `S.Conway` were queued for reset.

   ![Double Extension Closed Ticket]

   <img width="1220" height="460" alt="5 4" src="https://github.com/user-attachments/assets/08efa945-9d6d-4934-8f5d-5c89290b650f" />


---

### 3. Download from GitHub Repository
* **Timestamp:** Mar 21st 2025 at 13:02
* **Severity:** Low
* **Source Network / Host:** `VPN/DEVELOPERS` | `LPT-IT-063`
* **User:** `G.Chandler`
* **Accessed URL:** `https://github.com/facebook/react`
* **Verdict:** **False Positive**

#### Investigation & Tuning
The SIEM flagged an external code repository download. Reviewing contextual logs confirmed that the request originated from the developer network segment (`VPN/DEVELOPERS`) accessing Meta's official open-source React framework (`facebook/react`). This is normal baseline behavior for internal engineers.

1. **Initial Alert Snapshot:**
   ![GitHub Download Alert Details]

   <img width="1220" height="304" alt="5 5" src="https://github.com/user-attachments/assets/360cde8e-e371-463a-821d-d40ae3418a8b" />


3. **Remediation & Closure:**
   Closed as a False Positive. Recommended white-listing official corporate developer repositories to reduce SIEM alert noise.

   ![GitHub Download Closed Ticket]

   <img width="1214" height="389" alt="5 6" src="https://github.com/user-attachments/assets/0cd71d3e-2aea-4ab9-867e-dc8fb50e6afd" />


---

## 🏆 Lab Completion & Performance Summary

![Room Completed Badge]

<img width="1365" height="646" alt="6" src="https://github.com/user-attachments/assets/71b8367e-64e4-4b91-a136-f8711eee7847" />



# 🛡️ Enterprise SIEM Alert Triage & Incident Investigation

## 📌 Overview
This repository documents the end-to-end triage, analysis, and escalation of security alerts captured during a simulated shift within an enterprise Security Operations Center (SOC). The shift involved analyzing email security breaches, active host compromise, process execution trees, and Active Directory reconnaissance.

---

## 🖥️ SOC Dashboard Overview

![SOC Alert Dashboard Overview]

<img width="1286" height="366" alt="1 1" src="https://github.com/user-attachments/assets/388d851c-b01f-4cc2-9ebe-8a60ea9995d2" />

---

## 📊 Shift Summary Matrix

| Alert Timestamp | Alert Name | Severity | Targeted Host / Recipient | Verdict | Status | Assigned Analyst |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Mar 27, 18:02** | Fast Beaconing to Untrusted Domain | High | Internal Network | **False Positive** | Closed | S.Todd (L1) |
| **Mar 27, 18:30** | Sensitive Document Share to External | Medium | Enterprise Data | **True Positive** | In Progress | E.Fleming (L2) |
| **Mar 27, 19:10** | Web Scanning of Corporate Resources | Low | Web Infrastructure | **True Positive** | In Progress | E.Fleming (L2) |
| **Mar 27, 19:25** | Email Marked as Phishing after Delivery | Medium | `e.huffman@tryhackme.thm` | **True Positive** | In Progress | You (L1) |
| **Mar 27, 19:56** | Spike of Domain Discovery Commands | Medium | `DMZ-MSEXCHANGE-2013` | **True Positive** | In Progress / Escalated | E.Fleming (L2) |

---

## 🔍 Detailed Alert Investigations & Evidence

### 1. Email Marked as Phishing after Delivery
* **Timestamp:** Mar 27th 2025 at 19:25
* **Severity:** Medium
* **Target Recipient:** Eddie Huffman, IT Manager (`e.huffman@tryhackme.thm`)
* **Header Sender:** `Microsoft Support <support@microsoft.com>`
* **Authentication Checks:** **SPF: Fail** | **DKIM: Fail**
* **Attachment:** `REPORT.rar`
* **Verdict:** **True Positive**

#### Investigation Details
An automated post-delivery check flagged a social engineering attempt impersonating Microsoft Support regarding an urgent "600% price increase" for Microsoft Teams. Email header inspection confirmed complete failure of both **SPF** and **DKIM** authentication protocols, indicating identity spoofing. The email contained a malicious archive file (`REPORT.rar`).

1. **Alert Details & Indicators:**
   ![Phishing Alert Details]

   <img width="1287" height="402" alt="1 2" src="https://github.com/user-attachments/assets/01ae6bce-69ce-4f9a-8247-2ece5e78c13a" />


3. **Triage & Analyst Actions:**
   Marked as True Positive. Queued for immediate inbox purge, attachment hash extraction, and domain blocking at the secure email gateway (SEG).

   ![Phishing Ticket Resolution]

   <img width="670" height="484" alt="1 3" src="https://github.com/user-attachments/assets/fc043e58-9345-4877-81df-ebf17acb8d3b" />


---

### 2. Spike of Domain Discovery Commands (Host Compromise)
* **Timestamp:** Mar 27th 2025 at 19:56
* **Severity:** Medium / High Escalation
* **Target Host:** `DMZ-MSEXCHANGE-2013` (Windows Server 2012 R2)
* **Account:** `NT AUTHORITY\SYSTEM`
* **Process Hierarchy:** `w3wp.exe` → `revshell.exe` → `cmd.exe`
* **Commands Invoked:** `dir`, `hostname`, `whoami /priv`, `net group "Domain Admins" /domain`, `nltest /dclist:tryhackme.thm`
* **Verdict:** **True Positive**

#### Investigation & Incident Escalation
Process lineage analysis revealed that the IIS Web Server process (`w3wp.exe`) spawned an unauthorized backdoor executable (`revshell.exe`) located in `C:\Users\Public\`. Under `NT AUTHORITY\SYSTEM` privileges, the process executed multiple commands to map Active Directory structure and query Domain Admin groups.

1. **Process Lineage & Command Details:**
   ![Domain Discovery Alert Details]

   <img width="1281" height="422" alt="2 1" src="https://github.com/user-attachments/assets/5b720364-7bfe-4a63-83e4-050025f86cd9" />


3. **Incident Response Actions:**
   Escalated immediately to L2 Incident Response. Initiated host network isolation on `DMZ-MSEXCHANGE-2013` to prevent lateral movement and credential dumping across the domain.

   ![Domain Discovery Escalation Note]

   <img width="1275" height="489" alt="2 2" src="https://github.com/user-attachments/assets/3a2bd709-8bd2-41ab-bcf0-de857b218d04" />


---

## 🏆 Lab Completion Summary

![Room Completed Badge]

<img width="1362" height="646" alt="3" src="https://github.com/user-attachments/assets/d7799ffc-f9df-48ee-8fc0-f23bf075b147" />




# 🛠️ Standardized SOC Playbooks & Workbooks Engineering

## 📌 Overview
This repository documents the design and implementation of standardized **Security Operations Center (SOC) Workbooks & Playbooks**. The objective of this project is to build structured, repeatable incident triage workflows for Tier 1 and Tier 2 analysts—ensuring rapid triage, proper evidence collection, accurate verdict determination, and appropriate escalation paths across critical attack vectors.

---

## 🗂️ Standardized Playbook Architecture

### 📧 Workbook 01: External Email With Script or Binary Attachment (Email Analysis)
Focuses on evaluating suspicious incoming emails, parsing headers, verifying sender authenticity, and analyzing risky attachments.

#### Action Builder & Decision Logic
1. **Initial Context:** Take ownership of the alert and use identity inventory to gather recipient context and roles.
2. **Header & Domain Triage:** Analyze the email via EML analyzer—verify SPF/DKIM authentication, inspect body content, and check sender domain reputation.
3. **Attachment Inspection:** Perform manual code review for scripts or execute binary attachments in a isolated sandbox environment.
4. **Verdict Decision Branch:**
   * **YES (Malicious/Faked/Unexpected):** Gather comprehensive triage evidence (recipient lists, sandbox report, EML analysis) $\rightarrow$ Draft detailed L2 alert report $\rightarrow$ **Escalate to L2 Incident Response**.
   * **NO (Benign/Expected):** Document justification comment explaining why the email is safe $\rightarrow$ **Close as False Positive**.

| Builder Interface | Completed Decision Flowchart |
| :---: | :---: |
| ![Email Builder]

<img width="667" height="647" alt="1 1" src="https://github.com/user-attachments/assets/a8298664-2253-46ce-a857-91fba275d043" />

| ![Email Flowchart]

<img width="593" height="548" alt="1 3" src="https://github.com/user-attachments/assets/76804c34-1c80-401a-bcd3-36efe12b3229" />


---

### ⚡ Workbook 02: Executable File Download using PowerShell (Endpoint Analysis)
Focuses on triaging command-line payload downloads, inspecting process hierarchies, and distinguishing legitimate administrative scripting from malicious staging.

#### Action Builder & Decision Logic
1. **Asset & Identity Mapping:** Assign alert, look up host context in asset inventory, and identify logged-in users.
2. **Threat Intelligence & Static Analysis:** Analyze payload download URLs against Threat Intel feeds and perform static file analysis on downloaded binaries.
3. **Process Tree Reconstruction:** Build the execution tree to identify parent processes (`cmd.exe`, `w3wp.exe`, etc.) and execution privilege levels.
4. **Verdict Decision Branch:**
   * **YES (Malicious/Untrusted/Suspicious Process):** Save SIEM search outputs (`[WIN] Process Tree` and `[WIN] LoginTimeline`) $\rightarrow$ Compile L2 report with assumptions and evidence $\rightarrow$ **Escalate to L2**.
   * **NO (Authorized Admin/Tuned Script):** Document findings and submit tuning recommendations to SOC Engineers $\rightarrow$ **Close as False Positive**.

| Builder Interface | Completed Decision Flowchart |
| :---: | :---: |
| ![PowerShell Builder]

<img width="668" height="647" alt="2 1" src="https://github.com/user-attachments/assets/02ae850e-6900-407b-af5d-0279448b3c5a" />

 ![PowerShell Flowchart]

 <img width="1280" height="853" alt="2 3" src="https://github.com/user-attachments/assets/a889fb85-2984-419f-841d-2a8792602c17" />


---

### 🌐 Workbook 03: Port Scanning From Internal IP (Network Analysis)
Focuses on internal discovery detection, separating authorized corporate scanner activity (e.g., Nessus, Zabbix) from rogue host discovery attempts.

#### Action Builder & Decision Logic
1. **Network Mapping:** Take ownership, retrieve IP location, role, and subnet context from asset inventory/network maps.
2. **Port & Service Profiling:** List target ports scanned by the source IP and map associated services.
3. **Authorized Scanner Verification:** Cross-reference source IP against baseline inventory for approved vulnerability/monitoring engines.
4. **Verdict Decision Branch:**
   * **YES (Unlisted IP / Malicious Discovery Pattern):** Collect attack timeframe, target port list, and network context $\rightarrow$ Draft L2 incident report $\rightarrow$ **Escalate to L2**.
   * **NO (Authorized Enterprise Scanner):** Document verdict comment and notify SOC Engineers to tune SIEM detection thresholds $\rightarrow$ **Close as False Positive**.

| Builder Interface | Completed Decision Flowchart |
| :---: | :---: |
| ![Network Builder]

<img width="644" height="536" alt="3 1" src="https://github.com/user-attachments/assets/87f95e0f-515f-4cf9-a575-639f46b73172" />

 ![Network Flowchart]

 <img width="598" height="520" alt="3 3" src="https://github.com/user-attachments/assets/a5e68f45-c5ef-43e2-b9e4-ba25b05f3d52" />


---

## 🏆 Lab Completion & SLA Metrics

![Room Completed Badge]

<img width="1364" height="645" alt="4" src="https://github.com/user-attachments/assets/5f7b696f-4fb1-44f8-830c-42a7d5b066a2" />



# 📊 SOC Metrics, SLAs & Operational Optimization

## 📌 Overview
This repository documents the operational audit, metric analysis, and process optimization strategies executed during the **SOC Metrics and Objectives** lab. The project focuses on diagnosing core performance bottlenecks across Security Operations Center (SOC) metrics—specifically **Time to Respond (TTR)**, **Time to Detect (TTD)**, and **False Positive Rate (FPR)**—and engineering remediation workflows to optimize incident response SLAs and mitigate analyst fatigue.

---

## 🗂️ Operational Scenarios & Remediation Framework

### 🚨 Scenario 01: High Containment Latency (Unhappy Customer)
* **Incident Summary:** A critical compromise of an executive's Entra ID and mailbox resulted in data exfiltration due to a 6-hour delay in account containment (5 hours lost strictly on resetting credentials and MFA).
* **Problematic Metric:** **Time to Respond (TTR)** — Containment execution took too long due to a lack of standard credential rotation procedures.
* **Remediation Plan:** Create a dedicated workbook detailing standardized credential rotation steps and present it to the team.
* **Task Owner:** Assigned to the L2 Incident Response Lead who handled the incident.

| Scenario Context | Remediation Action Plan |
| :---: | :---: |
| ![Scenario 1 Prompt]

<img width="670" height="646" alt="1 1" src="https://github.com/user-attachments/assets/2faf10a1-8f3f-4eed-99e1-c0e6b2ddb8a6" />
 
 ![Scenario 1 Solution]

 <img width="1024" height="773" alt="1 2 (1)" src="https://github.com/user-attachments/assets/c46518ba-b80d-4969-b35a-9896f0f132ae" />


---

### ⏳ Scenario 02: Delayed SIEM Detection (Delayed Alert)
* **Incident Summary:** During a ransomware simulation, threat containment succeeded in 40 minutes, but the first 20 minutes were lost waiting for the SIEM detection rules to trigger and generate alerts.
* **Problematic Metric:** **Time to Detect (TTD)** — A 20-minute detection schedule delayed initial alert triage.
* **Remediation Plan:** Tune the SIEM and detection rules to run more frequently at 5-minute intervals.
* **Task Owner:** Assigned detection rule schedule review to the dedicated SOC engineer.

| Scenario Context | Remediation Action Plan |
| :---: | :---: |
| ![Scenario 2 Prompt]

<img width="666" height="647" alt="2 1" src="https://github.com/user-attachments/assets/df96d35a-5cb7-4173-a996-a438d0679501" />

| ![Scenario 2 Solution]

<img width="1534" height="909" alt="2 2 (1)" src="https://github.com/user-attachments/assets/3766bba5-f9b2-469c-8c39-13ee21c3371c" />


---

### 🥱 Scenario 03: Alert Fatigue & High Noise (Tired Analysts)
* **Incident Summary:** L1 analysts were processing 760 alerts per shift, with 95% categorized as benign IT system noise or automation scripts, causing operational exhaustion.
* **Problematic Metric:** **False Positive Rate (FPR)** — High signal-to-noise ratio causing analyst burnout.
* **Remediation Plan:** Schedule a call with the team to implement a structured False Positive remediation process.
* **Task Owner:** Assigned detection rule schedule review and tuning to the dedicated SOC engineer.

| Scenario Context | Remediation Action Plan |
| :---: | :---: |
| ![Scenario 3 Prompt]

<img width="673" height="646" alt="3 1" src="https://github.com/user-attachments/assets/237318f2-1fc8-4ca7-a830-7270ab82d18c" />

| ![Scenario 3 Solution]

<img width="1024" height="889" alt="3 2 (1)" src="https://github.com/user-attachments/assets/933f4431-750a-4a1f-89b9-df866bc6e7f6" />


---

## 📈 Metric Optimization Summary Matrix

| Metric Category | Root Cause | Target KPI Impact | Remediation Action |
| :--- | :--- | :--- | :--- |
| **Time to Respond (TTR)** | Unstandardized credential reset and MFA revoke workflows | Reduce containment latency from hours to minutes | Draft Credential Rotation Workbook |
| **Time to Detect (TTD)** | Low-frequency SIEM scheduled detection queries | Cut detection lag from 20m down to 5m | Increase SIEM rule execution frequency |
| **False Positive Rate (FPR)** | High noise ratio from benign IT scripts and tools (95%) | Drastically lower alert load per shift | Implement False Positive Remediation Process |

---

## 🏆 Lab Completion

![SOC SLA Completion Badge]

<img width="1365" height="647" alt="4" src="https://github.com/user-attachments/assets/1f661dc9-4ea3-487b-8fc3-55a062cf8ab3" />
