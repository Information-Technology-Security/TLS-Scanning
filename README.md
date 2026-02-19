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

# README

## TLS Scanning

This laboratory project involves a comprehensive security analysis of the **Transport Layer Security (TLS)** protocol across different categories of websites. The primary objective is to identify vulnerabilities related to **outdated protocol versions**, **weak cipher suites**, and known **SSL/TLS attacks** using both web-based and locally installed scanning tools.

---

## Table of Contents

| Section | Path / File                                  | Description                                                        |
| ------: | -------------------------------------------- | ------------------------------------------------------------------ |
|       1 | `assign/`                                    | Official laboratory exercise specifications                        |
|     1.1 | `assign/Excercise 5 (TLS Scanning)_2023.pdf` | Assignment description (English)                                   |
|     1.2 | `assign/Άσκηση 5 (TLS Scanning)_2023.pdf`    | Assignment description (Greek)                                     |
|       2 | `docs/`                                      | Technical analysis and TLS security documentation                  |
|     2.1 | `docs/TLS-Scanning.pdf`                      | TLS scanning report and results (English)                          |
|     2.2 | `docs/Σάρωση-TLS.pdf`                        | TLS scanning report and results (Greek)                            |
|       3 | `screens/`                                   | TLS scan outputs, certificate analysis, and vulnerability evidence |
|     3.1 | `screens/*Home.png`                          | Target website home pages before scanning                          |
|     3.2 | `screens/Scan-Python-*.png`                  | TLS scans executed via Python scripts                              |
|     3.3 | `screens/Run-Python-Script-*.png`            | Execution of custom TLS scanning scripts                           |
|     3.4 | `screens/SSL-Report-*.png`                   | SSL/TLS report summaries per target                                |
|     3.5 | `screens/Certificates*.png`                  | Certificate type and key analysis (RSA / EC)                       |
|     3.6 | `screens/Forum-*.png`                        | Detected TLS weaknesses and misconfigurations                      |
|       4 | `README.md`                                  | Project documentation                                              |
|       5 | `INSTALL.md`                                 | Usage instructions                                                 |

---

## 1. Laboratory Environment

The security assessments were conducted in the following environment:

- **Operating System:** Ubuntu 16.04 (Linux Virtual Machine)
- **Python Version:** Python 2 (required for the A2SV tool)

---

## 2. Tools Used

Two main tools were utilized for TLS vulnerability scanning:

- **Qualys SSL Labs (Web Tool):**  
  Performs in-depth analysis of public SSL/TLS server configurations, including certificate chains, protocol support, and cipher suites.

- **A2SV (Auto Scanning to SSL Vulnerability):**  
  A Python-based local scanning tool designed to detect common SSL/TLS vulnerabilities such as **HeartBleed**, **CRIME**, **DROWN**, and **POODLE**.

---

## 3. Target Websites

The analysis was performed on four different categories of websites:

- **Online Store:** https://www.e-shop.gr/
- **News Website:** https://www.newsbomb.gr/
- **University Website:** https://www.hua.gr/
- **Suspicious Website:** https://www.blackboxresale.com/

---

## 4. Vulnerabilities Assessed

The scanners evaluated the presence of the following critical TLS/SSL vulnerabilities:

- **CRIME & BREACH:** Compression-based attacks that can leak sensitive data.
- **HeartBleed:** A severe vulnerability in the OpenSSL library allowing memory disclosure.
- **POODLE:** An attack exploiting fallback mechanisms to SSL 3.0.
- **Weak Cipher Suites:** Detection of insecure algorithms such as RC4.
- **Protocol Support:** Verification of continued support for deprecated TLS versions (TLS 1.0 and 1.1).

---

## 5. How to Run the Local Scanner (A2SV)

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

## 6. Key Findings

### 6.1 Protocol Support

Several tested websites were limited to a “B” security grade due to continued support for TLS 1.0 and TLS 1.1, which are considered deprecated and vulnerable compared to TLS 1.3.

### 6.2 Tool Comparison:

Both scanning tools generally agreed on the detected vulnerabilities.

- Qualys SSL Labs provided more extensive details on certificates and server configuration.
- A2SV focused primarily on identifying specific exploit vectors and known TLS/SSL attacks.

---

## 7. Conclusion

This laboratory exercise demonstrates the importance of regularly auditing SSL/TLS configurations. Even well-known and widely used websites may expose unnecessary risk by supporting outdated protocols or weak cipher suites. Combining web-based and local scanning tools offers a more complete and reliable TLS security assessment.
