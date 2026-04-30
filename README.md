1. Project Title : Splunk SOC Brute Force Detection & Windows Event Log Analysis

2. Project Overview
This project demonstrates a SOC (Security Operations Centre) style investigation using Splunk SIEM. It focuses on detecting brute-force login attempts and analysing Windows Event Logs to identify suspicious authentication activity and system anomalies.

3. Objectives
Ingest authentication and Windows Event Logs into Splunk
Detect brute-force login patterns
Analyse failed authentication attempts
Build SIEM-based detection queries
Demonstrate SOC Tier 1 investigation workflow


4. Tools Used
Splunk Enterprise Splunk Enterprise
Windows Event Logs
Syslog authentication data
SPL (Search Processing Language)


5. Detection Logic 
index=main sourcetype="WinEventLog:Application"
| search "failed" OR "Failed password"
| stats count by host, user, src_ip
| sort -count


7. Evidence 
### Log Ingestion Success
![Ingestion](screenshots/ingestion.png)
### Windows Event Log Analysis
![Windows Logs](screenshots/windows-event-log.png)
### Detection Results
![Detection](screenshots/detection-results.png)


8. SOC Analyst Skills Demonstrated
SIEM log ingestion and parsing
Threat detection using SPL queries
Event log analysis (Windows security logs)
Brute-force attack pattern recognition
Security monitoring and alert investigation



This project demonstrates practical SOC analyst skills including SIEM-based threat detection, log analysis, and brute-force attack investigation using Splunk.
