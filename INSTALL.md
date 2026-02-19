<p align="center">
  <img src="https://www.especial.gr/wp-content/uploads/2019/03/panepisthmio-dut-attikhs.png" alt="UNIWA" width="150"/>
</p>

<p align="center">
  <strong>UNIVERSITY OF WEST ATTICA</strong><br>
  SCHOOL OF ENGINEERING<br>
  DEPARTMENT OF COMPUTER ENGINEERING AND INFORMATICS
</p>

<p align="center">
  <a href="https://www.uniwa.gr" target="_blank">University of West Attica</a> ·
  <a href="https://ice.uniwa.gr" target="_blank">Department of Computer Engineering and Informatics</a>
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
  <a href=https://scholar.google.com/citations?user=Djium2IAAAAJ&hl=en" target="_blank">Scholar</a> ·
  <a href="https://www.linkedin.com/in/aggelos-georgoulas/?originalSubdomain=uk" target="_blank">LinkedIn</a>
</p>

</hr>

---

<p align="center">
  Athens, June 2023
</p>

---

<p align="center">
  <img src="https://miro.medium.com/0*M-iAUj9XhwWPH-nS" width="250"/>
</p>

---

# INSTALL

## TLS Scanning

This guide describes how to prepare the laboratory environment and install the required tools for conducting TLS/SSL vulnerability scanning as part of the TLS Scanning laboratory exercise.

---

## 1. Prerequisites

### 1.1 Host System Requirements

- Host OS: Windows / Linux / macOS
- Virtualization Software:
  - Oracle VirtualBox (recommended)
- Minimum Hardware:
  - 4 GB RAM (8 GB recommended)
  - CPU with virtualization support enabled
  - ~10 GB free disk space

### 1.2 Virtual Machine Environment

All experiments are conducted inside a Linux virtual machine.

- Operating System: Ubuntu 16.04 LTS
- Architecture: 32-bit or 64-bit
- Purpose: Execution of local TLS scanning tools (A2SV) and Python scripts

> Important: Ubuntu 16.04 is required due to compatibility with Python 2, which is mandatory for the A2SV scanner.

---

## 2. Virtual Machine Setup

### 2.1 Create or Import Ubuntu 16.04 VM

Create a new VirtualBox virtual machine or import an existing Ubuntu 16.04 image.
Recommended settings:

- RAM: ≥ 2048 MB
- CPU: ≥ 1 core

Complete the Ubuntu 16.04 installation.

### 2.2 Update System Packages

After logging into the VM:

```bash
sudo apt update
sudo apt upgrade
```

---

## 3. Software Installation

### 3.1 Install Python 2 (Required)

Ubuntu 16.04 includes Python 2 by default, but verify installation:

```bash
python2 --version
```

If not installed:

```bash
sudo apt install python
```

### 3.2 Install Required Python Libraries

Some TLS scanning scripts require additional Python modules:

```bash
sudo apt install python-openssl python-requests
```

### 3.3 Install Git

```bash
sudo apt install git
```

Verify:

```bash
git --version
```

---

## 4. Repository Setup

### 4.1 Clone the Repository

```bash
git clone https://github.com/Information-Technology-Security/TLS-Scanning.git
cd TLS-Scanning
```

---

## 5. A2SV Tool Setup

### 5.1 Navigate to A2SV Directory

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

## 6. Supporting Python files

### 6.1 Verify Script Permissions

```bash
chmod +x a2sv.py
```

---

## 7. Running the TLS Scanner

### 7.1 Execute a TLS Vulnerability Scan

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

## 8. Web-Based Scanning Tool

In parallel with local scans, TLS configurations are analyzed using:

- Qualys SSL Labs: https://www.ssllabs.com/ssltest/

This tool is used for:

- Certificate chain analysis
- Cipher suite evaluation
- Protocol version grading
- No local installation is required.

---

## 9. Ready-to-Use Environment

At this point, the system is fully configured for:

- Local TLS/SSL vulnerability scanning using A2SV
- Comparative analysis with Qualys SSL Labs
- Collection of screenshots and reports for documentation
- Proceed with the scanning experiments described in the Laboratory Exercise.

---

## 10. Notes & Troubleshooting

- Always use Python 2, not Python 3.
- Some websites block aggressive scanning; results may vary.
- Prefer scanning IP addresses instead of domain names when using A2SV.
- Ubuntu 16.04 is deprecated but required for legacy tool compatibility.

---

## 11. Open the Documentation

1. Navigate to the `docs/` directory
2. Open the report corresponding to your preferred language:
   - English: `TLS-Scanning.pdf`
   - Greek: `Σάρωση-TLS.pdf`
