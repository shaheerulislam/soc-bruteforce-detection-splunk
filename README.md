SOC Brute Force Detection & Windows Event Log Analysis using Splunk SIEM

Project Overview
This investigation simulates a SOC Tier 1 alert triage workflow for brute-force authentication activity using Splunk Enterprise.The project focuses on identifying suspicious authentication behaviour through Windows Event Logs, analysing failed login patterns, and demonstrating how SOC analysts detect and investigate potential credential-based attacks.

Objectives
Ingest Windows Event Logs into Splunk SIEM
Detect brute-force authentication attempts using SPL queries
Analyse repeated failed login patterns and system events
Demonstrate SOC Tier 1 investigation and triage workflow
Translate raw logs into actionable security insights

Alert Context
Detected activity represents a potential low-to-medium severity brute-force authentication pattern, requiring investigation for repeated login attempts and source correlation. Such behaviour is commonly associated with credential-guessing attacks targeting Windows environments.

SOC Incident Scenario
A simulated brute-force attack pattern was generated using authentication logs containing repeated failed login attempts.
The investigation focused on:
Repeated authentication failures
Potential credential-guessing behaviour
System-level anomalies in Windows event logs

This reflects a real SOC Tier 1 use case where analysts investigate authentication-based attack patterns.

Detection Approach
The Splunk query aggregates authentication failures to identify repeated login attempts from the same host, user, or source.
This helps detect potential brute-force attack behaviour based on frequency and repetition patterns.

Tools & Technologies
Splunk Enterprise
Windows Event Logs
Syslog / Authentication Logs
SPL (Search Processing Language)

Detection Logic (Brute Force Analysis)
index=main sourcetype="WinEventLog:Application"
| search "failed" OR "Failed password"
| stats count by host, user, source
| sort -count


Key Findings
Multiple failed authentication attempts detected from repeated sources
Pattern consistent with automated credential-guessing behaviour
No successful authentication observed within attack window
Windows Application logs confirmed repeated access attempts
Logs successfully ingested and analysed in Splunk SIEM


SOC Analyst Conclusion
This activity is consistent with a brute-force authentication attempt targeting Windows services. 
In a real SOC environment, this would trigger:

Account lockout enforcement
Source IP investigation and blocking
Correlation with threat intelligence feeds
Escalation to Tier 2 SOC for deeper analysis


Detection Value
This detection enables early identification of credential-based attacks before successful compromise occurs, supporting proactive threat mitigation in SOC environments.

Evidence of Execution
Log Ingestion Success
Windows Event Log Analysis
Detection Query Results

Skills Demonstrated
SIEM log ingestion and configuration
Security event analysis using Splunk
Brute-force attack detection
SOC alert triage and investigation workflow
SPL query development and optimization
Windows Event Log interpretation

SOC Value
This project demonstrates practical SOC Tier 1 capabilities:
Threat detection and monitoring
Log-based security analysis
Incident investigation workflow
SIEM-based detection engineering
Security event correlation

Final Statement
This project simulates a real SOC investigation workflow using Splunk SIEM, demonstrating hands-on skills in threat detection, log analysis, and security incident triage.
