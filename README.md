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

## 🌐 Project Background

In modern cybersecurity operations, **log analysis and threat detection** are the backbone of proactive defense. Every endpoint, network device, and application generates logs that hold valuable insights about potential security events.  
However, manually reviewing these logs is inefficient and prone to human error — that’s where **SIEM (Security Information and Event Management)** tools like **Splunk** become essential.

**Splunk** enables security teams to:
- Collect and centralize logs from multiple data sources.
- Parse and normalize data for uniform analysis.
- Correlate seemingly unrelated events.
- Detect malicious behavior through pattern recognition and automation.
- Visualize and report incidents through interactive dashboards.

By mastering Splunk, you gain the ability to think and operate like a **SOC (Security Operations Center) Analyst**, turning raw data into actionable intelligence.

---

## 🧩 Project Workflow Overview

This Splunk SIEM project is designed as a step-by-step practical lab series that mirrors real-world security monitoring tasks.  
Each phase of the project builds on the previous one, taking you from environment setup to complex log correlation and investigation.

| Step | Focus Area | Description |
|------|-------------|-------------|
| **Step 1** | Splunk Installation & Configuration | Set up Splunk on Ubuntu and prepare it for data ingestion. |
| **Step 2** | DNS Log Analysis | Ingest and analyze DNS logs to identify suspicious domains and query patterns. |
| **Step 3** | SSH Log Analysis | Detect failed logins, brute-force attempts, and unauthorized SSH activity. |
| **Step 4** | HTTP Log Analysis | Examine web server logs to find anomalies, large file transfers, and possible attacks. |
| **Step 5** | Investigation & Correlation | Combine multi-log insights to investigate unauthorized access and potential compromise. |

---


## 🚀 What’s Next?

With the foundation established, the next section — **Step 1: Install and Configure Splunk** — will walk you through setting up Splunk Enterprise on Ubuntu and preparing it to ingest security logs.

👉 Continue to [Step 1 — Install and Configure Splunk](Step1_Install_and_Configure_Splunk.md)

---


