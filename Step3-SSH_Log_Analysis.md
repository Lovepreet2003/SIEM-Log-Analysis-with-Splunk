# SSH Log Analysis Lab – Splunk  

## 🎯 Objective  
In this lab, you will:  
- Learn how to ingest and analyze SSH logs using Splunk.  
- Detect failed and successful SSH authentication attempts.  
- Identify unusual SSH activity that may indicate brute force or unauthorized access.  

## 🖥️ Lab Setup  
**Requirements:**  
- **Splunk:** Already installed and accessible.  
- **Data Source:** JSON-formatted Zeek-style SSH logs.  

**Sample Log File:**  
Download the file: `synthetic_zeek_ssh.json` and upload it to Splunk.  

## ⚙️ Steps to Upload SSH Log into Splunk  

1. Go to **Splunk Web → Settings → Add Data**.  
2. Choose **Upload** and select `synthetic_zeek_ssh.json`.  
3. Set **Source type**: `json` or create a new one `zeek:ssh`.  
4. Select **Index**: Choose `main` or create a new index `ssh_lab`.  
5. Finish the upload and confirm indexing.  

---

## 🔍 Lab Tasks & SPL Queries  

###  Task 1: List the top 10 endpoints with failed SSH login attempts  
**SPL Query:**  
```
index=ssh_lab sourcetype="json" auth_success=false
| stats count by "id.orig_h"
| sort -count
| head 10
```
### RESULT:


###  Task 2: Find the number of total SSH connections

```
index=ssh_lab sourcetype="json"
| stats count as total_ssh_connections
```
### RESULT:


###  Task 3: Count all event types (successful, failed, no-auth, multiple-failed)

```
index=ssh_lab sourcetype="json"
| stats count by event_type
```
### RESULT:


---
🚀 **What’s Next?**  

Now that Splunk is installed and working, the next step is **HTTP Log Analysis**.  

In this section, you will:  
- Learn how to upload HTTP logs into Splunk.  
- Extract important fields from the logs.  
- Identify the most visited URLs.  
- Find the most active client IPs.  
- Detect unusual HTTP activity that might indicate attacks or suspicious behavior.  

👉 Continue to [Step 4 — HTTP Log Analysis:](Step4-HTTP_Log_Analysis)

