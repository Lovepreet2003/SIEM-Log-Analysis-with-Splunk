# HTTP Log Analysis Lab – Splunk  

## 🎯 Objective  
In this lab, you will:  
- Learn how to ingest and analyze HTTP logs using Splunk.  
- Detect client errors, server errors, and suspicious web activity.  
- Identify large file transfers and suspicious URI access attempts.  

## 🖥️ Lab Setup  
**Requirements:**  
- **Splunk:** Already installed and accessible.  
- **Data Source:** JSON-formatted Zeek-style HTTP logs.  

**Sample Log File:**  
Download the file: `synthetic_zeek_http.json` and upload it to Splunk.  

## ⚙️ Steps to Upload HTTP Log into Splunk  

1. Go to **Splunk Web → Settings → Add Data**.  
2. Choose **Upload** and select `synthetic_zeek_http.json`.  
3. Set **Source type**: `json` or create a new one `zeek:http`.  
4. Select **Index**: Choose `main` or create a new index `http_lab`.  
5. Finish the upload and confirm indexing.  

---

## 🔍 Lab Tasks & SPL Queries  

### ✅ Task 1: Find the top 10 endpoints generating web traffic  
**SPL Query:**  
```spl
index=http_lab sourcetype="json"
| stats count by "id.orig_h"
| sort -count
| head 10
```
RESULT:

### ✅ Task 2: Count the number of server errors (5xx) observed

```
index=http_lab sourcetype="json" status_code>=500 status_code<600
| stats count as server_errors
```
RESULT:

### ✅ Task 3: Identify User-Agents associated with possible scripted attacks

```
index=http_lab sourcetype="json" user_agent IN ("sqlmap/1.5.1", "curl/7.68.0", "python-requests/2.25.1", "botnet-checker/1.0")
| stats count by user_agent
```
RESULT:


🚀 **What’s Next?**  

After completing this lab, you will be able to:  
- Analyze HTTP logs for unusual activity.  
- Detect potential attacks.  
- Gain insight into web traffic patterns in Splunk.  

👉 **Continue to [Step 3 — Investigating Unauthorized Access**:](Step3-Investigating_Unauthorized_Access.md)
