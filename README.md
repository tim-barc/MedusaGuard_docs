# MedusaGuard 🛡️  
**Your Enterprise's Shield Against Vulnerabilities**

![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg) ![OpenVAS](https://img.shields.io/badge/Tool-OpenVAS-green.svg) ![Nuclei](https://img.shields.io/badge/Tool-Nuclei-yellow.svg) ![Nikto](https://img.shields.io/badge/Tool-Nikto-orange.svg) ![Metasploit](https://img.shields.io/badge/Tool-Metasploit-red.svg)

---

## Automated Vulnerability Detection and Exploitation Tool for Enhanced Security

**MedusaGuard** is an all-in-one solution integrating **Nikto**, **Greenbone OpenVAS**, **Nuclei**, and **Metasploit** to automate vulnerability detection and controlled exploitation, empowering enterprises to stay ahead of emerging threats with real-time protection.

---

## 📜 **Table of Contents**
1. [Project Overview](#project-overview)
2. [Technologies Used](#technologies-used)
   - [Nikto](#nikto)
   - [Greenbone OpenVAS](#greenbone-openvas)
   - [Nuclei](#nuclei)
   - [Metasploit Framework](#metasploit-framework)
3. [Key Features](#key-features)
   - [Periodic Automated Testing](#periodic-automated-testing)
   - [Advanced Exploitation Automation](#advanced-exploitation-automation)
   - [Interactive Dashboard for Reports](#interactive-dashboard-for-reports)
4. [Installation](#installation)
5. [Quick Start](#quick-start)
6. [Troubleshooting](#troubleshooting)
7. [Getting Started Guide](#getting-started-guide)
8. [Sample Reports](#sample-reports)
9. [API Commands](#api-commands)
10. [License](#license)
11. [Credits](#credits)

---

## **Project Overview**

**MedusaGuard** is an advanced automated vulnerability detection and exploitation tool designed to enhance the security of enterprise environments by identifying and exploiting vulnerabilities. Through automation, MedusaGuard offers continuous monitoring, enabling early detection and controlled mitigation of vulnerabilities **before** malicious actors can exploit them.

MedusaGuard integrates well-established open-source tools—**Nikto**, **Greenbone OpenVAS**, **Nuclei**, and **Metasploit**—for comprehensive vulnerability scanning and exploitation. It prioritizes security while maintaining system availability and integrity, ensuring that no harmful payloads are delivered during scans.

---

## **Technologies Used**

#### Nikto
A web server vulnerability scanner that quickly identifies common issues such as outdated software, misconfigurations, and potentially dangerous files. Nikto helps facilitate prompt resolution of these vulnerabilities.

#### Greenbone OpenVAS
An advanced open-source vulnerability scanning tool that ensures comprehensive network infrastructure assessment, backed by a vast and regularly updated vulnerability database.

#### Nuclei
A highly efficient, template-based vulnerability scanner that detects security flaws across various applications and infrastructure components.

#### Metasploit Framework
Used for controlled exploitation of identified vulnerabilities to safely validate their impact in real-world scenarios without compromising system integrity.

---

## **Key Features**

#### Periodic Automated Testing
Automated scheduling of scans at regular intervals provides **continuous monitoring** of network environments for new vulnerabilities.

#### Advanced Exploitation Automation
Automatically maps detected vulnerabilities to corresponding exploits, streamlining the exploitation process to validate security issues more efficiently.

#### Interactive Dashboard for Reports
A GUI-based dashboard provides real-time insights into vulnerabilities, along with both technical and non-technical reports, making it accessible for all stakeholders—from security analysts to executive decision-makers.

---

## **Installation**

Follow these steps to install MedusaGuard:

```bash
# Clone the repository
git clone https://github.com/LukeyBoyy/MedusaGuard.git

# Navigate to the directory
cd MedusaGuard

# Install necessary dependencies
sudo pip3 install -r requirements.txt
```

---

## **Quick Start**

After installation, follow these instructions to start using MedusaGuard:

#### **Running the GUI**

To launch MedusaGuard with a graphical user interface, run the following command:

```bash
sudo python3 medusaguard.py
```

#### **Running the CLI**

For command-line usage, run the following command (executing MedusaGuard using configuration details in `config.ini`):

```bash
sudo python3 main.py
```

To display the help menu for CLI options:

```bash
-h  --help  -help
```

The help menu provides a list of available arguments and usage examples to guide you through configuration:

```plaintext
usage: main.py [-h] [--config CONFIG] [--username USERNAME] [--password PASSWORD] ...
```

---

## **Troubleshooting**

This section outlines common issues and recommended solutions.

#### Externally-Managed Environment During Python Script Execution
- **Cause**: Conflicting package management configurations.
- **Solution**: Use a virtual environment (`venv`) or `pyenv`.

#### Greenbone Timeout or Connection Reset
- **Cause**: Scanning too many hosts or insufficient resources.
- **Solution**: Restart GVM services, reduce target hosts, or increase machine resources.

#### Socket `/run/gvmd/gvmd.sock` Does Not Exist
- **Cause**: GVM services not running.
- **Solution**: Run `gvm-start`.

#### Metasploit RPC Connection Fails
- **Cause**: Metasploit RPC server not reachable.
- **Solution**: Ensure Metasploit’s RPC server is running.

---

## **Getting Started Guide**

For more in-depth instructions, refer to the [MedusaGuard - Getting Started Guide](https://github.com/user-attachments/files/17359582/MedusaGuard.-.Getting.Started.Guide.pdf).

---

## **Sample Reports**

View sample reports generated by MedusaGuard [here](https://drive.google.com/drive/folders/1V1qrzmowVSx53C1W2zsUx3odLh-tbkJG?usp=sharing).

---

## **API Commands**

#### GVM Commands
```python
gmp.authenticate(username, password)
gmp.create_target(name=target_name, hosts=[hosts], ...)
```

#### Metasploit Commands
```python
MsfRpcClient(password, server=server, ...)
client.modules.use('exploit', exploit_name)
```

---

## **License**

This project is licensed under the terms of the [Apache License Version 2.0](https://www.apache.org/licenses/LICENSE-2.0).

---

## **Credits**

Special thanks to the following contributors:

- **Conner Dogger**  — [GitHub: DogLogik](https://github.com/DogLogik)
- **Costa Spandideas**  — [GitHub: cozzie19](https://github.com/cozzie19)
- **Luke Alexander**  — [GitHub: LukeyBoyy](https://github.com/LukeyBoyy)
- **Mark Kerleroux**  — [GitHub: MarkK-LaTrobe](https://github.com/MarkK-LaTrobe)
- **Timothy Barclay**  — [GitHub: tim-barc](https://github.com/tim-barc)

---

