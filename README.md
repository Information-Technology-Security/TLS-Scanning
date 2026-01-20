<p align="center">
  <img src="https://www.especial.gr/wp-content/uploads/2019/03/panepisthmio-dut-attikhs.png" alt="UNIWA" width="150"/>
</p>

<p align="center">
  <strong>UNIVERSITY OF WEST ATTICA</strong><br>
  SCHOOL OF ENGINEERING<br>
  DEPARTMENT OF COMPUTER ENGINEERING AND INFORMATICS
</p>

<hr/>

<p align="center">
  <strong>Information Technology Security</strong>
</p>

<h1 align="center" style="letter-spacing: 1px;">
  TLS Scanning
</h1>

<p align="center">
  <strong>Vasileios Evangelos Athanasiou</strong><br>
  Student ID: 19390005
</p>

<p align="center">
  <a href="https://github.com/Ath21" target="_blank">GitHub</a> ·
  <a href="https://www.linkedin.com/in/vasilis-athanasiou-7036b53a4/" target="_blank">LinkedIn</a>
</p>

<hr/>

<p align="center">
  <strong>Supervision</strong>
</p>

<p align="center">
  Supervisor: Ioanna Kantzavelou, Associate Professor<br>
</p>

<p align="center">
  <a href="https://ice.uniwa.gr/en/emd_person/ioanna-kantzavelou/" target="_blank">UNIWA Profile</a> ·
  <a href="https://www.linkedin.com/in/ioanna-kantzavelou-74685934/" target="_blank">LinkedIn</a>
</p>


<p align="center">
  Co-supervisor: Angelos Georgoulas, Assistant Professor<br>
</p>

<p align="center">
  <a href=https://scholar.google.com/citations?user=Djium2IAAAAJ&hl=en" target="_blank">UNIWA Profile</a> ·
  <a href="https://www.linkedin.com/in/aggelos-georgoulas/?originalSubdomain=uk" target="_blank">LinkedIn</a>
</p>

</hr>


<p align="center">
  Athens, June 2023
</p>


---

# Project Overview

This laboratory project involves a comprehensive security analysis of the **Transport Layer Security (TLS)** protocol across different categories of websites. The primary objective is to identify vulnerabilities related to **outdated protocol versions**, **weak cipher suites**, and known **SSL/TLS attacks** using both web-based and locally installed scanning tools.

---

## Table of Contents

| Section | Path / File | Description |
|--------:|-------------|-------------|
| 1 | `assign/` | Official laboratory exercise specifications |
| 1.1 | `assign/Excercise 5 (TLS Scanning)_2023.pdf` | Assignment description (English) |
| 1.2 | `assign/Άσκηση 5 (TLS Scanning)_2023.pdf` | Assignment description (Greek) |
| 2 | `docs/` | Technical analysis and TLS security documentation |
| 2.1 | `docs/TLS-Scanning.pdf` | TLS scanning report and results (English) |
| 2.2 | `docs/Σάρωση-TLS.pdf` | TLS scanning report and results (Greek) |
| 3 | `screens/` | TLS scan outputs, certificate analysis, and vulnerability evidence |
| 3.1 | `screens/*Home.png` | Target website home pages before scanning |
| 3.2 | `screens/Scan-Python-*.png` | TLS scans executed via Python scripts |
| 3.3 | `screens/Run-Python-Script-*.png` | Execution of custom TLS scanning scripts |
| 3.4 | `screens/SSL-Report-*.png` | SSL/TLS report summaries per target |
| 3.5 | `screens/Certificates*.png` | Certificate type and key analysis (RSA / EC) |
| 3.6 | `screens/Forum-*.png` | Detected TLS weaknesses and misconfigurations |
| 4 | `README.md` | Repository overview and experiment description |

---

## Laboratory Environment
The security assessments were conducted in the following environment:

- **Operating System:** Ubuntu 16.04 (Linux Virtual Machine)
- **Python Version:** Python 2 (required for the A2SV tool)

---

## Tools Used
Two main tools were utilized for TLS vulnerability scanning:

- **Qualys SSL Labs (Web Tool):**  
  Performs in-depth analysis of public SSL/TLS server configurations, including certificate chains, protocol support, and cipher suites.

- **A2SV (Auto Scanning to SSL Vulnerability):**  
  A Python-based local scanning tool designed to detect common SSL/TLS vulnerabilities such as **HeartBleed**, **CRIME**, **DROWN**, and **POODLE**.

---

## Target Websites
The analysis was performed on four different categories of websites:

- **Online Store:** https://www.e-shop.gr/
- **News Website:** https://www.newsbomb.gr/
- **University Website:** https://www.hua.gr/
- **Suspicious Website:** https://www.blackboxresale.com/

---

## Vulnerabilities Assessed
The scanners evaluated the presence of the following critical TLS/SSL vulnerabilities:

- **CRIME & BREACH:** Compression-based attacks that can leak sensitive data.
- **HeartBleed:** A severe vulnerability in the OpenSSL library allowing memory disclosure.
- **POODLE:** An attack exploiting fallback mechanisms to SSL 3.0.
- **Weak Cipher Suites:** Detection of insecure algorithms such as RC4.
- **Protocol Support:** Verification of continued support for deprecated TLS versions (TLS 1.0 and 1.1).

---

## How to Run the Local Scanner (A2SV)

To perform a TLS vulnerability scan using the A2SV tool:

1. Navigate to the tool’s directory:
   ```bash
   cd a2sv
   ```
2. Execute the scan against a target IP address:
    ```bash
    python2 a2sv.py -t [Target_IP_Address]
    ```

---

## Key Findings
#### Protocol Support:
Several tested websites were limited to a “B” security grade due to continued support for TLS 1.0 and TLS 1.1, which are considered deprecated and vulnerable compared to TLS 1.3.

### Tool Comparison:
Both scanning tools generally agreed on the detected vulnerabilities.
- Qualys SSL Labs provided more extensive details on certificates and server configuration.
- A2SV focused primarily on identifying specific exploit vectors and known TLS/SSL attacks.

---

## Conclusion
This laboratory exercise demonstrates the importance of regularly auditing SSL/TLS configurations. Even well-known and widely used websites may expose unnecessary risk by supporting outdated protocols or weak cipher suites. Combining web-based and local scanning tools offers a more complete and reliable TLS security assessment.  

---

# Installation & Setup Guide

This guide describes how to prepare the laboratory environment and install the required tools for conducting TLS/SSL vulnerability scanning as part of the TLS Scanning laboratory exercise.

## Prerequisites
### 1. Host System Requirements
- Host OS: Windows / Linux / macOS
- Virtualization Software:
  - Oracle VirtualBox (recommended)
- Minimum Hardware:
  - 4 GB RAM (8 GB recommended)
  - CPU with virtualization support enabled
  - ~10 GB free disk space

### 2. Virtual Machine Environment
All experiments are conducted inside a Linux virtual machine.
- Operating System: Ubuntu 16.04 LTS
- Architecture: 32-bit or 64-bit
- Purpose: Execution of local TLS scanning tools (A2SV) and Python scripts

> Important: Ubuntu 16.04 is required due to compatibility with Python 2, which is mandatory for the A2SV scanner.

---

## Virtual Machine Setup
### Step 1: Create or Import Ubuntu 16.04 VM
Create a new VirtualBox virtual machine or import an existing Ubuntu 16.04 image.
Recommended settings:
- RAM: ≥ 2048 MB
- CPU: ≥ 1 core

Complete the Ubuntu 16.04 installation.

### Step 2: Update System Packages
After logging into the VM:
```bash
sudo apt update
sudo apt upgrade
```

---

## Software Installation
### Step 3: Install Python 2 (Required)
Ubuntu 16.04 includes Python 2 by default, but verify installation:
```bash
python2 --version
```
If not installed:
```bash
sudo apt install python
```

### Step 4: Install Required Python Libraries
Some TLS scanning scripts require additional Python modules:
```bash
sudo apt install python-openssl python-requests
```

### Step 5: Install Git
```bash
sudo apt install git
```
Verify:
```bash
git --version
```

---

## Repository Setup
### Step 6: Clone the Repository
```bash
git clone https://github.com/Information-Technology-Security/TLS-Scanning.git
cd TLS-Scanning
```

---

## A2SV Tool Setup
### Step 7: Navigate to A2SV Directory
```bash
cd a2sv
```
Ensure the main script exists:
```bash
ls
```
Expected output includes:
```bash
a2sv.py
```

---

## Supporting Python files
### Step 8: Verify Script Permissions
```bash
chmod +x a2sv.py
```

---

## Running the TLS Scanner
### Step 9: Execute a TLS Vulnerability Scan
Run the A2SV scanner against a target IP address:
```bash
python2 a2sv.py -t <TARGET_IP_ADDRESS>
```
Example:
```bash
python2 a2sv.py -t 8.8.8.8
```
The scanner will test for:
```bash
HeartBleed
CRIME
POODLE
DROWN
Weak cipher suites
Deprecated TLS versions
```

---

## Web-Based Scanning Tool (Optional)
In parallel with local scans, TLS configurations are analyzed using:
- Qualys SSL Labs: https://www.ssllabs.com/ssltest/

This tool is used for:
- Certificate chain analysis
- Cipher suite evaluation
- Protocol version grading
- No local installation is required.

---

## Ready-to-Use Environment
At this point, the system is fully configured for:
- Local TLS/SSL vulnerability scanning using A2SV
- Comparative analysis with Qualys SSL Labs
- Collection of screenshots and reports for documentation
- Proceed with the scanning experiments described in the Laboratory Exercise.

---

## Notes & Troubleshooting
- Always use Python 2, not Python 3.
- Some websites block aggressive scanning; results may vary.
- Prefer scanning IP addresses instead of domain names when using A2SV.
- Ubuntu 16.04 is deprecated but required for legacy tool compatibility.

---

## Open the Documentation
1. Navigate to the `docs/` directory
2. Open the report corresponding to your preferred language:
    - English: `TLS-Scanning.pdf`
    - Greek: `Σάρωση-TLS.pdf`