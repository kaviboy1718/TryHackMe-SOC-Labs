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
