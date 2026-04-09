


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
3. Detection

Identified repeated failed login attempts from a single IP address targeting multiple accounts.

4. Analysis
High volume of failed logins within short time frame
Same IP attempting access across accounts
Pattern consistent with brute-force attack
🚨 Findings
Suspicious IP: 192.168.1.100
Attack Type: Brute Force Attempt
Target: Multiple user accounts
Risk Level: High
🛡️ Recommendations
Block the malicious IP address
Enable Multi-Factor Authentication (MFA)
Implement account lockout policies
Monitor login attempts continuously

## 📸 Evidence

![Splunk Failed Logins](phishing-analysis.png)

📚 Skills Demonstrated
SIEM Log Analysis
Threat Detection
Incident Investigation
Security Monitoring
MITRE ATT&CK Mapping
## 🚨 Findings

- Attack Type: Credential Harvesting  
- Malicious Domain: bit.ly/secure-login  
- Spoofed Email: noreply@microsoft.com  
- Technique: Social Engineering  
- Risk Level: High

