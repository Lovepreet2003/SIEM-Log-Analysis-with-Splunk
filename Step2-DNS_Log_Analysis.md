# DNS Log Analysis Lab – Splunk  

## 🎯 Objective  
In this lab, you will:  
- Learn how to ingest and analyze DNS logs in Splunk.  
- Extract useful information such as DNS query types, source hosts, and common destinations.  
- Practice building basic SPL (Search Processing Language) queries to investigate DNS activity.  

## 🖥️ Lab Setup  
**Requirements:**  
- **Splunk:** Already installed and accessible.  
- **Data Source:** JSON-formatted Zeek DNS logs.  

**Sample Log File:**  
Download the file: `dns.log` and place it in a directory accessible to Splunk for ingestion.  

## ⚙️ Steps to Upload DNS Log into Splunk  

1. Go to **Splunk Web → Settings → Add Data**.  
2. Choose **Upload** and select the file `dns.log`.  
3. Set **Source type**: `json` or create a custom source type `dns`.  
4. Select **Index**: Choose `main` or create a new index `dns_lab`.  
5. Finish the upload and confirm indexing.  

---

## 🔍 Lab Tasks & SPL Queries  

### Task 1: Identify the most frequently queried domain names  
**SPL Query:**  
```spl
index=dns_lab sourcetype="json"
| stats count by query
| sort -count
```
#### RESULT:
[](SIEM-Log-Analysis-with-Splunk/screenshot/1.png)

### Task 2: Find the most active user IPs generating DNS traffic

SPL Query:
```
index=dns_lab sourcetype="json"
| stats count by "id.orig_h"
| sort -count
```
#### RESULT:
(2.png)

### Task 3: Breakdown of DNS query types (A, AAAA, CNAME, PTR)

SPL Query:
```
index=dns_lab sourcetype="json"
| stats count by qtype
```
#### RESULT:
(3.png)

🚀 **What’s Next?**  
Now that Splunk is installed and configured successfully, the next section — **Step 2: SSH Log Analysis** — will guide you through ingesting SSH logs into Splunk and analyzing them using SPL (Search Processing Language).  

You’ll learn how to extract fields, identify the most active source IPs, detect failed and successful login attempts, and spot unusual SSH activity that could indicate malicious behavior.  

👉 **Continue to [Step 3 — SSH_Log_Analysis](Step3-SSH_Log_Analysis.md)
