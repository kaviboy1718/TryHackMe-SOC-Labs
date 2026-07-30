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
