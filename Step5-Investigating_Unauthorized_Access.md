# Investigating Unauthorized Access Lab – Splunk  

## 🎯 Objective  
To learn how to search and analyze authentication logs using Splunk to:  
- Detect unauthorized access attempts.  
- Extract meaningful insights from fields like `user`, `src_ip`, and `status`.  
- Identify suspicious login behaviors that may indicate compromise.  

---

## 🛠️ Lab Setup  
- **Ubuntu Server:** 22.04 or later  
- **Data Source:** Linux Auth log sample  
- **Pre-requisite:** Splunk Server set up on Ubuntu Server  

---

## 📥 Lab Task  
Submit your answers along with screenshots from your Splunk queries.  

### Question 1:  
What is the total number of success events in this log file?  

### Question 2:  
What is the most common event triggered and captured in this log file?  

### Question 3:  
If a user with a `uid` 1010 tried accessing a Linux server, what is the logfile path accessed by him twice?  

---

## ✅ Conclusion  
In this lab, you learned how to investigate unauthorized access attempts using Splunk by analyzing authentication logs.  

You gained hands-on experience with SPL (Search Processing Language) to:  
- Query login data.  
- Detect suspicious activity.  
- Extract valuable insights.  

This exercise helped you:  
- Understand patterns of unauthorized access behavior.  
- Use Splunk to identify high-risk user and IP combinations.  
- Strengthen your skills in log analysis and incident investigation.  

