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
4. [Installation](#installation)
5. [Quick Start Guide](#quick-start-guide)
   - [Running the GUI](#running-the-gui)
   - [Running the CLI](#running-the-cli)
6. [User Guide](#user-guide)
   - [Verifying GVM Services](#step-1-verifying-gvm-services)
   - [Verifying Nikto Installation](#step-2-verifying-nikto-installation)
   - [Verifying Nuclei Installation](#step-3-verifying-nuclei-installation)
   - [Verifying Metasploit Installation](#step-4-verifying-metasploit-installation)
   - [Launching MedusaGuard](#launching-medusaguard)
   - [Editing Configuration Setup](#editing-configuration-setup)
   - [Configuring Asset Criticality Score](#configuring-asset-criticality-score)
   - [Running Scans](#running-scans)
   - [Viewing Reports](#viewing-reports)
   - [Scheduling Scans](#scheduling-scans)
   - [Alternate Execution Method (CLI)](#alternate-execution-method-cli)
   - [Authenticated Scan](#authenticated-scan)
14. [Modifying Scripts](#modifying-scripts)
    - [Modifying Templates for Nuclei](#modifying-templates-for-nuclei)
    - [Modifying Timeout Settings for Long-Running Scans](#modifying-timeout-settings-for-long-running-scans)
    - [Changing Default Scan Configurations](#changing-default-scan-configurations)
    - [Customising Final Report](#customising-final-report)
    - [Integrating Additional Tools](#integrating-additional-tools)
15. [Troubleshooting Guide](#troubleshooting-guide)
16. [Sample Reports](#sample-reports)
17. [Credits](#credits)

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

##  **Installation**

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

<sup><span style="font-size: xxx-small;">[Back to top](#-table-of-contents)</span></sup>
---

## **User Guide**
Prior to running your first scan, please verify that you have the necessary services and tools installed, including **gvm**, **Nuclei**, **Nikto**, and **Metasploit**.

#### Step 1: Verifying GVM Services
Open a terminal in your Linux machine and enter the following command:

```bash
sudo gvm-start
```
![image](https://github.com/user-attachments/assets/bc394121-2ba4-4113-bc10-cbfa23f650fc)

#### Step 2: Verifying Nikto Installation
Open a terminal in your Linux machine and enter the following command:

```bash
nikto -Version
```
![image](https://github.com/user-attachments/assets/e51ec08f-0ffc-4143-8821-a184294ac6bd)

#### Step 3: Verifying Nuclei Installation
Open a terminal in your Linux machine and enter the following command:

```bash
nuclei -version
```
![image](https://github.com/user-attachments/assets/ce3403b8-6350-4817-9e34-7b6b88300425)

#### Step 4: Verifying Metasploit Installation
Open a terminal in your Linux machine and enter the following command:

```bash
msfconsole -v
```
![image](https://github.com/user-attachments/assets/5ed97628-7375-455e-b5eb-d9e9ca7fc6ee)

Additionally, verify **msfrpc** by running:

```bash
msfrpc
```
![image](https://github.com/user-attachments/assets/bca149b0-22d4-42ac-807e-d8f6964530a5)

---

## **Launching MedusaGuard**

Before configuring your scans, you need to launch MedusaGuard. Follow these steps:

#### Step 1: Navigate to MedusaGuard Directory
Open a terminal and navigate to the directory where `medusaguard.py` is located:

```bash
cd /path/to/MedusaGuard
```
![image](https://github.com/user-attachments/assets/e88a41b9-0093-43a3-bbc8-ca141389a41a)

#### Step 2: Run the MedusaGuard Script
Start the application by running the following command with superuser permissions:

```bash
sudo python3 medusaguard.py
```
![image](https://github.com/user-attachments/assets/dc21e091-21a9-4a02-a9ce-733e0d334ed3)

---

## **Editing Configuration Setup**

MedusaGuard includes an Edit Configuration page in the GUI to make it easy to set up and manage scan configurations for specific tasks.

#### Step 1: Access the Edit Configuration Page
- In the MedusaGuard GUI, navigate to the homepage (dashboard).
- Click the **Edit Config** button to open the configuration editor.

![image](https://github.com/user-attachments/assets/0d19fd60-03b2-4e8c-b5d3-cfa1a51d9d6f)

#### Step 2: Fill Out the Configuration Fields
Many of these fields come preconfigured. You only need to add your **Greenbone credentials**, **target name**, **task name**, and **target IP address(es)** before running your first scan.

- **Socket Path**: The path to the Unix socket for Greenbone Vulnerability Manager (GVM) communication (e.g., `/run/gvmd/gvmd.sock`).
- **Greenbone Username**: Username for Greenbone (OpenVAS) (e.g., `admin`).
- **Greenbone Password**: Password for your Greenbone account (e.g., `mypassword`).
- **Target Name**: Name of the scan target (e.g., `MyTargetServer`).
- **Target IP Address**: IP address of the target machine (e.g., `192.168.1.100`).

![image](https://github.com/user-attachments/assets/59027738-1b53-4bb9-94f6-6022b80295bf)

Once completed, press **Save**.

---

## **Configuring Asset Criticality Score**
Asset Criticality Score (ACS) configuration is not required, however, if you wish to apply an ACS from 1 to 5 for each asset click the Asset Criticality link in the sidebar:
![image](https://github.com/user-attachments/assets/18238dd2-c7da-4285-a39c-ddcf0ebbdefd)
This will open up the acs_scores.csv file:
![image](https://github.com/user-attachments/assets/0bf0d1a0-44a3-4e5f-b58b-4631d2e851dd)
In this file you can configure the ACS for each host you wish to scan, if you do not change or add a host ACS pairing, the default assigned to each host is 1, aka least critical. 
If you wish to configure an ACS score, simply add it like as follows:
![image](https://github.com/user-attachments/assets/be855c8d-762c-4f93-8688-e629dcf82609)
As you can see in the above image, there are two host ACS pairings, one for 192.168.100.6 with an ACS of 2 and one for 192.168.100.28 with an ACS of 5. The purpose of ACS
is to enable you to see what hosts are most critical in your environment, allowing you to better conduct remediation efforts. 

---

## **Running Scans**

#### Running Scans with the Main Script
When you press **Start Scan** on the main page, MedusaGuard's main script will execute, running all configured tools. The log window will display the logs of the scan, including the duration.
![image](https://github.com/user-attachments/assets/739ffb41-04ba-4df6-8b1a-a08b7627106e)

The following scans are triggered:
1. **Nuclei scan**
2. **Nikto scan**
3. **Greenbone scan**
4. **Metasploit exploitation**

A summary of the scan results will be displayed in the **Report Summary** after completion.
![image](https://github.com/user-attachments/assets/98b4c82e-c25f-4380-b309-f6e957e5c74b)

For detailed reports, access the full results in the specific folders listed on the left-hand side of the MedusaGuard interface:
- **Custom Reports**
- **Greenbone Reports**
- **Nuclei Results**
- **Metasploit Results**
- **Nikto Results**

![image](https://github.com/user-attachments/assets/39590654-8907-4fa5-a316-24e8d3c5bf9b)

---

## **Viewing Reports**

Full reports are available in the specific folders for each tool's scan. These folders contain the full CSV or text results, which can be further analyzed.

---

## **Scheduling Scans**

To schedule automated scans instead of running one-off scans, use the **Scan Scheduler** feature available in the MedusaGuard GUI.

#### Step 1: Access the Scan Scheduler
In the MedusaGuard interface, navigate to the left panel: **Config → Schedule Scan**.
![image](https://github.com/user-attachments/assets/2089bf78-8e44-40d3-acb2-17868cacb1aa)

#### Step 2: Configure the Schedule
In the **Schedule Scan** page, you can configure the scan schedule by filling out the following:
- **Comment**: Add a note about the scan (optional).
- **Starts On**: Select the date and time when the scan should start.
- **Time zone**: Choose the correct time zone for the scan.
- **Repeat Every**: Set how frequently the scan should repeat (e.g., daily, weekly).
![image](https://github.com/user-attachments/assets/dfc81ab1-504d-4600-b345-9353c23abb7a)

Once all scheduling details are configured, click **Save / Start** to begin the scheduled scan.
![image](https://github.com/user-attachments/assets/8ac2b0b7-5ebf-44d1-8cc0-37971ca7884c)
![image](https://github.com/user-attachments/assets/02b61528-cbc3-4f27-b1d0-9dc25ab99702)

---

## **Alternate Execution Method (CLI)**

If you prefer a more lightweight version of MedusaGuard, you can run it entirely through the command line.

#### Step 1: Navigate to MedusaGuard Directory
Open a terminal and navigate to the directory where `main.py` is located:

```bash
cd /path/to/MedusaGuard
```
![image](https://github.com/user-attachments/assets/cf5b0681-6f59-4511-afdc-0a35d7de99f3)

#### Step 2: Execute `main.py`
To start using MedusaGuard in the command line, explore the help output first by entering:

```bash
sudo python3 main.py -h
```
![image](https://github.com/user-attachments/assets/925dba6d-bb8f-4a5e-b300-1d3a8280750d)

#### Step 3: Running Your First Scan
To run a scan, enter the following command:

```bash
sudo python3 main.py
```
![image](https://github.com/user-attachments/assets/6082b6a5-ff71-40d4-bd4d-fb386a9de13c)

#### Step 4: Passing Arguments
To modify the scan configuration through the CLI, pass one or more arguments when executing the `main.py` script. For example, to change the task and target name, enter:
![image](https://github.com/user-attachments/assets/54591528-d6ef-4122-a617-146dcde4ba07)

```bash
sudo python3 main.py --task_name example --target_name example
```
![image](https://github.com/user-attachments/assets/7eff9ddf-a492-43c9-bc81-855d18ca3226)

<sup><span style="font-size: xxx-small;">[Back to top](#-table-of-contents)</span></sup>
---


## **Authenticated Scan**
Greenbone allows for both unauthenticated (default) and authenticated scans. If you wish to perform an unauthenticated scan on a public facing asset for example, all you need to do is execute MedusaGuard as normal.
If, however, you wish to run an authenticated scan against internal assets, you will need to navigate and authenticate to the GVM interface. Once you have done so, navigate to Configuration > Credentials:
![image](https://github.com/user-attachments/assets/49bae593-8d6e-4508-9ac0-6c058c74067a)

Once you are on this page, click the following button to add a new credential:
![image](https://github.com/user-attachments/assets/93b3967d-1912-4dfd-875b-c7140bb5aedc)
On this page, you want to configure the credential, in this example it is just a username and password pair: 
![image](https://github.com/user-attachments/assets/dc6bac66-cc7f-48bc-ad3a-58586347d077)
After clicking save, navigate to Configuration > Targets. On this page, click the following button to configure a new target:
![image](https://github.com/user-attachments/assets/9a416300-d66e-43e0-93bc-e867b4405b81)
When configuring the target, make sure to use the targets.txt file found in the MedusaGuard directory and in this instance, because we are scanning a Windows environment click SMB authentication and select the credentials you made previously:
![image](https://github.com/user-attachments/assets/39f6f3d1-08df-46b5-8425-bcce76f56d04)
It is recommended to create an account in your environment specially for vulnerability scanning that has access to systems you wish to scan. To run the scan in MedusaGuard, all you need to do is **make the target name in MedusaGuard the same as what you made on the GVM interface**. Also make sure to have the same assets in the targets.txt file and execute the scan as normal. 

<sup><span style="font-size: xxx-small;">[Back to top](#-table-of-contents)</span></sup>
---

## **Modifying Scripts**
MedusaGuard is open-source, and you may need to modify some of its scripts to suit your specific needs. Below are some common modifications and how to implement them:

#### **Modifying Templates for Nuclei** ####
If you'd prefer to expand on the current Nuclei templates being used, you can do this by editing the following section of the 'nuclei_utils.py' file:
```python
# Define the Nuclei scan commands to execute
nuclei_commands = {
   "network": "nuclei -target {} -t network/ -o {}",
   # "http": "nuclei -target {} -t http/ -o {}",
   # "rdp": "nuclei -target rdp://{} -o {}"
   # You can add more scan types and their corresponding commands here
}
```


This is where you can remove, add, or modify Nuclei templates. For context, Nuclei templates is how vulnerabilities are identified, so HTTP templates for example can identify HTTP based vulnerabilities. 

#### **Modifying Timeout Settings for Long-Running Scans**
If you find that scans are timing out, you can increase the timeout settings in the relevant script files.

- **File**: `nikto_utils.py`, `openvas_utils.py`, `nuclei_utils.py`
- **Modification**: Locate the `subprocess.run()` calls and adjust the `timeout` parameter.

```python
subprocess.run(['nikto', '-h', target], timeout=3600)  # Timeout is an hour
```


#### **Changing Default Scan Configurations**
You may wish to change the default scan configurations used by MedusaGuard.

- **File**: `config.ini`
- **Modification**: Edit the default scan parameters such as **port lists**, and **scan configs** to better match your network environment.

```ini
[connection]
path = /run/gvmd/gvmd.sock
username = 
password = 

[target]
target_name = 
target_ip = targets.txt
port_list_name = 33d0cd82-57c6-11e1-8ed1-406186ea4fc5

[task]
task_name = 
scan_config = daba56c8-73ec-11df-a475-002264764cea
scanner = 08b69003-5fc2-4037-a479-93b440211c73
```

#### **Customising Final Report**
If you need to customize the final report, you can modify the 'report_utils.py' file. Each section of the report is commented accordinly, enabling you to add, modify, or remove sections.


#### **Integrating Additional Tools**
You might want to add new tools for scanning or exploitation to enhance MedusaGuard's capabilities. MedusaGuard is a module based tool, meaning you can add as many modules as desired to expand on the tools current capabilities
without ruining its current operations. 

- **File**: `main.py`
- **Modification**: Import the new tool’s library and add a function to execute it within the main scanning sequence.

```python
import new_tool

def run_new_tool(target):
    new_tool.scan(target)
```

Add the function call to the main scan execution flow:

```python
run_new_tool(target)
```

<sup><span style="font-size: xxx-small;">[Back to top](#-table-of-contents)</span></sup>
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

<sup><span style="font-size: xxx-small;">[Back to top](#-table-of-contents)</span></sup>
---

