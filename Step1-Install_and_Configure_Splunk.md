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


