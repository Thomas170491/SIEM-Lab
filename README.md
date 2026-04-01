# 🔐 SIEM Lab – SOC Simulation (ELK Stack)

## 📌 Overview
This project consists of a self-built SIEM lab designed to simulate real-world Security Operations Center (SOC) workflows. The objective is to understand how security events are collected, analyzed, and correlated to detect potential threats.

The lab focuses on log ingestion, event analysis, detection rule creation, and investigation of suspicious activity.

---

## 🏗️ Architecture

The lab is composed of two virtual machines:

### 🖥️ Windows VM (Log Source)
- Sysmon (detailed system and process monitoring)
- Winlogbeat (log forwarding)

### 🐧 Linux VM (SIEM Stack)
- Elasticsearch (log storage and indexing)
- Kibana (visualization and analysis)

### 🔄 Log Flow
Windows (Sysmon / Event Logs)  
→ Winlogbeat  
→ Elasticsearch  
→ Kibana (analysis & detection)

---

## ⚙️ Implementation

- Installed and configured **Sysmon** to capture detailed process and system activity
- Configured **Winlogbeat** to forward Windows event logs to Elasticsearch
- Deployed an **ELK stack** (Elasticsearch + Kibana) on a Linux machine
- Verified log ingestion and indexing in Elasticsearch
- Used Kibana to explore, filter, and analyze logs

---

## 🔍 Detection & Analysis

### 🧪 Use Case: PowerShell Activity Monitoring
- Analyzed `powershell.exe` execution logs
- Investigated command-line arguments for signs of **obfuscation**
- Identified suspicious execution patterns commonly used in attacks

### 🚨 Detection Logic
- Created detection queries in Kibana to identify:
  - Suspicious PowerShell usage
  - Unusual process execution patterns
- Correlated events across logs to validate suspicious activity

---

## 🧠 SOC Workflow Simulation

This lab simulates key SOC analyst tasks:

- Log collection and centralization  
- Event correlation across multiple sources  
- Detection rule creation  
- Alert investigation  
- Threat identification based on log patterns  

---

## 🚧 Ongoing Improvements

- Authentication log analysis (failed vs successful login correlation)
- Brute-force detection scenarios  
- Additional attack simulations  
- Alert tuning and false-positive reduction  

---

## 🛠️ Technologies Used

- ELK Stack (Elasticsearch, Kibana)
- Sysmon
- Winlogbeat
- Windows Event Logs
- Virtual Machines

---

## 🎯 Key Learnings

- Understanding of SIEM architecture and log pipelines  
- Practical experience in log analysis and event correlation  
- Detection of suspicious behaviors in system activity  
- Hands-on exposure to SOC workflows and threat detection  

---

## 📎 Future Enhancements

- Dashboard creation for security monitoring  
- Integration of additional log sources  
- Automated alerting workflows  
- Expansion to more advanced attack scenarios  

---

## 👤 Author

Thomas Papas  
Cybersecurity Analyst (Junior) | Python | SIEM | Threat Detection  
