# 🔍 Splunk SIEM Log Analysis Project

> A complete hands-on cybersecurity project using **Splunk** as a **SIEM (Security Information and Event Management)** tool.  
> This project demonstrates how to **install, configure, and use Splunk** to analyze various types of logs such as DNS, SSH, and HTTP logs — and detect suspicious or unauthorized access activities.  
> Ideal for SOC Analysts, Cybersecurity Students, and Beginners learning Splunk for threat detection and log analysis.

---

## 📘 Table of Contents
1. [Project Overview](#project-overview)
2. [Learning Objectives](#learning-objectives)
3. [Tools & Setup](#tools--setup)
4. [Step 1 — Install and Configure Splunk](#step-1--install-and-configure-splunk)
5. [Step 2 — DNS Log Analysis](#step-2--dns-log-analysis)
6. [Step 3 — SSH Log Analysis](#step-3--ssh-log-analysis)
7. [Step 4 — HTTP Log Analysis](#step-4--http-log-analysis)
8. [Step 5 — Investigating Unauthorized Access](#step-5--investigating-unauthorized-access)
9. [Results and Screenshots](#results-and-screenshots)
10. [Author & Credits](#author--credits)

---

## 🧠 Project Overview
This project focuses on building a **SIEM environment using Splunk** to perform practical log analysis and security monitoring.  
You will learn how to ingest logs, write **SPL (Search Processing Language)** queries, and identify security events such as brute-force attacks, server errors, and unauthorized access.

---

## 🎯 Learning Objectives
- Install and configure Splunk Enterprise on Ubuntu  
- Ingest and analyze DNS, SSH, and HTTP logs  
- Detect anomalies and suspicious activities  
- Develop SOC-style investigation and reporting skills  
- Gain experience using SPL for real-world incident analysis  

---

## 🧰 Tools & Setup
| Component | Description |
|------------|-------------|
| **System** | Ubuntu 22.04 / 20.04 (Server or Desktop) |
| **Tool** | Splunk Enterprise (Free version for local setup) |
| **Access** | Splunk Web Interface (port `8000`) |
| **Logs Used** | Zeek-formatted DNS, SSH, and HTTP logs (JSON) |

---

## 🧩 Step 1 — Install and Configure Splunk

### 🎯 Objective
The objective of this task is to help students **install and configure Splunk on an Ubuntu machine**.  
By completing this task, you will have **Splunk up and running** to collect and analyze security logs.

### 🖥️ Lab Setup

**Requirements**
- System: Ubuntu 22.04 / 20.04 (Server or Desktop)  
- Tools: Splunk Enterprise (Free version), Terminal access

---

### ⚙️ Steps to Install and Configure Splunk

#### Step 1: Download Splunk
Open Terminal and download Splunk using:

```bash
wget -O splunk-9.3.0-51ccf43db5bd-linux-2.6-amd64.deb "https://download.splunk.com/products/splunk/releases/9.3.0/linux/splunk-9.3.0-51ccf43db5bd-linux-2.6-amd64.deb"
```
Once the file is downloaded, verify it with:
```
ls -lh splunk-9.3.0-51ccf43db5bd-linux-2.6-amd64.deb
```

Then install Splunk using dpkg:
```
sudo dpkg -i splunk-9.3.0-51ccf43db5bd-linux-2.6-amd64.deb
```

⚠️ Note: If any dependency issues occur, fix them with:
```
sudo apt --fix-broken install
```
#### Step 2: Enable Splunk as a Service

Move to the Splunk installation directory:
```
cd /opt/splunk/bin

```
Accept the license agreement and enable Splunk to start automatically when the system boots:
```
sudo ./splunk enable boot-start --accept-license

```
Now, start the Splunk service:
```
sudo ./splunk start
```
<br>

---

## 🌐 Access Splunk Web Interface

Once Splunk is running, open your web browser and navigate to:
```
http://<your-server-ip>:8000
```

Example for local systems:
```
http://localhost:8000
```

Log in using the admin credentials you just created.

You should see the Splunk Web Dashboard, which allows you to search, add data, and configure your Splunk instance.

<br>


---


## 🧩 Verify Splunk Installation

After logging into Splunk Web, verify that Splunk is indexing internal logs correctly.

Go to Search & Reporting and run this SPL query:
```
index=_internal | stats count
```

If you receive a non-zero count, Splunk is working properly 🎉

## Manage Splunk Service (Optional Commands)

Start Splunk manually:
```
sudo /opt/splunk/bin/splunk start
```

Stop Splunk:
```
sudo /opt/splunk/bin/splunk stop
```

Restart Splunk:
```
sudo /opt/splunk/bin/splunk restart
```

Check Splunk status:
```
sudo /opt/splunk/bin/splunk status
```

