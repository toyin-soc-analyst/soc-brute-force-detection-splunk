
soc-brute-force-detection-splunk
# 🚨 SOC Incident Response: Brute Force Attack Detection Using Splunk

## 📌 Scenario
A company’s security team noticed multiple failed login attempts on a user account. As a SOC Analyst, I was tasked with investigating potential brute-force attack activity using Splunk.

---

## 🎯 Objective
- Detect suspicious login behavior  
- Analyze authentication logs  
- Identify attack patterns  
- Recommend mitigation strategies  

---

## 🛠️ Tools Used
- Splunk (SIEM)
- Windows Event Logs
- MITRE ATT&CK Framework

---

## 🔍 Investigation Steps

### 1. Log Collection
Collected Windows Event Logs and ingested them into Splunk.

### 2. Search Query
Used Splunk to identify multiple failed login attempts:

```spl
index=wineventlog EventCode=4625
| stats count by Account_Name, Source_Network_Address
| sort - count
