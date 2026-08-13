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




# 🛡️ Cybersecurity Portfolio: Incident Response & Alert Triage
Platform: TryHackMe  
Status: 🎖️ Completed  
---
## 📊 Performance Summary
During this Security Operations Center (SOC) simulation lab, I investigated a queue of five high-priority security alerts involving network firewalls and corporate email systems. By analyzing domain infrastructure, network telemetry, and social engineering indicators, I successfully triaged every alert with perfect accuracy, mitigating active threats while minimizing alert fatigue.
---
## 🔍 Detailed Case Breakdowns
### 🚨 Case 1: Access to Blacklisted External URL (Firewall Alert)

| Attribute | Detail |
| :--- | :--- |
| Incident Classification | True Positive |
| Source Host | 10.20.2.17 |
| Destination Connection | 67.199.248.11 |
| Flagged Hyperlink | http://bit.ly/3sHkX3da12340 |
| Escalation Required | Yes |

* Analysis & Rationale: An internal workstation initiated an outbound connection targeting a known malicious infrastructure destination matching active threat intelligence blacklist feeds.
* Escalation Justification: The request involves direct interaction with a high-risk external link shortener (bit.ly). While the perimeter firewall successfully blocked the outbound traffic flow, tier-2 escalation is necessary to analyze the endpoint for potential local malware persistence or follow-up execution payloads.
* Remediation Actions: 
  1. Temporarily isolate the host machine at 10.20.2.17 from the local network segment.
  2. Execute a comprehensive endpoint antivirus/EDR scan.
  3. Clear local browser caches and coordinate quick security awareness guidance with the user.
* Attack Indicators: Threat intelligence blacklist signature match; URL shortener obfuscation.
---
### 🚨 Case 2: Suspicious External Link (Amazon Spoofing)

| Attribute | Detail |
| :--- | :--- |
| Incident Classification | True Positive |
| Target Recipient | h.harris@thetrydaily.thm |
| Malicious Sender | urgents@amazon.biz |
| Obfuscated Link | http://bit.ly/3sHkX3da12340 |
| Escalation Required | Yes |

* Analysis & Rationale: The inbound email exhibits standard characteristics of a brand-spoofing social engineering campaign. The adversary utilized an unauthorized top-level domain (.biz) to mimic a trusted delivery service, created artificial high urgency ("within 48 hours"), and leveraged an obfuscated bit.ly link to hide the final credential harvesting page.
* Escalation Justification: The malicious template successfully bypassed the corporate perimeter email filter to land directly in a user inbox. Escalation is mandatory to run a tenant-wide message trace and purge identical elements from other employee mailboxes.
* Remediation Actions: Deploy a permanent gateway block on the amazon.biz sender domain and run an active indicator check across proxy logs to ensure the link wasn't clicked prior to triage.
* Attack Indicators: Unauthorized sender TLD; delivery failure decoy theme; obfuscated redirection link.
---
### 🛡️ Case 3: Suspicious External Link (HR Onboarding - Alert 8818)

| Attribute | Detail |
| :--- | :--- |
| Incident Classification | False Positive |
| Target Recipient | j.garcia@thetrydaily.thm |
| Legitimate Sender | onboarding@hrconnex.thm |
| Verified URL | https://hrconnex.thm/onboarding/15400654060/j.garcia |
| Escalation Required | No |

* Analysis & Rationale: The system generated an alert on a legitimate, automated human resources notification sequence. Both the sender profile and the embedded registration links map directly to verified corporate partner domain infrastructure (hrconnex.thm). No external redirections or suspicious elements are present.
* Remediation Actions: Close the alert case as a benign False Positive. No further containment steps required.
---
### 🚨 Case 4: Suspicious External Link (Microsoft Typosquatting)
| Attribute | Detail |
| :--- | :--- |
| Incident Classification | True Positive |
| Target Recipient | c.allen@thetrydaily.thm |
| Malicious Sender | noreply@m1crosoftsupport.co |
| Harvesting URL | https://m1crosoftsupport.co/login |
| Escalation Required | Yes |

* Analysis & Rationale: This alert captures a severe, highly targeted credential harvesting vector. The malicious sender used a visible typosquatting technique (substituting the number 1 for the letter i in m1crosoft) and an unauthorized .co domain. The email utilized an "Unusual Sign-In Activity" panic decoy to force the user to click a fraudulent login panel.
* Escalation Justification: Because the email reached the inbox, urgent escalation is required to audit network logs and ensure the employee did not supply corporate credentials to the malicious site.
* Remediation Actions: Implement an immediate tenant-wide block on m1crosoftsupport.co, execute a search-and-destroy action to sweep the template from all corporate mailboxes, and enforce a proactive password reset for c.allen.
* Attack Indicators: Typosquatting domain structure; urgent security alert theme; malicious external login interface.
---
### 🛡️ Case 5: Suspicious External Link (HR Onboarding - Baseline Alert)

| Attribute | Detail |
| :--- | :--- |
| Incident Classification | False Positive |
| Target Recipient | Internal Corporate User |
| Legitimate Sender | onboarding@hrconnex.thm |
| Verified URL | https://hrconnex.thm/onboarding/... |
| Escalation Required | No |

* Analysis & Rationale: This baseline administrative event tracked standard profile setup messages. The email signatures, sender address routing, and hyperlinked destinations align perfectly with authorized internal environment white-lists, validating safe operations rather than an active compromise threat.
* Remediation Actions: Close the case in the SIEM dashboard as a False Positive. No further operational adjustments necessary.
---
## 🏆 Verified Credentials & Milestones
The following official platform milestone was successfully achieved upon final triage submission, confirming validation accuracy across the entire incident queue:

| Badge Achievement | Verification Objective | Performance Metric |
| :--- | :--- | :--- |
| 🏅 100% True Positive Rate | Flawless validation and escalation routing across all 5 operational cases. | 100% Accuracy Score |

> *Note: Verification milestone badge has been logged and archived alongside these technical documentation case logs.*

<img width="757" height="520" alt="3" src="https://github.com/user-attachments/assets/7b3fb539-0210-4af3-859f-d172ef705304" />



# 🛡️ Endpoint Detection & Response (EDR) Investigation Walkthrough

## 📌 Overview
This repository documents the practical incident response and threat analysis performed during the **Introduction to EDR Web App** lab. The objective was to utilize an EDR console to investigate endpoint telemetry, analyze process execution trees, identify indicators of compromise (IoCs), trace malware staging, detect credential dumping, and evaluate threat intelligence to differentiate true security incidents from benign internal tools.

---

## 🗂️ Case File Investigations

### 🔍 Case 01: Macro-Enabled Malware Staging (`DESKTOP-HR01`)
* **Target User / Host:** `alice.thomas` | `DESKTOP-HR01`
* **Timestamp:** Aug 4th, 2026 at 00:35
* **Severity:** High
* **Incident Analysis:**
  * A macro-enabled Office document (`invoice.docm`) was opened via Microsoft Word (`WINWORD.EXE`).
  * Word spawned `CMD.EXE`, which subsequently executed `cURL.EXE` to retrieve a payload from an external domain.
  * The downloaded file (`install.exe`) was written to disk at `C:\Users\Public\install.exe`.
  * The payload remained unexecuted on disk, indicating malware staging behavior.
* **Key Artifacts:**
  * **Downloader Tool:** `cURL.exe`
  * **Payload Absolute Path:** `C:\Users\Public\install.exe`
  * **Payload SHA256:** `9e107d9d372bbb6826bd81d3542a419d6eaf1e3f5b94fc3b1f69413c5c30ef2e5`

| Alert Overview | Process Chain & File Path |
| :---: | :---: |
| ![Case 1 Summary] <img width="663" height="645" alt="1 1" src="https://github.com/user-attachments/assets/f68ad522-07c6-439c-ba6b-183e1e6568b2" /> |
 | ![Case 1 Process Chain] <img width="1365" height="496" alt="1 2" src="https://github.com/user-attachments/assets/bc47c9f9-b31e-4e32-90f0-eea22fc3ac72" />
 |

---

### 🚨 Case 02: LSASS Credential Dumping & Data Exfiltration (`WIN-ENG-LAPTOP03`)
* **Target User / Host:** `haris.khan` | `WIN-ENG-LAPTOP03`
* **Timestamp:** Aug 3rd, 2026 at 23:56
* **Severity:** High
* **Incident Analysis:**
  * An unsigned binary named `syncsvc.exe` was executed from a temp directory.
  * The process accessed `lsass.exe` to attempt a memory dump for credential harvesting.
  * Persistence was configured via a Windows Registry Run Key (`HKCU\Software\Microsoft\Windows\CurrentVersion\Run\syncsvc`).
  * An attempt was made to exfiltrate the dumped memory payload (`dump_2025.dmp`) to an external file-sharing domain over HTTP, which was blocked by EDR controls.
* **Key Artifacts:**
  * **Suspicious Binary Path:** `C:\Users\haris.khan\AppData\Local\Temp\syncsvc.exe`
  * **Exfiltration URL:** `https://files-wetransfer.com/upload/session/ab12cd34ef56/dump_2025.dm`
  * **C2 / Exfiltration IP:** `100.42.28.64`

| Alert Overview | IoC Breakdown | Network & Registry Activity |
| :---: | :---: | :---: |
| ![Case 2 Summary]<img width="666" height="645" alt="2 1" src="https://github.com/user-attachments/assets/cdd00fa9-cd87-4dcf-aca6-f3897cecb26b" /> | ![Case 2 IoCs]<img width="1359" height="375" alt="2 2" src="https://github.com/user-attachments/assets/2e9e7092-9187-46b1-ae9c-cde5b38355b9" /> | ![Case 2 Network]<img width="1365" height="335" alt="2 3" src="https://github.com/user-attachments/assets/a8d2cd61-27cb-464b-bee1-ee817a153ca9" /> |

---

### ℹ️ Case 03: False Positive Analysis — Internal IT Utility (`DESKTOP-DEV01`)
* **Target User / Host:** `daniel.richards` | `DESKTOP-DEV01`
* **Timestamp:** Aug 3rd, 2026 at 23:27
* **Severity:** Medium
* **Incident Analysis:**
  * An unsigned binary `UpdateAgent.exe` located at `C:\Users\daniel.richards\AppData\Roaming\UpdateAgent.exe` initiated an outbound connection to an internal IP (`10.10.20.5:8080`).
  * Upon cross-referencing EDR Threat Intelligence, the binary was categorized as a **Known internal IT utility tool**.
  * *Verdict:* **False Positive** (Authorized internal IT software activity).

| Alert Overview | Threat Intel Assessment |
| :---: | :---: |
| ![Case 3 Summary]<img width="663" height="646" alt="3 1" src="https://github.com/user-attachments/assets/830f0b66-cc48-4b5e-a1cf-f3fdb7693edd" /> | ![Case 3 Details]<img width="1362" height="645" alt="3 2" src="https://github.com/user-attachments/assets/ef66a427-a6cc-4415-8a67-d12a6e8c4da9" /> |

---

## 📊 Summary Matrix

| Hostname | User | Severity | Detection Trigger | Primary Indicator / Artifact | Verdict |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `DESKTOP-HR01` | `alice.thomas` | High | Macro execution & cURL download | `C:\Users\Public\install.exe` | **True Positive** (Malware Staging) |
| `WIN-ENG-LAPTOP03` | `haris.khan` | High | LSASS memory access & exfil attempt | `https://files-wetransfer.com/...` | **True Positive** (Credential Dumping) |
| `DESKTOP-DEV01` | `daniel.richards` | Medium | Outbound HTTP from AppData folder | Threat Intel: *Known internal IT utility tool* | **False Positive** (Legitimate Tool) |

---

## 🏆 Completion

![EDR Web App Completion]<img width="1365" height="646" alt="4" src="https://github.com/user-attachments/assets/b1f54766-f3cc-4180-87ed-ba18b137da18" />




# TryHackMe: Intro to SIEM - Security Analysis & Incident Response Walkthrough

## Executive Summary
This repository documents the hands-on completion and investigation performed in the **Intro to SIEM** lab on TryHackMe. The objective of this lab is to understand Security Information and Event Management (SIEM) architecture, analyze centralized logs, triage automated detection alerts, investigate process execution events, and perform containment actions against unauthorized cryptomining activity.

---

## 🛠️ Tools & Technologies
* **Platform:** TryHackMe
* **Technology:** SIEM (Security Information & Event Management)
* **Log Types:** Windows Event Logs (`EventID 4688` - Process Creation)
* **Concepts:** Alert Triage, Threat Hunting, Detection Rules, Incident Response (Host Isolation), True/False Positive Analysis

---

## 🔍 Incident Investigation & Walkthrough

### 1. Alert Triage & Suspicious Process Detection
Upon triggering the simulated attack, the SIEM generated an alert indicating potential cryptomining activity on the network.

![SIEM Alert - CryptoMiner Activity Detected]<img width="1365" height="647" alt="1 1" src="https://github.com/user-attachments/assets/24f7b54a-d3c9-4fde-b9f7-a89d3c9a6755" />

* **Triggered Alert:** `Potential CryptoMiner Activity Observed`
* **Suspicious Process:** `cudominer.exe`

---

### 2. Event Log Analysis & Attribution
By pivoting to the central log repository, the execution logs were analyzed to trace the source user and endpoint responsible for executing the unauthorized application.

![Process Execution User Identification]<img width="1364" height="646" alt="1 2" src="https://github.com/user-attachments/assets/670593bb-9c51-426d-8d0c-caa575aa204a" />
![Hostname Identification]<img width="1364" height="647" alt="1 3" src="https://github.com/user-attachments/assets/c055b9ac-7071-42c4-b9d7-634b1a81e6a5" />

* **User Responsible:** `chris`
* **Full Process Path:** `C:\Users\Chris\temp\cudominer.exe`
* **Affected Hostname:** `HR_02`

---

### 3. Detection Rule Analysis
Examining the underlying SIEM detection logic revealed how the rule was triggered.

![SIEM Rule Logic Analysis]<img width="1365" height="565" alt="2 1" src="https://github.com/user-attachments/assets/016df476-97fe-48eb-898d-1a0c413406e0" />

* **Rule Query:** 
  `Alert "Potential CryptoMiner Activity" If EventID = 4688 AND Log_Source = WindowsEventLogs AND ProcessName = (*miner* OR *crypt*)`
* **Matched Term:** `miner` (matched via `*miner*` wildcard on `cudominer.exe`)

---

### 4. Incident Response & Host Containment
Based on the evidence collected, the alert was classified as a **True Positive**. Immediate containment action was taken through the SIEM platform to isolate the compromised workstation from the internal network.

![Incident Response Action Selection]<img width="1363" height="521" alt="2 2" src="https://github.com/user-attachments/assets/99cdc01b-0840-452e-b400-bf3042b81a68" />

* **Classification:** True Positive
* **Remediation Action:** Host Isolated (`HR_02`)

---

## 🏆 Lab Completion & Proof of Completion

### Task Progress
![Task Completion Overview]<img width="688" height="647" alt="3 1" src="https://github.com/user-attachments/assets/0d72b367-9d47-4822-9a5f-f5bd6618e8d5" />

### Room Completion Banner
![TryHackMe Room Completed]<img width="1365" height="644" alt="4" src="https://github.com/user-attachments/assets/ac7fd007-d173-4561-b52e-73b638e73592" />

---

## 💡 Key Takeaways
1. **SIEM Correlation Rules:** Simple wildcard string matching (e.g., `*miner*`) on process creation logs (`Event ID 4688`) can quickly flag unauthorized execution of tools like cryptominers.
2. **Contextual Investigation:** Identifying the process path (`C:\Users\Chris\temp\cudominer.exe`) and host (`HR_02`) provides the necessary context to determine intent and impact.
3. **Automated Response:** Modern SIEM environments allow analysts to take immediate containment steps—such as host isolation—directly within the alert workflow to limit lateral movement.




# TryHackMe: Splunk Basic Room Writeup

A comprehensive walkthrough covering log ingestion, index configuration, and Search Processing Language (SPL) queries executed in Splunk Enterprise during the Splunk: Basic room on TryHackMe.

---

## 📌 Room Details
* Platform: [TryHackMe](https://tryhackme.com/)
* Room: Splunk: Basic
* Category: SIEM / SOC Operations
* Skills Tested: Data Ingestion, Index Management, SPL Filtering, Data Analysis & Field Extraction

---

## 🛠️ Environment & Ingestion Setup

Before executing search queries, the target log file was ingested into Splunk Enterprise using the following steps:

1. **Target Environment:** AttackBox running Splunk Enterprise (v8.2.6)
2. **Log File Location:** `/root/Rooms/SplunkBasic/VPNlogs.json`
3. **Ingestion Workflow:**
   * Navigated to `Settings -> Add Data -> Upload`.
   * Selected `VPNlogs.json` from the local directory `/root/Rooms/SplunkBasic/`.
   * Set `sourcetype` to `_json` for proper key-value field parsing.
   * Created a new index named `vpn_logs`.
   * Reviewed input settings and finalized ingestion to start searching.

---

## 🔍 Task Walkthrough & Detailed SPL Investigations

### Task 1: Ingested Log Event Count
Question: Upload the data attached to this task and create an index "VPN_Logs". How many events are present in the log file?

* **SPL Query:** `index="vpn_logs"`
* **Answer:** `2862`
* **Detailed Explanation:** 
  After uploading `VPNlogs.json` to Splunk and storing it inside the `vpn_logs` index, executing a broad search across `index="vpn_logs"` with the time range set to All time returns every parsed log entry. Splunk calculates the total count directly above the timeline view, confirming that exactly 2,862 log events were successfully indexed from the raw JSON file.

![Task 1 - Total Ingested Events]<img width="1365" height="577" alt="1 1" src="https://github.com/user-attachments/assets/699e1adb-7e16-4b88-bbd2-36224d1d4b8b" />

---

### Task 2: User Activity Filtering
Question: How many log events are captured by the user Maleena?

* **SPL Query:** `index="vpn_logs" "Maleena"`
* **Answer:** `60`
* **Detailed Explanation:** 
  To isolate all VPN activities performed specifically by the user "Maleena", we execute a text-matching search filter on our index. Splunk scans the parsed `UserName` JSON fields and filters out all unrelated user activities, resulting in exactly 60 event logs tied to Maleena's connections and teardowns.

![Task 2 - User Maleena Events]<img width="1363" height="563" alt="1 2" src="https://github.com/user-attachments/assets/7d0bdf8a-281d-4bbd-bf53-1f65dc2cbde2" />

---

### Task 3: IP Address to Identity Correlation
Question: What is the username associated with IP 107.14.182.38?

* **SPL Query:** `index="vpn_logs" "107.14.182.38"`
* **Answer:** `Smith`
* **Detailed Explanation:** 
  In threat hunting and log analysis, correlating source IP addresses to specific user accounts is critical. By querying the target IP address `107.14.182.38` within the `vpn_logs` index, Splunk filters down the matching events. Expanding any event payload reveals the JSON field structure where `UserName` is explicitly mapped to Smith.

![Task 3 - IP and Username Correlation]<img width="1365" height="573" alt="1 3" src="https://github.com/user-attachments/assets/53814ac4-6fae-4818-ab22-22a9c67f520a" />

---

### Task 4: Country Exclusion Search (Boolean NOT / !=)
Question: What is the number of events that originated from all countries except France?

* **SPL Query:** `index="vpn_logs" Source_Country!="France"`
* **Answer:** `2814`
* **Detailed Explanation:** 
  To filter out geographical noise or isolate non-domestic traffic, we utilize Splunk's relational exclusion operator (`!=`). The field `Source_Country` is evaluated, and any log entry where the country equals "France" is excluded from the query results. Out of the 2,862 total events, subtracting France's events leaves exactly 2,814 events originating from all other countries.

![Task 4 - Non-France Events Count]<img width="1365" height="515" alt="1 4" src="https://github.com/user-attachments/assets/9811bc2c-c0af-4d3f-af87-2301526b7d02" />

---

### Task 5: Specific IP Activity Tracking
Question: How many VPN events were associated with the IP 107.3.206.58?

* **SPL Query:** `index="vpn_logs" Source_ip="107.3.206.58"`
* **Answer:** `14`
* **Detailed Explanation:** 
  To determine the frequency of network traffic originating from a specific endpoint, we query the extracted field `Source_ip` directly against `107.3.206.58`. Splunk executes an exact field match search and aggregates the events, returning a total event count of 14 for this IP address.

![Task 5 - Specific IP Events Count]<img width="1365" height="572" alt="1 5" src="https://github.com/user-attachments/assets/af3efbc2-8cd7-4173-bc6d-6b4ade54bf49" />

---

## 🎉 Room Completion

All investigative tasks were answered correctly and verified on TryHackMe.

![TryHackMe Room Completed]<img width="1365" height="645" alt="2" src="https://github.com/user-attachments/assets/565974dc-39bb-4d1b-a87a-2513f7c41039" />





# ⚡ TryHackMe Writeup: Kibana — Data Visualization & Threat Hunting 🛡️

> Author: Kavindu  
> Target System: Elastic Stack (Kibana Discover & Kibana Lens)  
> Focus Area: Threat Hunting, Log Analysis, KQL Queries & SOC Dashboard Building  

---

## 📌 Executive Summary
This repository contains a comprehensive walk-through and investigation report for the TryHackMe: Kibana lab. The objective was to analyze raw VPN connection logs, isolate malicious activity, trace compromised/unauthorized accounts, and build dedicated Security Operations Center (SOC) visualizations and monitoring dashboards.

---

## 🔍 Part 1: Log Exploration & Field Filtering

### 1. Initial Overview of VPN Logs
Analyzed baseline VPN telemetry to determine general connection patterns and baseline activity.
* Total Records Analyzed: 2,861 hits
* Observation: Steady volume of connections with noticeable periodic spikes.

![Baseline VPN Logs]<img width="1363" height="646" alt="1 1" src="https://github.com/user-attachments/assets/7cb30ae2-77dc-4a67-9c77-3155bb864b39" />

---

### 2. Identifying Top Source IP Addresses
Inspected network parameters to isolate top talking external endpoints.
* Top Originating IP: 238.163.231.224 (Accounting for 3.2% of overall traffic)

![Top Source IPs]<img width="1365" height="645" alt="1 2" src="https://github.com/user-attachments/assets/fddca3ed-9a26-4bd6-8a89-0b304f3af6e1" />

---

### 3. User Investigation — Emanda
Filtered logs specifically targeting user Emanda to evaluate authentication behavior and network origins.
* Filter: UserName : Emanda
* Total Volume: 56 hits

![Emanda Logs]<img width="1364" height="646" alt="1 3" src="https://github.com/user-attachments/assets/30e62ee3-1638-4e09-b6f2-91847e59b540" />

* Source IP Distribution:
  * 107.14.1.247 — 53.6%
  * 107.14.4.82 — 46.4%

![Emanda Source IPs]<img width="1365" height="643" alt="1 4" src="https://github.com/user-attachments/assets/224ba08e-7bab-4135-bf66-1770b006bc15" />

---

### 4. Anomaly Investigation — January 11, 2022
Detected and investigated a severe anomaly (traffic surge) on January 11, 2022.
* Date Filter: Jan 11, 2022 @ 00:00:00 ➔ Jan 11, 2022 @ 23:59:59
* Total Hits: 283 hits
* Primary Offender: 172.201.60.191 (Responsible for 97.2% of total connections)

![Jan 11 Surge]<img width="1365" height="647" alt="1 5" src="https://github.com/user-attachments/assets/18ce28cd-4478-4d4a-854f-02acdd93b694" />
![Jan 11 Source IP]<img width="1364" height="646" alt="1 6" src="https://github.com/user-attachments/assets/112e21b0-4655-48a7-b8ea-4e2e942cb4c8" />

---

### 5. Multi-Filter Analysis — New York Geographic Tracking
Correlated geolocation and IP telemetry to track connections from New York via IP 238.163.231.224.
* Total Matching Events: 48 hits
* Target Account: Rafique M

![New York Filters]<img width="1365" height="645" alt="1 7" src="https://github.com/user-attachments/assets/94775c98-5979-4023-ba89-27d4d7d9b8ee" />

---

### 6. Customized Field View Setup
Configured a clean tabular view isolating high-value SOC fields: @timestamp, Source_ip, UserName, and Source_Country.

![Custom Log Table]<img width="1364" height="644" alt="1 8" src="https://github.com/user-attachments/assets/9a19f238-5583-44d8-88d0-495e0b8de594" />

---

## 🎯 Part 2: Kibana Query Language (KQL) Investigations

### 1. Compound Logic Search
Constructed a boolean KQL expression targeting US-originating traffic for users James or Albert.

* KQL Query: Source_Country : "United States" AND UserName : James OR Albert
* Total Resulting Hits: 161
* Outcome: Successfully isolated relevant targeted connection traffic.

![Compound KQL Search]<img width="1365" height="646" alt="2 1" src="https://github.com/user-attachments/assets/fe0055bf-ab87-43c3-b8f6-d08156c94291" />

---

### 2. Terminated Employee Access Audit (Johny Brown)
Cross-referenced offboarding records against active VPN connections. User Johny Brown was terminated on January 1, 2022.

* KQL Query: UserName : Johny Brown
* Post-Termination Traffic: 1 connection detected on Jan 7, 2022 @ 07:58:47.
* Verdict: 🚨 True Positive (Potential rogue access or unrevoked VPN credentials post-offboarding).

![Johny Brown Investigation]<img width="1365" height="646" alt="2 2" src="https://github.com/user-attachments/assets/1b6fde2e-bd5c-4b5b-bbf7-117e8ad2db4c" />

---

## 📊 Part 3: Visualizations & SOC Dashboarding

### 1. Failed Logon Aggregation Table
Built a dedicated Kibana Lens table visualization aggregating failed authentication attempts.
* Filter: action: failed
* Columns: UserName | Source_ip | Count of records
* Key Finding: User Simon logged 274 failed attempts from IP 172.201.60.191 (Strong indicator of a brute-force attack).

![Failed Logon Visualization]<img width="1365" height="645" alt="3 1" src="https://github.com/user-attachments/assets/294a7dc4-62d8-4dc7-accf-37cf1336f4aa" />

---

### 2. Centralized SOC Monitoring Dashboard
Combined custom metrics, charts, and tables into a real-time Elastic Dashboard for active threat monitoring.

![Custom Elastic Dashboard]<img width="1365" height="647" alt="4 1" src="https://github.com/user-attachments/assets/43d56e83-48a4-4a44-9033-9d17d0fb7020" />

---

## 🏁 Completion Summary
* Lab Status: ✅ 100% Completed
* Core Competencies: KQL Syntax, Log Filtering, Anomaly Identification, Insider Threat Detection, SOC Dashboard Engineering.

![Room Completion]<img width="1365" height="646" alt="5" src="https://github.com/user-attachments/assets/1c3c45dc-e424-4b87-b3a8-c76dada6a19f" />




# TryHackMe: Introduction to SOAR — Room Writeup

A comprehensive guide and Security Operations Center (SOC) analysis covering Security Orchestration, Automation, and Response (SOAR) workflow design, playbook configuration, and human-in-the-loop automation balancing on TryHackMe.

---

## 📌 Room Overview
* **Platform:** [TryHackMe](https://tryhackme.com/)
* **Room:** Introduction to SOAR
* **Category:** SOC Operations / Security Engineering
* **Skills Tested:** Playbook Design, SOAR Workflow Automation, Incident Response Orchestration, Human-in-the-Loop Validation

---

## ⚙️ SOAR Workflow Configuration Matrix

| Workflow Category | Action Item | Mode | Rationale |
| :--- | :--- | :--- | :--- |
| **Case Management** | Create Case Ticket | **Automated** | Instantly index incoming alerts into ticketing platforms (TheHive, ServiceNow). |
| **Case Management** | Assign Case Ticket | **Automated** | Route tickets to available analysts or tiered queues based on severity. |
| **Case Management** | Communicate Case Ticket | **Automated** | Dispatch real-time notification alerts across Slack, Email, or Teams channels. |
| **Case Management** | Update Case Ticket | **Automated** | Sync case status and dynamic enrichment data via REST APIs automatically. |
| **Case Management** | Delete Case Ticket | **Automated** | Automatically purge or archive resolved/false-positive test tickets. |
| **Threat Intelligence** | Fetch New Incident Alerts | **Automated** | Pull new telemetry continuously from threat feed integrations. |
| **Threat Intelligence** | Set Fetch Intervals | **Automated** | Maintain scheduled API query intervals without manual triggering. |
| **Threat Intelligence** | Failed Fetch Notifications | **Automated** | Alert SOC team instantly if threat feed API connectors go offline. |
| **Threat Intelligence** | Discard Old Alerts | **Manual** | Require human review before permanently purging stale threat intelligence data. |
| **Data Extraction** | Extract Domains | **Automated** | Parse domain IOCs from raw alert payloads for lookup against VirusTotal. |
| **Data Extraction** | Extract URLs | **Automated** | Extract malicious URLs automatically for automated enrichment. |
| **Data Extraction** | Extract IPs | **Automated** | Isolate source/destination IP addresses for automated reputation scoring. |
| **Data Extraction** | Analyst Extraction | **Manual** | Reserve manual extraction for unknown, obfuscated, or custom protocol payloads. |
| **Reputation Checks** | Reputation Results Output | **Automated** | Compile reputation scores automatically from VirusTotal and threat feeds. |
| **Reputation Checks** | Sandbox Testing | **Manual** | Require analyst verification before executing untrusted files in ANY.RUN/Hybrid-Analysis. |
| **Reputation Checks** | Analyst Validation | **Manual** | Human tier-2 analyst confirms malicious intent before taking destructive action. |
| **Course of Action** | Block Domains | **Automated** | Push domain blacklist rules directly to firewalls upon approved mitigation. |
| **Course of Action** | Block IPs | **Automated** | Execute IP blocking on network perimeter devices via automated scripts. |
| **Course of Action** | Block URLs | **Automated** | Update secure web gateway (SWG) filtering rules automatically. |
| **Course of Action** | Update Case Tickets | **Automated** | Log remediation actions and update ticket state upon execution. |
| **Course of Action** | Analyst Approve COA | **Manual** | Require explicit analyst approval prior to executing containment/blocking actions. |

---

## 🔍 Step-by-Step Lab Breakdown

### 1. SOAR Interactive Dashboard Navigation
The interactive environment consists of 5 core investigation modules that make up a complete Incident Response (IR) automated pipeline:
1. Case Ticket Management
2. Threat Intelligence Feeds
3. Incident Data Extraction
4. Reputation Checks
5. Course of Action (COA)

![SOAR Interactive Dashboard]<img width="643" height="646" alt="1 1" src="https://github.com/user-attachments/assets/8bc6be3b-7a27-43d8-802e-e712fa3ca165" />

---

### 2. Module 1: Case Management Settings
* **Troubleshooting Note:** Setting `Delete Case Ticket` to Manual causes an environment pipeline error (`Error: Case Ticket setting is incorrect.`). To establish proper SOAR case lifecycle automation, all case management operations (Create, Assign, Communicate, Update, and Delete) must be enabled as **Automated**.

![Case Management Settings]<img width="609" height="420" alt="1 2" src="https://github.com/user-attachments/assets/64d6f710-a5b2-46ff-9b65-4b5d0e2ef6e3" />

---

### 3. Module 2: Threat Intelligence Feeds
* **Automation Scope:** Automatic ingestion of incident alerts, scheduled API polling intervals, and automated failure notifications.
* **Manual Control:** Discarding old alerts is assigned to **Manual** review to prevent accidental deletion of threat logs needed for historical hunting.

![Threat Intelligence Feeds Settings]<img width="605" height="334" alt="1 3" src="https://github.com/user-attachments/assets/8471fe8f-7f2f-4de0-912f-e691253a87ec" />

---

### 4. Module 3: Incident Data Extraction
* **Automation Scope:** Automated parsing and regex extraction of Domains, URLs, and IPv4/v6 addresses from alert payloads.
* **Manual Control:** Analyst extraction remains **Manual** for non-standard payloads or zero-day obfuscation patterns.

![Incident Data Extraction Settings]<img width="611" height="340" alt="1 4" src="https://github.com/user-attachments/assets/b5245322-e30f-496b-93f5-379be5b2ef4d" />

---

### 5. Module 4: Reputation Checks
* **Automation Scope:** Output compilation of threat intelligence scores from platforms like VirusTotal.
* **Manual Control:** Sandbox detonate execution (ANY.RUN / Hybrid Analysis) and final case validation are set to **Manual** to avoid false-positive detonations and overhead.

![Reputation Checks Settings]<img width="609" height="340" alt="1 5" src="https://github.com/user-attachments/assets/541231f4-90d1-4f48-8083-4a7efc71067a" />
---

### 6. Module 5: Course of Action (COA) / Containment
* **Automation Scope:** Automated deployment of firewall and web proxy rules (Block Domains, Block IPs, Block URLs) and ticket updating.
* **Human-in-the-Loop Safeguard:** `Analyst Approve COA` is enforced as **Manual**, ensuring a human analyst authorizes all blocking actions before perimeter firewalls execute containment commands.

![Course of Action Settings]<img width="607" height="425" alt="1 6" src="https://github.com/user-attachments/assets/ef5d4eb0-feee-45f6-ae6d-465d4d0473dd" />
---

## 🎉 Room Completion

After configuring all 5 SOAR settings blocks with the correct blend of automated playbooks and human analyst intervention safeguards, the workflow engine validates successfully.

![TryHackMe Room Completed Screen]<img width="1365" height="646" alt="2" src="https://github.com/user-attachments/assets/757957fa-91d6-4420-9d05-376387720551" />




# TryHackMe: Pyramid of Pain — Room Writeup

A practical guide and Cyber Threat Intelligence (CTI) writeup on analyzing Indicators of Compromise (IOCs), threat attribution, and dynamic sandbox malware analysis using the **Pyramid of Pain** framework on TryHackMe.

---

## 📌 Room Overview
* **Platform:** [TryHackMe](https://tryhackme.com/)
* **Room:** Pyramid of Pain
* **Category:** Cyber Threat Intelligence (CTI) / Blue Team
* **Skills Tested:** IOC Categorization, ANY.RUN Dynamic Malware Analysis, MITRE ATT&CK Mapping, REvil/Sodinokibi Ransomware Analysis

---

## 🔺 The Pyramid of Pain Breakdown

The Pyramid of Pain (conceptualized by David J Bianco) illustrates how difficult it is for an adversary to alter their indicators of compromise (IOCs) when detected by security analysts.

| Level | Indicator Type | Relative Pain Level | SOC / Defender Impact & Description |
| :--- | :--- | :--- | :--- |
| **1 (Base)** | **Hash Values** | Trivial | SHA-256, SHA-1, or MD5 file signatures. Easy to calculate and block, but trivial for attackers to change via single-byte modification. |
| **2** | **IP Addresses** | Easy | Network infrastructure endpoints. Blocking IPs provides quick relief, but attackers easily switch to new proxies, VPNs, or cloud nodes. |
| **3** | **Domain Names** | Simple / Moderate | Domain infrastructure used in typo-squatting or phishing. Slightly harder to replace due to domain registration and DNS setup costs. |
| **4** | **Network & Host Artifacts** | Annoying | Distinctive indicators left by malicious tools (e.g., custom User-Agent strings, specific registry keys, ransom notes, URI patterns). |
| **5** | **Tools** | Challenging | Software utilities employed by threat actors (e.g., Cobalt Strike, Mimikatz, vssadmin scripts). Tool replacement forces attackers to rewrite software. |
| **6 (Peak)** | **TTPs** | Tough! | Tactics, Techniques, and Procedures (MITRE ATT&CK framework). Disrupting TTPs forces attackers to re-engineer their entire operational methodology. |

---

## 🔍 Practical Analysis & Threat Investigation

### 1. ANY.RUN Dynamic Sandbox Analysis (REvil / Sodinokibi Ransomware)
During the practical investigation, a binary (`some_malicious_file.bin.exe`) was executed within an ANY.RUN dynamic analysis sandbox to observe runtime behavior and extract IOCs across the Pyramid levels.

* **Sample Name:** `some_malicious_file.bin.exe`
* **File MD5:** `890A58F200DFFF23165DF9E1B088E58F`
* **Threat Family:** REvil / Sodinokibi Ransomware
* **Threat Score:** `100 / 100` (Malicious)

![ANY.RUN Execution Tree]

<img width="1362" height="646" alt="1 1" src="https://github.com/user-attachments/assets/2f303cbb-5812-4723-99f6-bf1dc27bad2a" />

#### Execution Process Hierarchy & Commands:
1. `some_malicious_file.bin.exe` (PID 2256) spawns process instance PID 1632.
2. PID 1632 executes command shell subprocess:
   ```cmd
   cmd.exe /c vssadmin.exe Delete Shadows /All /Quiet & bcdedit /set {default} recoveryenabled No & bcdedit /set {default} bootstatuspolicy ignoreallfailures
   ```
3. `vssadmin.exe Delete Shadows /All /Quiet` — Purges Volume Shadow Copies to block system restore capabilities.
4. `bcdedit.exe /set {default} recoveryenabled No` — Disables automated Windows startup recovery.
5. `bcdedit.exe /set {default} bootstatuspolicy ignoreallfailures` — Forces system to bypass boot errors automatically.

---

### 2. Extracted IOCs & Network Telemetry

![ANY.RUN DNS Ingestion & Threat Score]

<img width="1365" height="646" alt="1 2" src="https://github.com/user-attachments/assets/30012fd9-cf7f-44ff-8cae-9a617a3a9b93" />

* **Ransom Artifact:** File encrypted notification generated on victim desktop: `Find 9m32i-readme.txt and follow instuctions`.
* **DNS Query Requests & Resolved IPs:**
  * `craftingalegacy.com` ➔ `50.87.136.52`
  * `g2mediainc.com` ➔ `78.46.1.42`
  * `brinkdoepke.eu` ➔ `134.119.253.108`
  * `vipcarrental.ae` ➔ `104.21.87.185` / `172.67.145.154`
* **MITRE ATT&CK Technique Mapping:**
  * **T1486 (Data Encrypted for Impact):** Ransomware encrypted host files and generated ransom instructions.
  * **T1490 (Inhibit System Recovery):** Deletion of shadow copies via `vssadmin` and modification of `bcdedit` boot configurations.

---

### 3. Concept Mapping & Hierarchy Completion

![Pyramid of Pain Concept Mapping]

<img width="666" height="643" alt="2 3" src="https://github.com/user-attachments/assets/05ec1c86-79c7-4e64-91a5-ba70cb321321" />

![Pyramid of Pain Full Hierarchy]

<img width="667" height="647" alt="2 4" src="https://github.com/user-attachments/assets/88b23d5f-8a19-4009-acf5-c96f7543ed17" />

---

## 🎉 Room Completion

All 10 tasks completed successfully on TryHackMe.

![TryHackMe Room Completed Screen]<img width="1363" height="645" alt="3" src="https://github.com/user-attachments/assets/bd9926e3-da97-440c-bf4a-0e305df99396" />




# TryHackMe: Cyber Kill Chain — Room Writeup

A comprehensive guide and Security Operations Center (SOC) breakdown analyzing the Lockheed Martin **Cyber Kill Chain** framework, attack stage mapping, and practical threat scenario reconstruction on TryHackMe.

---

## 📌 Room Overview
* **Platform:** [TryHackMe](https://tryhackme.com/)
* **Room:** Cyber Kill Chain
* **Category:** Cyber Threat Intelligence (CTI) / Security Operations
* **Skills Tested:** Lockheed Martin Cyber Kill Chain Mapping, Intrusion Lifecycle Analysis, Threat Scenario Reconstruction, Defense-in-Depth Strategy

---

## 🎯 Cyber Kill Chain Phase Mapping Matrix

The Lockheed Martin Cyber Kill Chain model outlines seven distinct stages of an adversary intrusion. The table below details how real-world attack vectors map to each phase in the practical scenario:

| Kill Chain Stage | Icon Indicator | Scenario Action Item | Stage Description & Defensive Focus |
| :--- | :--- | :--- | :--- |
| **1. Reconnaissance** | Radar | *Information Gathering* | Adversaries harvest target OSINT, email lists, domain topology, and vulnerable endpoints. |
| **2. Weaponization** | Bug / Malicious Code | **powershell** | Coupling malicious payloads with exploits (e.g., weaponizing PowerShell scripts or office macros). |
| **3. Delivery** | Sealed Package | **spearphishing attachment** | Transmitting the weaponized payload to the target (e.g., via targeted emails or infected USBs). |
| **4. Exploitation** | Target Laptop | **exploit public-facing application** | Triggering the malicious code by exploiting software vulnerabilities or web applicaton flaws. |
| **5. Installation** | Unpacked Box / Arrow | **dynamic linker hijacking** | Establishing persistence on the host system (e.g., dynamic link library hijacking, scheduled tasks, web shells). |
| **6. Command & Control** | Megaphone | **fallback channels** | Establishing a covert communication channel back to attacker infrastructure (e.g., C2 backup channels, DNS tunneling). |
| **7. Actions on Objectives** | Bullseye / Target | **data from local system** | Executing the primary goal (e.g., exfiltrating local host data, ransomware encryption, lateral movement). |

---

## 🔍 Practical Scenario Analysis

### 1. Kill Chain Lifecycle Framework
Understanding the intrusion lifecycle enables security teams to implement **Defense-in-Depth** controls at each layer, breaking the chain before adversaries reach their final objectives.

![Cyber Kill Chain Interactive Diagram]

<img width="674" height="647" alt="1 1" src="https://github.com/user-attachments/assets/6895d463-ad54-4306-84f4-ae2b46408a6c" />

---

### 2. Practical Attack Reconstruction
In the practical exercise, threat vectors were categorized across the 6 active scenario stages to trace the adversary path from weaponization through post-exploitation exfiltration:

* **Weaponization:** `powershell` — Payload created to execute malicious memory-resident scripts.
* **Delivery:** `spearphishing attachment` — Initial access vector used to deliver the payload directly to internal end-users.
* **Exploitation:** `exploit public-facing application` — Triggering unpatched application flaws on exposed network infrastructure.
* **Installation:** `dynamic linker hijacking` — Achieving system persistence by replacing legitimate shared libraries with malicious binaries.
* **Command & Control:** `fallback channels` — Maintaining robust operational control through redundant C2 communication channels.
* **Actions on Objectives:** `data from local system` — Harvesting and exfiltrating target host data.

![Cyber Kill Chain Scenario Mapping]

<img width="1365" height="646" alt="1 2" src="https://github.com/user-attachments/assets/ccbb72ca-2e51-4bff-9eb6-1f528bdee9a5" />

---

## 🎉 Room Completion

All tasks completed successfully on TryHackMe.

![TryHackMe Room Completed Screen]

<img width="1365" height="647" alt="3" src="https://github.com/user-attachments/assets/33bd6d7c-f9ae-4da2-98ab-4f954933f7d2" />




# TryHackMe: Unified Kill Chain — Room Writeup

A comprehensive guide and Security Operations Center (SOC) breakdown analyzing Paul Pols' **Unified Kill Chain (UKC)** framework, attack phase mapping, and practical threat scenario alignment on TryHackMe.

---

## 📌 Room Overview
* **Platform:** [TryHackMe](https://tryhackme.com/)
* **Room:** Unified Kill Chain
* **Category:** Cyber Threat Intelligence (CTI) / Security Operations
* **Skills Tested:** Unified Kill Chain Mapping, Threat Modeling, TTP Identification, Adversary Lifecycle Analysis

---

## 🧭 Unified Kill Chain (UKC) Framework Overview

The Unified Kill Chain unifies the **Lockheed Martin Cyber Kill Chain** and **MITRE ATT&CK** into an 18-stage framework categorized under three primary tactical goals:

```text
       ┌─────────────────────────────────────────────────────────┐
       │                 THE UNIFIED KILL CHAIN                  │
       └────────────────────────────┬────────────────────────────┘
                                    │
         ┌──────────────────────────┼──────────────────────────┐
         ▼                          ▼                          ▼
   ┌───────────┐             ┌─────────────┐            ┌─────────────┐
   │  GOAL 1:  │             │   GOAL 2:   │            │   GOAL 3:   │
   │    IN     │ ──────────► │   THROUGH   │ ─────────► │     OUT     │
   │ (Initial  │             │  (Network   │            │ (Action on  │
   │ Foothold) │             │Propagation) │            │ Objectives) │
   └───────────┘             └─────────────┘            └─────────────┘
```

| UKC Goal Category | Focus Area | Key Tactical Phases Included |
| :--- | :--- | :--- |
| **Goal 1: In** | Initial Access & Foothold | Reconnaissance, Weaponization, Delivery, Social Engineering, Exploitation, Persistence |
| **Goal 2: Through** | Network Propagation & Escalation | Defense Evasion, Command & Control (C2), Pivoting, Privilege Escalation, Lateral Movement |
| **Goal 3: Out** | Action on Objectives | Target Identification, Exfiltration, Data Encrypting, Impact / Monetization |

---

## 🔍 Practical Phase Scenario Matching

During the practical assessment, adversary actions were evaluated and mapped to their corresponding phase within the Unified Kill Chain:

| Scenario Action Description | Correct UKC Phase | UKC Goal Category | Key Defensive Verification |
| :--- | :--- | :--- | :--- |
| **"The Attacker uses tools to gather information about a system"** | **Reconnaissance** | Goal 1: In | Active/Passive scanning and OSINT gathering prior to initial delivery. |
| **"The Attacker installs a malicious script to allow them remote access at a later date"** | **Persistence** | Goal 1: In | Maintaining host presence across system reboots and credential changes. |
| **"The hacked machine is being controlled from an Attacker's own server"** | **Command and Control** | Goal 2: Through | Establishing active beaconing channels back to C2 infrastructure. |
| **"The Attacker uses the hacked machine to access other servers on the same network"** | **Pivoting** | Goal 2: Through | Leveraging an internal compromised host to traverse network segments. |
| **"The Attacker steals a database and sells this to a 3rd party"** | **Action and Objectives** | Goal 3: Out | Fulfilling ultimate operational goals (Exfiltration, Impact, and Monetization). |

---

## 📸 Lab Screenshots & Verification

### 1. Phase Mapping Scenarios

![Reconnaissance Phase Mapping]<img width="665" height="645" alt="1 1" src="https://github.com/user-attachments/assets/49b42f71-6fac-4bc1-a19d-02cb2800de65" />
![Persistence Phase Mapping]<img width="668" height="646" alt="1 2" src="https://github.com/user-attachments/assets/1a54cd8e-2c2f-4f58-90bd-89a7e6d6470b" />
![Command and Control Phase Mapping]<img width="666" height="644" alt="1 3" src="https://github.com/user-attachments/assets/b172e6e3-3e22-4914-8ec4-baae7dc8e528" />
![Pivoting Phase Mapping]<img width="665" height="645" alt="1 4" src="https://github.com/user-attachments/assets/6fcb6c3c-8adb-483c-9fef-bcac932f81f7" />
![Action on Objectives Phase Mapping]<img width="668" height="645" alt="1 5" src="https://github.com/user-attachments/assets/108b8925-1d8e-4018-9194-91a6e353df93" />

---

### 2. Task Progress & Room Completion

All 9 tasks completed successfully on TryHackMe.

![TryHackMe Task Completion List]<img width="1365" height="606" alt="1 6" src="https://github.com/user-attachments/assets/efcf89e1-a80d-46c4-889b-56c031a4e7fd" />
![TryHackMe Room Completed Screen]<img width="1365" height="647" alt="2" src="https://github.com/user-attachments/assets/25e6ad68-c703-477c-b9ee-7e941f32c95a" />




# TryHackMe: MITRE — Room Writeup

A comprehensive walkthrough and Security Operations Center (SOC) breakdown analyzing the **MITRE** room on TryHackMe, covering threat actor profiling, analytics repositories, defensive countermeasure matrices, and emerging technology frameworks.

---

## 📌 Room Overview
* **Platform:** [TryHackMe](https://tryhackme.com/)
* **Room:** MITRE
* **Category:** Cyber Threat Intelligence (CTI) / Threat Hunting / Defensive Engineering
* **User:** kaviboy
* **Tasks Completed:** 8 / 8
* **Skills Tested:** Threat Actor Profiling (ATT&CK), Operational Detection Rules (CAR), Countermeasure Mapping (D3FEND), Emerging Domain Security (AADAPT & ATLAS).

---

## 🧭 Key Frameworks & Knowledge Domains

### 1. MITRE ATT&CK® Framework & Threat Intelligence
* **Adversary Profiling:** Evaluated threat actor profiles such as **Mustang Panda (G0129)**, analyzing associated aliases (TA416, RedDelta, BRONZE PRESIDENT, STALEY TAURUS, etc.) and targeted industries across diplomatic, non-governmental, and research entities.
* **ATT&CK Navigator:** Utilized ATT&CK Navigator layers to visualize attack paths spanning Reconnaissance, Initial Access (*Spearphishing Link/Attachment*), Execution (*PowerShell, Command Interpreter*), and Persistence (*Registry Run Keys / Autostart*).

### 2. MITRE Cyber Analytics Repository (CAR)
* Examined detection-focused analytics designed to identify specific adversary TTPs in host telemetry.
* **Featured Analytic:** `CAR-2020-09-001: Scheduled Task - FileAccess` — detection mechanism for Windows Task Scheduler persistence and execution via creation/modification of files in `C:\Windows\Tasks` or `C:\Windows\System32\Tasks`.

### 3. MITRE D3FEND™ Framework
* Navigated the defensive countermeasure knowledge graph to align defensive capabilities against offensive ATT&CK techniques.
* **Featured Countermeasure:** `D3-UBA (User Behavior Analysis)` — leveraging statistical algorithms and anomaly detection to identify malicious insider behavior and unexpected activity patterns.

### 4. Specialized & Emerging MITRE Frameworks
* **MITRE AADAPT™:** Evaluated specialized threat vectors targeting modern technology stacks (`ADT3025: Scrape Blockchain Data` under Collection tactic).
* **MITRE ATLAS™:** Analyzed threat intelligence matrices for Artificial Intelligence and Machine Learning assets (`AML.T0068: LLM Prompt Obfuscation` under Defense Evasion).

---

## 🔍 Practical Lab Breakdown

| Task | Topic | Key Focus & Reference Material |
| :--- | :--- | :--- |
| **Task 1** | Introduction | Overview of MITRE ecosystem resources |
| **Task 2** | ATT&CK® Framework | Tactics, Techniques, Sub-techniques, and Matrices |
| **Task 3** | ATT&CK in Operation | Real-world threat scenario mapping & ATT&CK Navigator |
| **Task 4** | ATT&CK for Threat Intelligence | Threat Actor profiling (Mustang Panda / G0129) |
| **Task 5** | Cyber Analytics Repository (CAR) | Threat detection rules & analytic coverage (`CAR-2020-09-001`) |
| **Task 6** | MITRE D3FEND Framework | Countermeasure Knowledge Graph (`D3-UBA`) |
| **Task 7** | Other MITRE Projects | Emerging matrices: MITRE AADAPT (`ADT3025`) & MITRE ATLAS (`AML.T0068`) |
| **Task 8** | Conclusion | Practical summary and learning path integration |

---

## 📸 Lab Evidence & Verification

### Threat Intelligence & ATT&CK Mapping
![Mustang Panda Profile]<img width="1365" height="646" alt="1 1" src="https://github.com/user-attachments/assets/7379dcf2-9669-4d03-a1a4-a3bcbcaed7f5" />
![ATT&CK Navigator Layer]<img width="1365" height="645" alt="1 2" src="https://github.com/user-attachments/assets/2e615a74-228c-4090-9cab-172747d28aaf" />
![MITRE ATT&CK Groups]<img width="1365" height="646" alt="1 3" src="https://github.com/user-attachments/assets/1151c3e6-2d39-46e2-b3f7-c76ad05a3df1" />
### Cyber Analytics & Defensive Countermeasures
![CAR Scheduled Task Analytic]<img width="1365" height="647" alt="1 4" src="https://github.com/user-attachments/assets/5c522c60-d854-4cf2-a788-9a8d1ed3bd6f" />
![D3FEND User Behavior Analysis]<img width="1365" height="646" alt="1 5" src="https://github.com/user-attachments/assets/e014736f-a8ba-44e0-ba5a-18c79341b840" />

![D3FEND Countermeasure Matrix]
### Specialized & Emerging Frameworks
![MITRE AADAPT Blockchain Scraping]<img width="1365" height="645" alt="1 7" src="https://github.com/user-attachments/assets/c643d0b7-1c6e-4624-ab72-7e385f2b92ea" />
![MITRE ATLAS LLM Prompt Obfuscation]<img width="1365" height="646" alt="1 8" src="https://github.com/user-attachments/assets/26c1ec5c-0945-4a67-84af-33c87b72ffff" />

### Room Progress & Completion
![TryHackMe Task List]<img width="1365" height="646" alt="2" src="https://github.com/user-attachments/assets/c68eae00-58b3-4c01-b2ba-7b57ac8ca057" />
![TryHackMe Room Completed]<img width="1365" height="647" alt="3" src="https://github.com/user-attachments/assets/2ce0003b-25c2-4219-aa79-2de37133b67c" />





# TryHackMe: Summit — Complete Writeup & Defense Guide

## 📌 Room Metadata
* **Platform:** [TryHackMe](https://tryhackme.com/)
* **Room Name:** Summit
* **Category:** Defensive Security / Threat Hunting / Detection Engineering
* **User:** kaviboy
* **Completion Status:** 100% Complete

---


## 📐 Detection Matrix & Pyramid Mapping

| Tier | Level | Sample Binary | Extracted Artifact / Behavioral Pattern | Defensive Action / Rule Applied | MITRE ATT&CK ID |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Hash Values** | 1 | `sample1.exe` | `9c550591a25c6228cb7d74d970d133d75c961ffed2ef7180144859cc09efca8c` | Added SHA256 to EDR Blocklist | N/A |
| **IP Addresses** | 2 | `sample2.exe` | Destination IP: `154.35.10.113:4444` | Firewall Egress Deny Rule | N/A |
| **Domain Names** | 3 | `sample3.exe` | Domain: `emudyn.bresonicz.info` | DNS Filtering Deny Rule | N/A |
| **Host Artifacts** | 4 | `sample4.exe` | Key: `...\Real-Time Protection`<br>Name: `DisableRealtimeMonitoring`<br>Value: `1` | Sysmon Registry Modification Rule | Defense Evasion (TA0005) |
| **Tools** | 5 | `sample5.exe` | Remote IP/Port: `any`<br>Payload Size: `97 bytes`<br>Frequency: `1800 seconds` | Sysmon Network Connection Rule | Command & Control (TA0011) |
| **TTPs** | 6 | `sample6.exe` | Path: `%temp%`<br>File Name: `exfiltr8.log` | Sysmon File Creation & Modification Rule | Collection (TA0009) |

---

## 🔍 Level-by-Level Walkthrough

### 🚨 Level 1: Hash Values (Trivial)

#### 1. Analysis & Artifact Extraction
Submitted `sample1.exe` to PicoSecure Malware Sandbox. Identified static file hash matching Metasploit payload signature:
* **SHA256:** `9c550591a25c6228cb7d74d970d133d75c961ffed2ef7180144859cc09efca8c`

![Level 1 Sandbox Analysis]<img width="1365" height="646" alt="1 1" src="https://github.com/user-attachments/assets/83e4c62f-e04f-4249-a642-8530e7345bcb" />

#### 2. EDR Rule Configuration
Added the SHA256 string directly into the EDR Hash Blocklist engine to prevent binary execution across endpoints.

![Level 1 Hash Block Rule]<img width="1365" height="644" alt="1 2" src="https://github.com/user-attachments/assets/14ba1d9d-4f3e-4069-924c-7752a5b57cf4" />

#### 3. Adversary Reaction
Sphinx acknowledged the block but noted that recompiling or re-packing source code alters hash values instantaneously.

![Level 1 Email Response]<img width="1365" height="494" alt="1 3" src="https://github.com/user-attachments/assets/f26f8526-5cbe-4a4e-8521-7e0451da18f2" />

---

### 🌐 Level 2: IP Addresses (Easy)

#### 1. Analysis & Artifact Extraction
Inspected process network activity for `sample2.exe` (`PID: 1927`). Captured direct socket connections over non-standard C2 port `4444`:
* **Target C2 IP:** `154.35.10.113`

![Level 2 Network Log Analysis]<img width="1365" height="645" alt="2 1" src="https://github.com/user-attachments/assets/95b8c179-1504-4671-88d7-41eb3ccf7f11" />

#### 2. Firewall Rule Configuration
Configured an Egress rule in Firewall Rule Manager targeting the command-and-control server IP:
* **Rule Type:** Egress
* **Destination IP:** `154.35.10.113`
* **Action:** Deny

![Level 2 Firewall Deny Rule]<img width="1365" height="646" alt="2 2" src="https://github.com/user-attachments/assets/e1cd0a00-a22d-441d-b211-2fd53826117f" />

#### 3. Adversary Reaction
Sphinx stated that IP blocklists create minor inconvenience, as adversaries can migrate infrastructure to new hosting providers quickly.

![Level 2 Email Response]<img width="1365" height="538" alt="2 3" src="https://github.com/user-attachments/assets/0ad5bf47-6ba0-4186-a899-2263b3752c5f" />

---

### 🏷️ Level 3: Domain Names (Simple)

#### 1. Analysis & Artifact Extraction
Analyzed fallback DNS queries triggered by `sample3.exe` attempting to resolve C2 domain infrastructure:
* **Malicious Domain:** `emudyn.bresonicz.info`

![Level 3 DNS Logs]<img width="1365" height="646" alt="3 1" src="https://github.com/user-attachments/assets/a0a7488d-75ce-4847-ad75-68c139dcbdb4" />

#### 2. DNS Rule Configuration
Added a deny rule in DNS Rule Manager under the Malware category:
* **Domain Name:** `emudyn.bresonicz.info`
* **Category:** Malware
* **Action:** Deny

![Level 3 DNS Block Rule]<img width="1364" height="647" alt="3 2" src="https://github.com/user-attachments/assets/3598273c-611c-4f5d-9849-10a54f85c63e" />

#### 3. Adversary Reaction
Sphinx noted that revoking domain infrastructure increases financial overhead and forces waiting times for DNS propagation.

![Level 3 Email Response]<img width="1363" height="530" alt="3 3" src="https://github.com/user-attachments/assets/988205da-7e30-4990-8349-b6d321d15715" />

---

### 💻 Level 4: Host Artifacts (Annoying)

#### 1. Analysis & Artifact Extraction
Reviewed host system activity for `sample4.exe`. Captured registry manipulation aiming to neutralize local Windows Defender real-time protection:
* **Registry Key:** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Real-Time Protection`
* **Registry Name:** `DisableRealtimeMonitoring`
* **Value:** `1`

![Level 4 Registry Log Analysis]<img width="1365" height="646" alt="4 1" src="https://github.com/user-attachments/assets/ccdd76f4-2b8f-4841-87df-cdebcef0b023" />

#### 2. Sysmon Detection Rule
Configured a host-based Sysmon Registry Modification detection rule mapped to **MITRE ATT&CK Defense Evasion (TA0005)**:
* **Registry Key:** `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Real-Time Protection`
* **Registry Name:** `DisableRealtimeMonitoring`
* **Value:** `1`
* **ATT&CK ID:** `Defense Evasion (TA0005)`

![Level 4 Sysmon Registry Rule]<img width="1365" height="645" alt="4 2" src="https://github.com/user-attachments/assets/95db43a3-ebef-45ed-9a68-0d71eaf65e55" />

#### 3. Adversary Reaction
Sphinx acknowledged that host artifact detection destroyed local execution scripts, forcing them to re-architect back-end communication frameworks.

![Level 4 Email Response]<img width="1365" height="647" alt="4 3" src="https://github.com/user-attachments/assets/c1825d0a-4ead-4ef5-b423-b448b6da0b57" />

---

### 🛠️ Level 5: Tools & Network Artifacts (Challenging)

#### 1. Analysis & Artifact Extraction
Evaluated `outgoing_connections.log` attached to `sample5.exe`. Identified automated C2 SSL beaconing behavior executing consistently every 30 minutes (1800s) carrying a uniform 97-byte payload:
* **Payload Size:** `97 bytes`
* **Beacon Frequency:** `1800 seconds`

![Level 5 Connection Log Analysis]<img width="1365" height="647" alt="5 1" src="https://github.com/user-attachments/assets/ae636fad-711f-4df6-92c9-585318f2bf24" />

#### 2. Sysmon Detection Rule
Configured a Sysmon Network Connection rule targeting beacon behavior mapped to **MITRE ATT&CK Command and Control (TA0011)**:
* **Remote IP:** `any`
* **Remote Port:** `any`
* **Size (bytes):** `97`
* **Frequency (seconds):** `1800`
* **ATT&CK ID:** `Command and Control (TA0011)`

![Level 5 Sysmon Network Rule]<img width="1365" height="644" alt="5 2" src="https://github.com/user-attachments/assets/6345bf2e-c23c-4d47-92a2-73de25bf31f2" />

#### 3. Adversary Reaction
Sphinx reported that detecting tool behaviors invalidated their entire framework, forcing significant financial and retraining investment.

![Level 5 Email Response]<img width="1365" height="644" alt="5 3" src="https://github.com/user-attachments/assets/865900da-050e-438d-9455-1c63e10328f8" />

---

### 🥷 Level 6: TTPs — Tactics, Techniques & Procedures (Tough)

#### 1. Command Log & Behavioral Analysis
Reviewed `commands.log` for `sample6.exe`. Identified automated discovery and exfiltration staging scripts executing local commands and piping system data to `%temp%\exfiltr8.log`:

```cmd
dir c:\ >> %temp%\exfiltr8.log
dir "c:\Documents and Settings" >> %temp%\exfiltr8.log
dir "c:\Program Files\" >> %temp%\exfiltr8.log
dir d:\ >> %temp%\exfiltr8.log
net localgroup administrator >> %temp%\exfiltr8.log
ver >> %temp%\exfiltr8.log
systeminfo >> %temp%\exfiltr8.log
ipconfig /all >> %temp%\exfiltr8.log
netstat -ano >> %temp%\exfiltr8.log
net start >> %temp%\exfiltr8.log
```

![Level 6 Exfiltration Commands]<img width="1365" height="646" alt="6 1" src="https://github.com/user-attachments/assets/2da5eb92-9d2e-48a9-a83a-44332f868253" />

#### 2. Sysmon Detection Rule
Created a Sysmon File Creation and Modification detection rule targeting the exfiltration staging artifact mapped to **MITRE ATT&CK Collection (TA0009)**:
* **File Path:** `%temp%`
* **File Name:** `exfiltr8.log`
* **ATT&CK ID:** `Collection (TA0009)`

![Level 6 Sysmon File Rule]<img width="1365" height="645" alt="6 2" src="https://github.com/user-attachments/assets/cc2f6318-2b38-4e46-ade4-bb326182e3c5" />

#### 3. Adversary Surrender & Final Verification
Detecting behavioral TTPs placed defense at the apex of the Pyramid of Pain. Sphinx officially surrendered, stating that changing core operational habits requires too much research and retraining.

![Level 6 Surrender Email]<img width="1364" height="490" alt="6 3" src="https://github.com/user-attachments/assets/a62e3c2c-4ebf-469d-b929-60bb6dd73934" />

![Final Inbox Status]

<img width="451" height="645" alt="8" src="https://github.com/user-attachments/assets/61ffa863-a0bb-428c-ba39-f183907f258f" />

---

## 🏆 Room Completion Banner

![TryHackMe Room Complete]<img width="1365" height="646" alt="7" src="https://github.com/user-attachments/assets/2b3ac6e7-f73a-4f26-a76c-5b643ca44858" />




# 🛡️ Threat Hunting & Incident Response Report: E-Corp APT Investigation

![MITRE ATT&CK](https://img.shields.io/badge/Framework-MITRE%20ATT%26CK-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Threat%20Neutralized-success?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-SOC%20%2F%20Threat%20Hunting-red?style=for-the-badge)

---

## 📌 Investigation Overview

| Metric | Details |
| :--- | :--- |
| **Target Organization** | E-Corp Enterprise Infrastructure |
| **Threat Actor** | Advanced Persistent Threat (APT) |
| **Primary Objective** | Exfiltration of Intellectual Property (SharePoint) |
| **Attack Vector** | Phishing E-mail with Malicious Attachment |
| **Final Outcome** | 🛑 **Intercepted & Neutralized** (Data Exfiltration Blocked) |

---

## 📋 Executive Summary

> **CRITICAL INCIDENT SUMMARY**  
> SOC analysts identified and neutralized a sophisticated intrusion campaign targeting E-Corp's core information repositories. Proactive threat hunting verified that while the adversary achieved internal foothold and credential movement, containment controls successfully prevented the egress of sensitive intellectual property.

The threat lifecycle progressed across the following operational phases:
* 🎯 **Initial Access:** Delivered via spearphishing emails containing malicious attachments.
* ⚙️ **Execution & Persistence:** Built on native Windows scripting environments (`powershell.exe` & `cmd.exe`) and auto-run registry keys.
* 🥷 **Defense Evasion:** Executed via proxy binary execution utilizing `rundll32.exe`.
* 🔎 **Discovery & Lateral Movement:** Internal reconnaissance via `tcpdump` and lateral pivot through `SMB/Windows Admin Shares`.
* 📦 **Collection & C2 Egress:** Staging inside **SharePoint** with attempted egress over external and multi-hop proxy networks.

---

## 🛠️ Investigation Methodology

The investigation was aligned with the **MITRE ATT&CK Framework** to map observed adversary behaviors across endpoint event logs, registry modifications, process telemetry, and network traffic captures.

### 🗺️ Mapped ATT&CK Matrix Summary

| Tactic | Technique | MITRE ID | Artifact / Indicator |
| :--- | :--- | :--- | :--- |
| **Initial Access** | Spearphishing Attachment | `T1566.001` | Malicious email deliverable |
| **Execution** | Command and Scripting Interpreter | `T1059.001 / .003` | `powershell.exe` & `cmd.exe` |
| **Persistence** | Registry Run Keys / Startup Folder | `T1547.001` | Obfuscated startup registry entry |
| **Defense Evasion** | System Binary Proxy Execution | `T1218.011` | `rundll32.exe` execution |
| **Discovery** | Network Sniffing | `T1040` | `tcpdump` binary deployment |
| **Lateral Movement**| Remote Services | `T1021.002` | SMB / Windows Admin Shares (`C$`, `ADMIN$`) |
| **Collection** | Information Repositories | `T1213.002` | Unauthorized SharePoint access |
| **Command & Control**| Proxy | `T1090.002 / .003`| External & Multi-hop Proxy channels |

---

## 🔍 Detailed Incident Analysis

### 1. 🎯 Initial Access
The threat actor established entry into E-Corp's internal ecosystem using **Spearphishing Attachments** (`T1566.001`). The attached malicious file contained embedded delivery code designed to initiate secondary stager downloads upon user execution.

![ATT&CK Navigator - Initial Access - Spearphishing Attachment]<img width="1365" height="647" alt="1 1" src="https://github.com/user-attachments/assets/3a16c123-0473-41ba-90bd-d06a3f911f6f" />

![Initial Access Verification]<img width="1365" height="421" alt="1 2" src="https://github.com/user-attachments/assets/6fd64719-e3c5-4206-93ec-62fa2ecb6fc8" />

---

### 2. ⚙️ Execution
Following the initial trigger, the stager invoked native command-line shells to interpret obfuscated scripts. Analysis confirmed execution logs stemming from both **PowerShell** (`T1059.001`) and **Windows Command Shell** (`T1059.003`).

![ATT&CK Navigator - Command and Scripting Interpreters]<img width="1365" height="646" alt="1 3" src="https://github.com/user-attachments/assets/d677b135-b5f2-4070-8bf7-1e6ee51fa1ad" />

![Execution Verification]<img width="1365" height="520" alt="1 4" src="https://github.com/user-attachments/assets/d3eed98d-919b-4033-93d2-d522a1241edf" />

---

### 3. 🔄 Persistence
To ensure persistent access across system restarts, the script modified auto-start entry locations in the Windows Registry, targeting **Registry Run Keys** (`T1547.001`) to automatically execute the secondary payload upon user logon.

![ATT&CK Navigator - Registry Run Keys]<img width="1365" height="645" alt="1 5" src="https://github.com/user-attachments/assets/813ec611-a0c8-47c4-8f6b-7ae1dbc51585" />

![Persistence Verification]<img width="1365" height="434" alt="1 6" src="https://github.com/user-attachments/assets/e836b4ff-12ad-4d74-ac92-5308386297ee" />

---

### 4. 🥷 Defense Evasion
To bypass signature-based endpoint monitoring and security controls, the APT utilized Living-off-the-Land Binaries (LotBins). Specifically, **Rundll32** (`rundll32.exe` - `T1218.011`) was leveraged to proxy the execution of untrusted dynamic-link libraries (DLLs).

![ATT&CK Navigator - System Binary Proxy Execution (Rundll32)]<img width="1365" height="638" alt="1 7" src="https://github.com/user-attachments/assets/2fea7e1d-f477-47b9-9ffc-260b78becfff" />

![Defense Evasion Verification]<img width="1363" height="540" alt="1 8" src="https://github.com/user-attachments/assets/4b6c75db-eabb-441d-84c8-49752d8ad6b1" />

---

### 5. 🔎 Discovery
Once host persistence was secured, the adversary dropped the packet capture tool `tcpdump` on the host to perform internal **Network Sniffing** (`T1040`). This allowed the actor to analyze subnet traffic and locate high-value target assets.

![ATT&CK Navigator - Discovery / Network Sniffing]<img width="1365" height="644" alt="1 9" src="https://github.com/user-attachments/assets/8285815e-38c9-48e8-be28-9eef3c1bc65f" />

![Discovery Verification]<img width="1365" height="359" alt="1 10" src="https://github.com/user-attachments/assets/c7beff90-cee4-4cf2-a471-aaaef66bc5df" />

![ATT&CK Navigator Discovery Layer Details]<img width="1365" height="644" alt="1 11" src="https://github.com/user-attachments/assets/653ea262-a22f-4353-87ff-b92b55f64247" />

![Progress Check 1]<img width="1365" height="352" alt="1 12" src="https://github.com/user-attachments/assets/81b8bc3f-608a-4106-a74e-613ef9a09f4e" />

---

### 6. 🚀 Lateral Movement
Leveraging harvested network credentials, the APT traversed the corporate network via **SMB / Windows Admin Shares** (`T1021.002`) (e.g., `ADMIN$`, `C$`), enabling remote process execution across adjacent servers.

![ATT&CK Navigator - Remote Services / SMB Shares]<img width="1364" height="646" alt="1 13" src="https://github.com/user-attachments/assets/09c4e9e9-9b98-4b46-9f7b-fb2f200e9abd" />

![Lateral Movement Verification]<img width="1365" height="443" alt="1 14" src="https://github.com/user-attachments/assets/97d8ebbe-a43e-42f7-ac26-30056c9aa3eb" />

---

### 7. 📦 Collection
The adversary pivoted directly toward E-Corp's core intellectual property repository: **SharePoint** (`T1213.002`). Unauthorized queries and file access logs confirmed intent to stage sensitive enterprise files for exfiltration.

![ATT&CK Navigator - Information Repositories / Sharepoint]<img width="1365" height="647" alt="1 15" src="https://github.com/user-attachments/assets/1f2eb2c5-f22a-467e-a997-ad423ff7a81c" />

![Collection Verification]<img width="1365" height="392" alt="1 16" src="https://github.com/user-attachments/assets/7b136eb7-9d77-49f4-9175-3d168ebcdfe6" />

---

### 8. 🌐 Command & Control / Exfiltration
Due to outbound egress restrictions at E-Corp's perimeter, the APT attempted to establish C2 communication and exfiltration pipelines using **External Proxies** (`T1090.002`) and **Multi-hop Proxies** (`T1090.003`). Proactive blocking of these egress proxy nodes prevented any data transfer.

![ATT&CK Navigator - Proxy Infrastructure]<img width="1365" height="646" alt="1 17" src="https://github.com/user-attachments/assets/9ee12387-ef6c-4c9a-acfa-dd147f22e7e0" />

![Command & Control Verification]<img width="1365" height="495" alt="1 18" src="https://github.com/user-attachments/assets/34c9a349-b322-416d-940c-161db9bbf9ad" />

![Full ATT&CK Matrix Overview]<img width="1363" height="643" alt="1 19" src="https://github.com/user-attachments/assets/a6529b16-cf7d-48bd-b23e-9b81982979c0" />

![Final Task Verification]<img width="1365" height="625" alt="1 20" src="https://github.com/user-attachments/assets/5cf912a7-512d-4f5c-aa5e-e583790337fa" />

---

### 🏆 Mission Accomplished
![Room Completed Banner]<img width="1365" height="644" alt="1 21" src="https://github.com/user-attachments/assets/37b50c60-425f-4612-8d99-964d875ef435" />

---

## ⚡ Detection & SIEM Queries

Below are production-ready SIEM queries to detect these TTPs in an enterprise logging environment:

### 1. Obfuscated PowerShell Execution
```kql
process.name: "powershell.exe" AND process.args: ("-EncodedCommand" OR "-e " OR "-nop" OR "-w hidden" OR "-enc")
```

### 2. Registry Persistence (Run Key Addition)
```kql
event.code: "13" AND target.path: "*\\Software\\Microsoft\\Windows\\CurrentVersion\\Run*"
```

### 3. Suspicious Rundll32 Execution
```kql
process.name: "rundll32.exe" AND NOT (process.parent.name: "explorer.exe" OR process.parent.name: "svchost.exe")
```

### 4. Sniffing Utility Execution on Endpoints
```kql
process.name: ("tcpdump.exe" OR "tshark.exe" OR "windump.exe") AND NOT (user.name: "admin_*")
```

### 5. Administrative Share Access (SMB)
```kql
event.code: "5140" AND share.name: ("*\\ADMIN$" OR "*\\C$")
```

---

## 💡 Mitigation & Defensive Recommendations

> [!IMPORTANT]
> A multi-layered defense strategy combining host isolation, strict access controls, and network filtering is required to prevent similar APT campaigns.

### 🔴 Immediate Incident Remediation
* **Host Isolation:** Immediately isolate all endpoints exhibiting `tcpdump` execution or anomalous `rundll32.exe` parent-child activity.
* **Credential Invalidation:** Reset passwords and revoke active tokens for all Active Directory user accounts involved in the SMB and SharePoint sessions.
* **Perimeter Blocking:** Block all external IP addresses and multi-hop proxy domains associated with the C2 infrastructure at the firewall level.

### 🔵 Strategic Enterprise Hardening
* **Email Attachment Security:** Enforce strict attachment rules at the secure email gateway (SEG) to block container/script formats (`.iso`, `.vbs`, `.js`, `.xlsm`) and run automated sandbox checks.
* **Attack Surface Reduction (ASR):** Enable Windows ASR rules prohibiting Office applications from launching child processes.
* **PowerShell Hardening:** Force **Constrained Language Mode (CLM)** system-wide and enable **Script Block Logging (Event ID 4104)**.
* **Restrict Admin Shares:** Restrict SMB admin share connections using local Windows Firewall rules and enforce **Network Level Authentication (NLA)**.
* **Data Loss Prevention (DLP):** Implement granular DLP monitoring on SharePoint deployments and enforce conditional access policies for unmanaged devices.




<div align="center">

# 🎣 TryHackMe: Phishing Emails 1

[![TryHackMe](https://img.shields.io/badge/TryHackMe-Phishing%20Emails%201-red?style=for-the-badge&logo=tryhackme)](https://tryhackme.com)
[![Role](https://img.shields.io/badge/Role-SOC%20Analyst%20Level%201-blue?style=for-the-badge&logo=shield)](https://tryhackme.com)
[![Status](https://img.shields.io/badge/Status-Completed%20100%25-brightgreen?style=for-the-badge&logo=checkmark)](https://tryhackme.com)
[![Tools](https://img.shields.io/badge/Tools-Thunderbird%20%7C%20CyberChef%20%7C%20APIVoid-orange?style=for-the-badge)](https://github.com)

**An end-to-end investigation and analysis write-up of malicious email artifacts, header inspection, payload extraction, and indicator defanging.**

---

</div>

## 📌 Table of Contents
- [Overview](#-overview)
- [Learning Objectives](#-learning-objectives)
- [Key Skills & Tools Covered](#-key-skills--tools-covered)
- [Step-by-Step Investigation Walkthrough](#-step-by-step-investigation-walkthrough)
  - [Task 1 & 2: Email Inspection & Domain Verification](#task-1--2-email-inspection--domain-verification)
  - [Task 3 & 4: Network Hops & Raw Header Analysis](#task-3--4-network-hops--raw-header-analysis)
  - [Task 5: Email Body & Encoded Attachment Analysis](#task-5-email-body--encoded-attachment-analysis)
  - [Task 6: Brand Impersonation & BEC Analysis](#task-6-brand-impersonation--bec-analysis)
  - [CyberChef Processing & IoC Defanging](#cyberchef-processing--ioc-defanging)
  - [Task 7: Room Completion](#task-7-room-completion)
- [Repository Structure & Image Placement](#-repository-structure--image-placement)

---

## 🎯 Overview
This repository documents the detailed walkthrough and investigation methodology for the **Phishing Emails 1** room on TryHackMe. As a SOC Level 1 Analyst, understanding how to dissect phishing emails is crucial for triage, extracting Indicators of Compromise (IoCs), and mitigating initial access vector threats.

![Room Tasks Overview]<img width="1365" height="645" alt="1 9" src="https://github.com/user-attachments/assets/7d86dc0d-ece1-432b-802b-3b9711e3e70f" />

---

## 🧠 Learning Objectives
* ✉️ **Email Architecture:** Understand envelopes, headers, message bodies, and attachments.
* 🔎 **Header Forensics:** Trace email server hops using `X-Originating-IP`, `Received`, and authentication controls (`SPF`, `DKIM`, `DMARC`).
* 🔓 **Payload Decoding:** Safely inspect and decode Base64 encoded email attachments without execution.
* 🛡️ **IoC Handling:** Process, normalize, and defang network artifacts before documentation.

---

## 🛠️ Key Skills & Tools Covered

| Tool / Concept | Category | Purpose / Utility |
| :--- | :--- | :--- |
| **Mozilla Thunderbird** | Email Client | Inspecting `.eml` files, visual layout triage, and viewing raw source headers |
| **Mousepad** | Text Editor | Direct examination of raw text-based email exports (`.txt`) |
| **CyberChef** | Data Analysis | Base64 decoding, string transformations, and IP/Domain defanging |
| **APIVoid** | Threat Intelligence | Decoding Base64 attachments and generating safe document previews |
| **Header Forensics** | SOC Triage | Identifying originating senders, spoofed domains, and infrastructure hops |

---

## 🚀 Step-by-Step Investigation Walkthrough

### Task 1 & 2: Email Inspection & Domain Verification
The investigation begins by inspecting `email1.eml` within Mozilla Thunderbird to evaluate sender details and visual layout.

![Thunderbird Email 1 View]<img width="673" height="647" alt="1 1" src="https://github.com/user-attachments/assets/47eae2f0-b1dc-48ca-8206-a24854b57142" />

* **From Header:** `newsletters@ant.anki-tech.com`
* **Recipient:** `alexa@yahoo.com`
* **Subject:** `Help protect your budget by protecting your home`
* **Observation:** Thunderbird automatically restricted remote content to prevent tracking pixels and malicious external calls.

---

### Task 3 & 4: Network Hops & Raw Header Analysis
By pressing `Ctrl + U` in Thunderbird, we open the raw message source for `email1.eml` to analyze network headers.

![Email 1 Source Code]<img width="677" height="645" alt="1 2" src="https://github.com/user-attachments/assets/cba1ea17-e7d5-40b6-ba90-9392af140733" />

* **Originating IP Address:** `43.255.56.161` (Extracted from `X-Originating-Ip`)
* **Return-Path:** `reback-a3970-837890-838253-c8b776d9=952622232=8@ant.anki-tech.com`
* **Email Security Checks:** 
  * `SPF`: `pass`
  * `DKIM`: `pass`
  * `DMARC`: `pass`

---

### Task 5: Email Body & Encoded Attachment Analysis
Next, we examine `email2.txt`, which contains a raw MIME attachment encoded in Base64.

![Email 2 Attachment Raw Text]<img width="671" height="644" alt="1 3" src="https://github.com/user-attachments/assets/f111614c-4340-4cbd-b14e-ef712d88318e" />

* **Attachment Filename:** `zmqpalgh.pdf`
* **Content-Type:** `application/pdf`
* **Encoding Type:** `base64`

To analyze the file safely, the raw Base64 string was extracted and passed into an online decoder tool (APIVoid) to render the attachment safely.

![APIVoid PDF Generation]<img width="1365" height="645" alt="1 4" src="https://github.com/user-attachments/assets/5b0dafad-53d2-4ee5-8153-7639b9a01c2b" />

---

### Task 6: Brand Impersonation & BEC Analysis
In `email3.eml`, we analyze an email purporting to be an official order confirmation from **Home Depot**.

![Thunderbird Email 3 View]<img width="674" height="646" alt="1 5" src="https://github.com/user-attachments/assets/b08a7bb6-16ff-4adb-8ebc-88b942f0322a" />

* **Sender Display Name:** `Thank you! Home Depot`
* **Actual Sending Address:** `support@teckbe.com`
* **Phishing Tactic:** Domain Mismatch / Brand Impersonation (`Home Depot` vs `teckbe.com`).

We then inspect the raw source code of `email3.eml` to pull back-end server indicators.

![Email 3 Source Code]<img width="672" height="645" alt="1 6" src="https://github.com/user-attachments/assets/e3d58e5b-b9c3-4069-8206-d3b3f1ba7a47" />

* **Originating IP:** `103.234.236.83`
* **Receiving Mail Server Domain:** `atlas102.free.mail.gq1.yahoo.com`

---

### CyberChef Processing & IoC Defanging
To ensure safety in incident reports, all malicious network indicators must be defanged prior to distribution.

#### 1️⃣ Defanging Originating IP Address
Using CyberChef's `Defang IP Addresses` operation:

![Defanging IP Address in CyberChef]<img width="1365" height="646" alt="1 7" src="https://github.com/user-attachments/assets/37f0999a-e5d1-4fad-a718-936c7d72d536" />

* **Raw IP:** `103.234.236.83`
* **Defanged IP:** `103[.]234[.]236[.]83`

#### 2️⃣ Verifying Mail Server Domain String
Using CyberChef to verify and standardize the receiving mail domain:

![Analyzing Domain in CyberChef]<img width="1364" height="641" alt="1 8" src="https://github.com/user-attachments/assets/a5def9ab-adf3-43e5-ba02-1da5ee96154d" />

* **Mail Server Domain:** `atlas102.free.mail.gq1.yahoo.com`

---

### Task 7: Room Completion
All questions and tasks for the room were successfully completed.

![Room Completed Banner]<img width="1365" height="647" alt="2" src="https://github.com/user-attachments/assets/a2879186-0fcc-462b-9e6b-ea11291c67ca" />

---




# TryHackMe: Phishing Emails 3 - Writeup & Analysis

## Overview
This repository contains a detailed walkthrough and analysis report for the **Phishing Emails 3** room on TryHackMe. The investigation covers email header inspection, sandbox dynamic analysis using ANY.RUN, metadata extraction, and exploit identification across multiple phishing scenarios involving malicious PDF documents and Excel spreadsheets.

* **Category:** Digital Forensics & Incident Response (DFIR) / Phishing Analysis
* **Platform:** [TryHackMe](https://tryhackme.com/)
* **Tools Used:** 
  * Mozilla Thunderbird
  * ANY.RUN Interactive Malware Analysis Sandbox
  * ExifTool / PDF & Office Metadata Tools
  * Linux Terminal

---

## Task 8: Case 1 & Case 2 — Email & PDF Malware Analysis

### 1. Phishing Email Analysis (Netflix Phishing Email)
The investigation begins with analyzing an incoming email claiming that a Netflix account is on hold due to billing issues.

![Netflix Email Preview]<img width="676" height="646" alt="1 1" src="https://github.com/user-attachments/assets/7057c513-66f1-4af7-9e0a-2de1a07611ae" />

#### Header Analysis
Inspecting the email headers using Mozilla Thunderbird reveals inconsistencies between the claimed sender, the envelope domain, and authentication protocols:

![Netflix Email Source Headers]<img width="678" height="618" alt="1 2" src="https://github.com/user-attachments/assets/58b27f2d-9605-4222-8341-7d23efc4538a" />

![Thunderbird Link Context Menu]<img width="675" height="645" alt="1 3" src="https://github.com/user-attachments/assets/fd3ef607-58e3-40b3-a0af-92835022fb59" />

* **From Header:** `N e t f l i x <JGQ47wazXe1xyVBrkeDg-JOg7ODDQwWdR@JOg7ODDQwWdR-yVkCaBKTNp.gogolecloud.com>`
* **Return-Path:** `<postmaster@etekno.xyz>`
* **X-Originating-IP:** `209.85.167.226`
* **SPF Record:** `none` (Domain `etekno.xyz` does not designate permitted sender hosts)
* **DMARC Record:** `unknown`

---

### 2. Malicious Document Analysis (`Payment-updateid.pdf`)
The second scenario involves analyzing a PDF file (`Payment-updateid.pdf`) submitted to ANY.RUN for dynamic sandbox execution.

![PDF Open & Initial Sandbox View]<img width="1365" height="645" alt="2 1" src="https://github.com/user-attachments/assets/de72d911-6b2b-43c6-8e05-530af783551d" />

#### Sandbox Execution & Indicator Details
The sample runs inside a Windows 7 32-bit virtual machine environment:

![ANY.RUN Process Details and Score]<img width="1365" height="646" alt="2 2" src="https://github.com/user-attachments/assets/3c9c2f89-9d72-4186-8f30-4385218dc30b" />

![PDF File Hashes and EXIF Metadata]<img width="1365" height="646" alt="2 3" src="https://github.com/user-attachments/assets/8bc561ad-c761-4504-9a56-8e66f141dcb0" />

![ANY.RUN Network Connections]<img width="1365" height="647" alt="2 4" src="https://github.com/user-attachments/assets/97c980d3-8ad4-4866-937e-8ca20503a623" />

![ANY.RUN Threat Activity & Indicators]<img width="1365" height="646" alt="2 5" src="https://github.com/user-attachments/assets/f4b5ed8a-a2ee-4bff-87df-5a944eeda1b7" />

#### File Metadata & Hashes
| Attribute | Value |
| :--- | :--- |
| **Filename** | `Payment-updateid.pdf` |
| **File Size** | `188.67 KB` |
| **MIME Type** | `application/pdf` |
| **PDF Version** | `1.7` |
| **Author** | `PayPal Support` |
| **Creator / Producer** | `Microsoft® Word 2016` |
| **Creation Date** | `2021:03:10 19:22:08+08:00` |
| **MD5 Hash** | `4A2775EAE2EBEF41901A3F08D3B857C8` |
| **SHA1 Hash** | `8B3439F5EA2F20C6BE329C4C6B8EAA9CC439233B` |
| **SHA256 Hash** | `CC6F1A04B10BCB168AEEC8D870B97BD7C20FC161E8310B5BCE1AF8ED420E2C24` |

#### Extracted Network IOCs
* **Malicious Connection:** `2.16.107.24:443` (`acroipm2.adobe.com`)
* **Malicious Traffic:** `142.250.186.132` (`www.google.com`)
* **Network Threat:** `svchost.exe` (PID: 1776) triggered `ET INFO TLS Handshake Failure`

---

## Task 9: Case 3 — Excel Exploit Analysis (CVE-2017-11882)

The third scenario covers an Excel spreadsheet attachment (`CBJ200620039539.xlsx`) that weaponizes an old Microsoft Office vulnerability to trigger remote code execution.

![Excel Execution and EQNEDT32 Process]<img width="1365" height="645" alt="3 1" src="https://github.com/user-attachments/assets/89c181a0-6e8c-40ce-9c6a-1d96bb0ee80e" />

### Hashes & File Information

![Excel Hashes and File Structure]<img width="1365" height="645" alt="3 2" src="https://github.com/user-attachments/assets/c590eb27-9137-4cb1-b82e-e96cf8f7d7eb" />

* **Filename:** `CBJ200620039539.xlsx`
* **File Size:** `15.05 KB`
* **MIME Type:** `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`
* **MD5 Hash:** `F7F4EC2A0ADC9CC33CDBC7D548A6BEF9`
* **SHA1 Hash:** `D460315F92AA3DCA63617431883834ED94C09F45`
* **SHA256 Hash:** `5F94A66E0CE78D17AFC2DD27FC17B44B3FFC13AC5F42D3AD6A5DCFB36715F3EB`

---

### Dynamic Execution & Network Connections

![DNS Requests and Network Traffic]<img width="1365" height="647" alt="3 3" src="https://github.com/user-attachments/assets/a29fc983-7cbf-42bf-9460-6f65072a4b3e" />

![Behavioral Activities and CVE Exploitation]<img width="1365" height="644" alt="3 4" src="https://github.com/user-attachments/assets/fe8acfa9-5ebe-4b14-80a0-6d111749ba88" />

#### Process Execution Flow
1. `EXCEL.EXE /dde` (PID: `1016`) — Initial document execution.
2. `EQNEDT32.EXE -Embedding` (PID: `1068`) — Equation Editor vulnerability triggered (**CVE-2017-11882**).
3. `ntvdm.exe -i1` (PID: `1328`) — Spawns as part of payload execution.

#### HTTP Requests & Malicious URLs
| Host Domain | IP Address | Status Code | URL Target |
| :--- | :--- | :--- | :--- |
| `biz9holdings.com` | `204.11.56.48` | `302 Found` | `http://biz9holdings.com/INVOICE/COVID19.exe` |
| `findresults.site` | `103.224.182.251` | `302 Found` | `http://findresults.site/?rpid=2POQ7BC1G` |
| `ww38.findresults.site` | `75.2.11.242` | `200 OK` | `http://ww38.findresults.site/?rpid=2POQ7BC1G&subid1=...` |

---

## Task Questions & Answers Summary

| Task # | Question / Analysis Point | Finding / Value |
| :--- | :--- | :--- |
| **Task 8** | PDF Sandbox Threat Score | `50 / 100` |
| **Task 8** | PDF Author Metadata | `PayPal Support` |
| **Task 8** | Primary Process Executed | `AcroRd32.exe` (PID: `2088`) |
| **Task 9** | Exploited Vulnerability CVE | `CVE-2017-11882` |
| **Task 9** | Exploit Process Name | `EQNEDT32.EXE` |
| **Task 9** | First Download URL Target | `http://biz9holdings.com/INVOICE/COVID19.exe` |

---

## Room Completion

![TryHackMe Room Completed]<img width="1365" height="644" alt="4" src="https://github.com/user-attachments/assets/b10f890f-69a6-4b6c-834f-94688532d561" />

* **Completed Tasks:** 10 / 10
* **Status:** Completed




# TryHackMe: Phishing Emails 4 & Wireshark PCAP Traffic Analysis

## Overview
This writeup documents the network traffic analysis of email communications and packet captures (`traffic.pcap`) captured using Wireshark. The investigation focuses on SMTP traffic inspection, protocol responses, error codes, email delivery failure tracking, user-agent/X-Mailer identification, and attachment extraction.

* **Category:** Digital Forensics & Incident Response (DFIR) / Network Traffic Analysis
* **Platform:** [TryHackMe](https://tryhackme.com/)
* **Tools Used:** 
  * Wireshark (Network Protocol Analyzer)
  * Linux Terminal

---

## Technical Analysis & Walkthrough

### 1. SMTP Handshake & TCP Session Inspection
Analyzing initial connection packets between internal host `10.12.19.101` and remote IP `67.97.216.244` over TCP port `1042`.

![TCP Handshake and Connection Analysis]<img width="672" height="647" alt="1 1" src="https://github.com/user-attachments/assets/c9008683-349f-4a06-96fb-dd78c2293bb6" />

---

### 2. Identifying Spam Filters & Blocklists (`smtp.response.code`)
Filtering for SMTP response codes to identify rejected connections. Frame 73 shows connection attempts from `17.171.2.68` to internal host `10.12.19.101` triggering IP lookup checks (`dnsbl-lookup.cgi?ip=173.66.46.112`).

![SMTP Filter and Spamhaus Blocked IP Check]<img width="677" height="645" alt="1 2" src="https://github.com/user-attachments/assets/9a2d0860-5dfb-40f6-9190-b80dd2d3ea09" />

---

### 3. Service Banners & Mail Server Greetings (`smtp.response.code==220`)
Filtering for code `220` (SMTP Service Ready Banners) highlights incoming connections from external IPs, including `216.97.88.9` sending an ESMTP Sendmail greeting (`unicode.org`).

![SMTP 220 Service Ready Banners]<img width="678" height="644" alt="1 3" src="https://github.com/user-attachments/assets/71ac1222-cfdc-4472-92bb-c2f3ef5357e2" />

---

### 4. Spamhaus Real-time Blackhole List (RBL) Rejection Analysis
Filtering string searches for `spamhaus` reveals SMTP code `553 5.3.0 Email blocked using spamhaus.org`, pointing to malicious origin IP `173.66.46.112`.

![Spamhaus String Match Analysis]<img width="682" height="644" alt="1 4" src="https://github.com/user-attachments/assets/179ba617-7752-4fb8-a4ba-e6c4fffc476b" />

---

### 5. Mailbox Rejection Verification (`553 Requested action not taken`)
Inspecting packet #156 reveals the explicit SMTP error parameters: `553 5.3.0 Email blocked using spamhaus.org - see http://www.spamhaus.org`.

![SMTP Response 553 Detailed Inspection]<img width="675" height="642" alt="1 5" src="https://github.com/user-attachments/assets/e3d57cc9-1de3-4218-94ac-32e8ea948897" />

---

### 6. Storage & Security Block Rejections (`smtp.response.code==552`)
Searching for error code `552` (Requested mail action aborted) reveals incoming connections from `173.194.66.27` returning `552-5.7.0 This message was blocked because its content presents a potential security issue`.

![SMTP Response 552 Security Block Analysis]<img width="678" height="645" alt="1 6" src="https://github.com/user-attachments/assets/62e4f125-722a-45f1-88cc-5934d3d79ac7" />

---

### 7. Full Session Stream & Rejection Trace
Tracking the full ESMTP conversation showing `EHLO unicode.org` followed by `MAIL FROM:<MAILER-DAEMON@unicode.org>` resulting in security rejections.

![SMTP Conversation Stream Tracking]<img width="679" height="643" alt="2 1" src="https://github.com/user-attachments/assets/d2658f18-7088-4f0f-8f0e-a051f1b82672" />

---

### 8. Attachment Extraction & MIME Encapsulation Analysis
Filtering for packet payloads containing raw email body MIME data shows `Content-Disposition: attachment; filename="document.zip"`.

![Extracting Attachment Name document.zip]<img width="679" height="647" alt="2 2" src="https://github.com/user-attachments/assets/6e8fb34d-b687-444f-b3d8-8decc40462d8" />

---

### 9. Delivery Failure Message Tracking (Non-Delivery Reports - NDR)
Analyzing delivery failure notifications inside packet #270 reveals failure reason `Host 212.253.25.152 is not responding` when attempting delivery to recipient `talkback@mozilla.org`.

![Delivery Failure Notification Trace]<img width="680" height="647" alt="2 3" src="https://github.com/user-attachments/assets/1a225b5b-3ac2-40ed-8f65-85970269032f" />

---

### 10. Email Client Profiling via `X-Mailer` Headers (`imf`)
Filtering for Internet Message Format (`imf`) headers reveals mail client metadata:
`X-Mailer: Microsoft Outlook Express 6.00.2600.0000` and `X-MimeOLE: Produced By Microsoft MimeOLE V6.00.2600.0000`.

![Extracting X-Mailer User-Agent Metadata]<img width="678" height="644" alt="2 4" src="https://github.com/user-attachments/assets/69b0bbdb-a820-4733-bc86-52f02be02d48" />

---

### 11. Malicious Executable Attachment Identification (`attachment.scr`)
Inspecting encapsulated multipart attachments reveals an executable payload named `attachment.scr` (`Content-Type: application/octet-stream`), containing Base64 encoded PE headers starting with `TVqQAAMAAAA...`.

![Identifying Suspicious Executable Payload attachment.scr]<img width="676" height="646" alt="2 5" src="https://github.com/user-attachments/assets/ecc1a70f-f3cc-4490-a105-1623f283c213" />

---

## Room Completion

![Phishing Prevention Banner]<img width="651" height="326" alt="3" src="https://github.com/user-attachments/assets/c6e63091-cf32-4388-a6db-48fbd178a982" />

---

## Summary of Key Findings & Network IOCs

| Parameter / Indicator | Extracted Value / Finding |
| :--- | :--- |
| **Internal Receiver Host** | `10.12.19.101` |
| **Blocked Origin IPs** | `173.66.46.112`, `173.194.66.27`, `216.97.88.9` |
| **RBL Blocklist Used** | `spamhaus.org` |
| **SMTP Error Codes** | `553` (Blocked by RBL) / `552` (Content/Security issue) |
| **Extracted Mail Client** | `Microsoft Outlook Express 6.00.2600.0000` |
| **Extracted Attachments** | `document.zip`, `attachment.scr` (PE Executable File) |
| **Failed Recipient Address** | `talkback@mozilla.org` |




# TryHackMe: Greenholt v2 Phishing Email Forensics & Header Analysis

## Executive Summary
This investigation analyzed a suspicious phishing email artifact (`challenge.eml`) disguised as an official SWIFT payment confirmation. Forensic analysis revealed a spoofed sender domain, failed email authentication controls, and a malicious Cabinet archive attachment (`SWT_#09674321____PDF__.CAB`). Hash identification verified the attachment as **Trojan.MSIL/Loki (LokiBot)**, a prominent info-stealer. 

**Core SOC Takeaway:** Security controls should strictly enforce DMARC `quarantine`/`reject` policies and block executable/archive attachments with deceptive double extensions (`.PDF__.CAB`) at the secure email gateway (SEG) boundary.

---

## Overview
This documentation details the forensic investigation of a suspicious email artifact (`challenge.eml`) as part of the Greenholt v2 challenge on TryHackMe. The analysis encompasses email header examination, IP intelligence gathering via WHOIS, SPF/DMARC domain authentication checks, payload hash extraction, and VirusTotal threat analysis.

* **Category:** Digital Forensics & Incident Response (DFIR) / Email Analysis
* **Platform:** [TryHackMe](https://tryhackme.com/)
* **Tools Used:** 
  * Mozilla Thunderbird (Email Client / Raw Source Viewer)
  * Linux Terminal (`sha256sum`)
  * Whois / ARIN Lookup
  * MXToolbox (SPF & DMARC Record Lookup)
  * VirusTotal

---

## Table of Contents
* [Executive Summary](#executive-summary)
* [Overview](#overview)
* [Technical Analysis & Walkthrough](#technical-analysis--walkthrough)
  * [1. Initial Email Content Inspection](#1-initial-email-content-inspection)
  * [2. Identifying Subject & Lure Details](#2-identifying-subject--lure-details)
  * [3. Raw Email Header Analysis & Authentication Failures](#3-raw-email-header-analysis--authentication-failures)
  * [4. Originating IP Identification](#4-originating-ip-identification)
  * [5. IP WHOIS Reconnaissance](#5-ip-whois-reconnaissance)
  * [6. Domain Authentication Analysis: SPF Lookup](#6-domain-authentication-analysis-spf-lookup)
  * [7. Domain Authentication Analysis: DMARC Lookup](#7-domain-authentication-analysis-dmarc-lookup)
  * [8. MIME Body & Malicious Payload Attachment Analysis](#8-mime-body--malicious-payload-attachment-analysis)
  * [9. File Hash Extraction (SHA-256)](#9-file-hash-extraction-sha-256)
  * [10. VirusTotal Malicious Payload Analysis](#10-virustotal-malicious-payload-analysis)
* [Room Completion](#room-completion)
* [Summary of Key Findings & Indicators of Compromise (IOCs)](#summary-of-key-findings--indicators-of-compromise-iocs)

---

## Technical Analysis & Walkthrough

### 1. Initial Email Content Inspection
Opening `challenge.eml` in Mozilla Thunderbird reveals a lure message pretending to be a SWIFT funds transfer confirmation from `Mr. James Jackson <info@mutawamarine.com>` sent to `webmaster@redacted.org`. An attachment named `SWT_#09674321____PDF__.CAB` (400 KB) is embedded.

![Initial Phishing Email Inspection in Thunderbird]<img width="679" height="643" alt="1 1" src="https://github.com/user-attachments/assets/627a3ae6-2634-4e20-805d-50dfebfb4be8" />

---

### 2. Identifying Subject & Lure Details
Extracting the subject line (`Transfer Reference Number:(09674321)`) used in the financial pretexting attack.

![Subject Line Analysis]<img width="676" height="643" alt="1 2" src="https://github.com/user-attachments/assets/8b51591d-c37b-4b4d-a0b5-4a467cb0e818" />

---

### 3. Raw Email Header Analysis & Authentication Failures
Inspecting the raw email source in Thunderbird reveals critical metadata headers:
* **Return-Path:** `<info@mutawamarine.com>`
* **Received-SPF:** `fail` (Domain `mutawamarine.com` does not designate sending IP as permitted)
* **DMARC:** `unknown`

![Raw Email Header Inspection]<img width="679" height="645" alt="1 3" src="https://github.com/user-attachments/assets/98aa51c7-541b-4c10-8428-e7a64dba2dd7" />

---

### 4. Originating IP Identification
Tracing the hop headers (`Received: from ...`) isolates the true sending IP address `192.119.71.157` (`hwsrv-737338.hostwindsdns.com`).

![Originating IP Extraction]<img width="677" height="647" alt="1 4" src="https://github.com/user-attachments/assets/4254b482-2eb8-4e70-ab28-1c6ebfb6de22" />

---

### 5. IP WHOIS Reconnaissance
Performing a WHOIS lookup on IP `192.119.71.157` identifies the hosting provider as **HostPapa** (NetRange: `192.119.64.0 - 192.119.127.255`, OrgName: `HostPapa`, OrgId: `HOSTP-7`).

![WHOIS IP Analysis]<img width="1365" height="644" alt="1 5" src="https://github.com/user-attachments/assets/ff3e978d-7901-4061-ae64-33d25602d7f3" />

---

### 6. Domain Authentication Analysis: SPF Lookup
Querying MXToolbox for `mutawamarine.com`'s SPF record yields:
`v=spf1 include:spf.protection.outlook.com -all`
Since the email originated from HostPapa (`192.119.71.157`) and not Microsoft Outlook servers, the SPF check correctly failed.

![MXToolbox SPF Record Lookup]<img width="1365" height="647" alt="1 6" src="https://github.com/user-attachments/assets/2bf946a0-7b0b-40f7-9ad0-b4c343512973" />

---

### 7. Domain Authentication Analysis: DMARC Lookup
Querying MXToolbox for DMARC records reveals:
`v=DMARC1; p=quarantine; fo=1`
The domain has configured DMARC policy to quarantine messages failing authentication checks.

![MXToolbox DMARC Record Lookup]<img width="1365" height="647" alt="1 7" src="https://github.com/user-attachments/assets/bb04d972-5f69-4c8e-af24-56f8810127ab" />

---

### 8. MIME Body & Malicious Payload Attachment Analysis
Inspecting the MIME structure shows HTML body styling followed by the attachment definition:
* **Content-Type:** `application/octet-stream`
* **Filename:** `SWT_#09674321____PDF__.CAB` (Double extension masquerading as a PDF)

![MIME Attachment Source Analysis]<img width="676" height="645" alt="1 8" src="https://github.com/user-attachments/assets/8a1cba2c-cf68-4037-a693-cba8b97a669c" />

---

### 9. File Hash Extraction (`SHA-256`)
In the Linux Terminal, calculating the SHA-256 hash of the extracted `.CAB` file:

sha256sum SWT_#09674321____PDF__.CAB
# Hash: 2e91c533615a9bb8929ac4bb76707b2444597ce063d84a4b33525e25074fff3f

![SHA-256 Hash Generation]<img width="679" height="646" alt="1 9" src="https://github.com/user-attachments/assets/fa8224d6-fe11-4ccf-ae94-1cde6e929bce" />

---

### 10. VirusTotal Malicious Payload Analysis
Submitting the SHA-256 hash to VirusTotal yields **51/64 security vendor detections**. The file is identified as a malicious loader/stealer associated with the **Trojan.MSIL/Loki** (LokiBot) malware family.

![VirusTotal Threat Detection Results]<img width="1365" height="647" alt="1 10" src="https://github.com/user-attachments/assets/184a7eb2-0cdc-470b-80a7-358bf45042c5" />

---

## Room Completion

![TryHackMe Greenholt v2 Room Completion]<img width="1365" height="646" alt="1 11" src="https://github.com/user-attachments/assets/f6ac4b7c-3452-42fe-bcf3-c0e6b4b6dd9e" />

---

## Summary of Key Findings & Indicators of Compromise (IOCs)

| Parameter / Indicator | Extracted Value / Finding |
| :--- | :--- |
| **Sender Address** | `Mr. James Jackson <info@mutawamarine.com>` |
| **Recipient Address** | `webmaster@redacted.org` |
| **Reply-To Address** | `info.mutawamarine@mail.com` |
| **Originating IP** | `192.119.71.157` |
| **IP Hosting Provider** | HostPapa / Hostwinds |
| **SPF Result** | `FAIL` (Unauthorized sending IP) |
| **DMARC Policy** | `p=quarantine` |
| **Attachment Filename** | `SWT_#09674321____PDF__.CAB` |
| **Attachment SHA-256** | `2e91c533615a9bb8929ac4bb76707b2444597ce063d84a4b33525e25074fff3f` |
| **Malware Family** | Trojan.MSIL/Loki (LokiBot / Kryptik) |





# Snapped Phish-ing Line – TryHackMe Writeup

## Overview
This writeup documents the step-by-step investigation of the **Snapped Phish-ing Line** challenge room on TryHackMe. The objective is to analyze a captured phishing kit, trace its internal mechanisms, inspect server configurations, identify exfiltrated data pathways, and recover the hidden flag.

---

## Lab Execution & Findings

### Step 1: Initial Lab Environment Setup
The target Virtual Machine was booted up to access the dedicated forensic analysis desktop environment. This provided access to the terminal, web browser, and local file system required for the investigation.
![Initial Setup]<img width="674" height="644" alt="1 1" src="https://github.com/user-attachments/assets/05fb0f05-61de-4d82-80d0-dfd8d2c0fa89" />

### Step 2: Investigating the Web Server Root Directory
Navigated to `/var/www/html/` to list all web documents and discover directory structures. This revealed the underlying files and folders making up the hosted phishing site.
![Directory Listing]<img width="678" height="646" alt="1 2" src="https://github.com/user-attachments/assets/736c5079-5b38-48ce-9b08-ec237072d445" />

### Step 3: Analyzing `index.php` Source Code
Inspected `index.php` using a text editor to analyze how incoming HTTP requests are handled. The code revealed initial parameter checks and redirection rules used to route victims to the phishing page.
![index.php Analysis]<img width="676" height="645" alt="1 3" src="https://github.com/user-attachments/assets/5388bbc0-79b9-4ecf-927d-628f95aa8fef" />

### Step 4: Extracting Network Connections (`netstat`)
Executed `netstat -tuln` in the terminal to inspect all active listening ports and network connections. This verified which web and service ports were actively running on the host.
![Netstat Execution]<img width="668" height="647" alt="1 4" src="https://github.com/user-attachments/assets/4ede007e-3cbd-4576-b429-941b2f6677b5" />

### Step 5: Checking Running Processes (`ps aux`)
Ran `ps aux` to trace running system processes and identify active web services. This confirmed Apache and PHP background processes were executing from the web directory.
![Process Listing]<img width="673" height="641" alt="1 5" src="https://github.com/user-attachments/assets/d7bdae94-4581-42f4-8c30-d75c7aab80e8" />

### Step 6: Reviewing Web Server Virtual Host Configuration
Inspected `/etc/apache2/sites-enabled/` to examine active Apache site configurations. This uncovered active domain aliases, document roots, and path rewrite rules configured on the server.
![Apache Config]<img width="1365" height="646" alt="1 6" src="https://github.com/user-attachments/assets/1358d5cb-ea5b-41dc-b0c4-62775880431c" />

### Step 7: Inspecting Phishing Directory Structure
Navigated directly to the extracted phishing kit directory to identify processing scripts and asset folders. This mapped out the core files responsible for handling victim interactions.
![Phishing Kit Directory]<img width="1365" height="646" alt="1 7" src="https://github.com/user-attachments/assets/52c88667-247b-40fd-b2b1-2ab01f0aca30" />

### Step 8: Examining Credential Capture Logic
Reviewed the core processing script to determine how user input is captured and formatted. The script constructs log entries containing captured emails, passwords, victim IP addresses, and User-Agent strings.
![Credential Processing Logic]<img width="670" height="645" alt="1 8" src="https://github.com/user-attachments/assets/7c5c80c5-8bfd-476f-8d21-808ec8d6e117" />

### Step 9: Locating Stored Victim Credentials
Searched the phishing kit files to locate where captured credentials and telemetry are saved locally. Discovered log files used by the attacker to temporarily store intercepted credentials.
![Exfiltrated Logs]<img width="671" height="645" alt="1 9" src="https://github.com/user-attachments/assets/3a8381e6-e758-4658-a65e-e5ee15afa5c7" />

### Step 10: Tracing Exfiltration Mail Routing Configuration
Inspected `submit.php` to identify how captured data is transmitted externally. The script compiles victim credentials into an email payload for exfiltration via PHP mail functions.
![Exfiltration Configuration]<img width="679" height="647" alt="1 10" src="https://github.com/user-attachments/assets/169ab471-253c-4a83-9a2d-5c7e86494f24" />

### Step 11: Identifying Attacker Email & C2 Infrastructure
Analyzed line 49 of `submit.php` to extract hardcoded attacker details. The variable `$send` revealed the attacker's primary exfiltration address as `m3npat@yandex.com`.
![Attacker C2 Details]<img width="680" height="644" alt="1 11" src="https://github.com/user-attachments/assets/3460a372-b38c-4858-8a52-9000d917f2f0" />

### Step 12: Triggering the Flag / Secret Output
Navigated to the target endpoint using the Firefox browser to execute the final stage of the kit script. This successfully rendered the hidden secret key directly in the browser output.
* **Secret Key:** `fUxSVV8zSHRfaFQxd195NExwe01VAo=`
![Secret Flag Extraction]<img width="680" height="646" alt="1 12" src="https://github.com/user-attachments/assets/2ab66d76-d09e-4764-b1e0-1c27463f210e" />

### Step 13: Lab Completion
Submitted the extracted flag into the TryHackMe platform. The flag was verified successfully, completing the **Snapped Phish-ing Line** challenge.
![Lab Completion]<img width="1365" height="646" alt="1 13" src="https://github.com/user-attachments/assets/33c8ccf7-25ba-43b3-8e0c-5f55704de4d4" />

---

## Key Findings & Security Summary

| Parameter | Extracted Detail |
| :--- | :--- |
| **Phishing Target** | Microsoft Office365 / Outlook Update |
| **Attacker Exfiltration Email** | `m3npat@yandex.com` |
| **Primary Artifact Script** | `submit.php` |
| **Captured Secret / Flag** | `fUxSVV8zSHRfaFQxd195NExwe01VAo=` |




# TryHackMe: Traffic Analysis Basics Write-up

This repository contains the walkthrough, answers, and network traffic analysis process for the **Traffic Analysis Basics** room on TryHackMe.

---

## 🚀 Room Overview

* **Room Name:** Traffic Analysis Basics
* **Category:** Network Security / Traffic Analysis
* **Platform:** [TryHackMe](https://tryhackme.com/)

---

## 🛠️ Walkthrough & Analysis

### Scenario 1: Basic Web & File Traffic Analysis

In this exercise, network topology and HTTP session details were analyzed to trace file downloads from external endpoints.

#### Network Topology Setup
![Network Topology - Scenario 1]<img width="666" height="646" alt="1 1" src="https://github.com/user-attachments/assets/c228d137-10c7-445d-a42a-5dbeefaf37b0" />

#### HTTP Packet Details
* **Source IP:** `203.0.113.200`
* **Destination IP:** `192.168.0.3`
* **Requested File / Attachment:** `install.ps1`
* **HTTP Status Code:** `200 OK`

![HTTP Packet Details]<img width="669" height="647" alt="1 2" src="https://github.com/user-attachments/assets/7650476b-75f1-4324-b9a0-fc0651a91d85" />

---

### Scenario 2: DNS Infiltration Investigation

A workstation on the network was compromised, and malicious Command and Control (C2) instructions were transmitted via DNS TXT records.

#### Identifying the Optimal Tap Placement
To capture all DNS traffic efficiently, the network tap must be placed directly in front of the primary DNS server (`SRV-DNS`), as all external host DNS queries and replies route through this point.

![DNS Infiltration Challenge Interface](<img width="671" height="645" alt="2 1" src="https://github.com/user-attachments/assets/a5e69485-aee9-4957-a1ea-79e2ae7edecf" />
![Network Topology Map]<img width="670" height="645" alt="2 2" src="https://github.com/user-attachments/assets/b0b4dbf2-2f68-4603-91c8-009c532df0af" />
![Correct TAP Placement on SRV-DNS]<img width="667" height="647" alt="2 3" src="https://github.com/user-attachments/assets/ee5852d6-6dd6-43aa-be83-af730826f050" />

#### DNS Packet Stream Analysis
Once the TAP was configured, DNS traffic streams were inspected for high-entropy or unexpected TXT record queries.

![Captured DNS Packet Log]<img width="675" height="647" alt="2 4" src="https://github.com/user-attachments/assets/62c71e2c-e856-4479-8ee5-f8a3cf9962fe" />

#### Extracting the Flag from DNS TXT Record
* **Queried Domain:** `c2.tryhackme.thn`
* **Query Type:** `TXT/IN`

![DNS TXT Response Payload]<img width="662" height="407" alt="2 5" src="https://github.com/user-attachments/assets/10ca588e-191b-429b-8e59-d5a5765a7c64" />

---

## 🎉 Room Completion

![Room Completion Badge]<img width="1365" height="645" alt="3" src="https://github.com/user-attachments/assets/2fe480c8-df87-43d3-acd1-5d4ab91be930" />

