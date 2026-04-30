#  SOC Project: Brute Force Attack Detection using Splunk

##  Overview

This project demonstrates the detection and analysis of brute-force login attacks using SIEM (Splunk). It is designed to simulate real-world Security Operations Centre (SOC) Tier 1 workflows, including alert monitoring, triage, investigation, and incident reporting.

The goal of this project is to showcase practical cybersecurity skills in log analysis, threat detection, and incident response aligned with SOC operations.

---

##  Objectives

* Detect brute-force login attempts using SIEM queries
* Analyse authentication logs to identify suspicious behaviour
* Simulate SOC alert triage and escalation workflows
* Document findings in a structured incident report
* Map detection to MITRE ATT&CK framework

---

##  Tools & Technologies

* SIEM: Splunk
* Log Source: Linux authentication logs (`auth.log`)
* Techniques: Log analysis, threat detection, incident investigation

---

##  Detection Logic

### Splunk Query Used

```
index=auth_logs sourcetype=linux_secure
"Failed password"
| stats count by src_ip, user
| where count > 5
| sort - count
```

### Detection Explanation

This query identifies repeated failed login attempts from the same source IP and user account. A threshold of more than 5 failed attempts is used to flag potential brute-force activity.

---

## Threat Scenario

Brute-force attacks involve repeated login attempts using different password combinations to gain unauthorised access to user accounts. These attacks can lead to account compromise if successful.

---

##  Investigation Process (SOC Workflow)

1. **Alert Identification**

   * Multiple failed login attempts detected from a single IP

2. **Triage**

   * Classified as **Medium to High severity** based on frequency

3. **Analysis**

   * Checked number of attempts per user
   * Identified targeted accounts
   * Reviewed log timestamps and patterns
   * Looked for successful login after failed attempts

4. **Validation**

   * Pattern consistent with brute-force behaviour

5. **Escalation**

   * Escalated to Tier 2 SOC for further investigation

---

##  Key Indicators of Compromise (IOCs)

* Suspicious Source IP (e.g., 192.168.x.x)
* High number of failed login attempts (>5 threshold)
* Repeated targeting of specific user accounts

---

##  Incident Report Summary

###  Incident Description

Detected multiple failed login attempts from a single source IP targeting one or more user accounts.

###  Impact

Potential risk of account compromise and unauthorised access.

###  Response Actions

* Blocked suspicious IP address
* Recommended password reset for affected accounts
* Suggested enabling Multi-Factor Authentication (MFA)
* Increased monitoring for similar activity

---

##  Dashboard Insights (Conceptual)

* Failed login trends over time
* Top attacking IP addresses
* Most targeted user accounts

---

##  MITRE ATT&CK Mapping

* **Technique:** T1110 – Brute Force
* **Tactic:** Credential Access

---

##  Key Skills Demonstrated

* SIEM Monitoring & Alert Triage
* Log Analysis & Threat Detection
* Incident Investigation & Reporting
* SOC Workflow Understanding
* Cyber Threat Analysis

---

##  Project Structure

```
soc-bruteforce-detection-splunk/
│
├── README.md
├── detection-queries/
│   └── brute_force_query.txt
├── sample-logs/
│   └── auth_logs_sample.txt
├── dashboards/
│   └── dashboard_description.md
├── incident-report/
│   └── brute_force_case_study.md
```

---

##  Conclusion

This project demonstrates how brute-force attacks can be detected and analysed using SIEM tools within a SOC environment. It highlights practical skills in identifying threats, performing investigations, and responding to security incidents.

---

##  Author

Shaheer Ul Islam
Cybersecurity MSc | SOC Analyst (Aspiring)
