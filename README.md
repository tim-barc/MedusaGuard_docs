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
7. [Sample Reports](#sample-reports)
8. [License](#license)
9. [Credits](#credits)

---

## **Project Overview**

**MedusaGuard** is an advanced automated vulnerability scanning and exploitation tool designed to enhance the security of small to larger environments by identifying and exploiting vulnerabilities. Through automation, MedusaGuard enables the early
detection and controlled exploitation of vulnerabilities. 

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

## **Troubleshooting Guide**  

This section lists common issues that may arise with MedusaGuard, along with recommended solutions.

#### Externally-Managed Environment During Python Script Execution
- **Cause**: Conflicts in package management, possibly due to recent installations.
- **Solution**: Consider using a virtual environment with `venv` or a Python version manager like `pyenv`. Alternatively (not recommended), ensure `pip` is configured correctly and run with `--break-system-packages`.

#### Greenbone Timeout or Connection Reset Issues
- **Cause**: Network resource or configuration constraints, likely a result of scanning too many hosts, packet loss, insufficient computing resources (CPU, RAM, etc.), or misconfigured scan configuration.
- **Solution**: Restart GVM services and run the scan again. Consider upgrading your machine or giving your VM more computing resources if the issue persists.

#### Socket `/run/gvmd/gvmd.sock` Does Not Exist
- **Cause**: GVM services are not running, or socket path has changed.
- **Solution**: Start GVM services by entering `gvm-start`, or ensure the socket path has not changed.

#### Greenbone Connectivity Issues
- **Cause**: The Greenbone services might not be running, or connection parameters may be incorrect.
- **Solution**: Verify that the Greenbone service is running (`gvm-start`), and check `config.ini` for correct socket path and credentials. If the problem persists, try reinstalling Greenbone or run `gvm-check-setup`.

#### Permission Denied or Elevated Privileges Required
- **Cause**: The tool requires `sudo` privileges to execute.
- **Solution**: Execute the script with `sudo` privileges (i.e., `sudo python3 medusaguard.py`).

#### Unable to Detect the URI-Scheme of `<file-path>`
- **Cause**: File path does not exist.
- **Solution**: Start the scan or execute the `main.py` script, which will create all the required report directories.

#### Report Summary Results not Showing
- **Cause**: This issue typically only occurs right after installation, however it does not impact the tools operation whatsover (i.e., all reports still get generated). 
- **Solution**: Run another scan. 

#### Metasploit RPC Connection Fails
- **Cause**: The Metasploit RPC server might not be reachable.
- **Solution**: Ensure Metasploit’s RPC server is running and the credentials configured in `exploit_module.py` are correct.

#### Nuclei Update/Scan Fails
- **Cause**: Nuclei might require an update or template paths may be misconfigured.
- **Solution**: Run `nuclei -update` in the terminal and ensure template directories are accessible and correct.

#### Report Generation Errors or Missing Assets
- **Cause**: Missing dependencies, data files, or assets needed for reports.
- **Solution**: Ensure all dependencies have been installed, check for required image assets in `/assets`, and investigate the log file for detailed error messages if errors persist.

#### Subprocess `TimeoutExpired` Errors
- **Cause**: Long-running scans, especially on large networks, may exceed the set timeout (1 hour).
- **Solution**: Increase timeout values directly in the `nikto_utils.py`, `openvas_utils.py`, and `nuclei_utils.py` scripts. You can do this by adjusting the `timeout` parameter in `subprocess.run()` calls.

---

## **Sample Reports**

View sample reports generated by MedusaGuard [here](https://drive.google.com/drive/folders/1V1qrzmowVSx53C1W2zsUx3odLh-tbkJG?usp=sharing).

---

## **Credits**

Special thanks to the following contributors:

- **Conner Dogger**  — [GitHub: DogLogik](https://github.com/DogLogik)
- **Costa Spandideas**  — [GitHub: cozzie19](https://github.com/cozzie19)
- **Luke Alexander**  — [GitHub: LukeyBoyy](https://github.com/LukeyBoyy)
- **Mark Kerleroux**  — [GitHub: MarkK-LaTrobe](https://github.com/MarkK-LaTrobe)
- **Timothy Barclay**  — [GitHub: tim-barc](https://github.com/tim-barc)

---

