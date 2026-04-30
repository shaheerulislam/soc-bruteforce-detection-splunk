SOC Brute Force Detection & Windows Event Log Analysis

Project Overview
This project simulates a real-world SOC (Security Operations Centre) investigation using Splunk Enterprise.
The objective is to detect brute-force authentication attempts and analyse Windows Event Logs to identify suspicious login behaviour and system anomalies.
This project demonstrates end-to-end SOC Tier 1 analysis including log ingestion, detection engineering, and incident interpretation.

Objectives
Ingest Windows Event Logs into Splunk SIEM
Detect brute-force login attempts using SPL queries
Analyse authentication failures and system events
Identify suspicious patterns in login behaviour
Demonstrate SOC investigation workflow

SOC Scenario
A simulated attack pattern was generated using authentication logs containing repeated failed login attempts. The goal was to identify brute-force behaviour and analyse system-level security events.
This reflects a common SOC Tier 1 use case: credential-based attack detection.


 Tools & Technologies
Splunk Enterprise
Windows Event Logs
SPL (Search Processing Language)
Syslog / Authentication logs

Detection Query (Brute Force Analysis)
index=main sourcetype="WinEventLog:Application"
| search "failed" OR "Failed password"
| stats count by host, user, source
| sort -count


Key Findings
Multiple failed login attempts detected from repeated sources
Pattern indicates potential brute-force attack behaviour
Windows Application logs showed repeated authentication failures
Service-level errors also observed in system logs

Evidence of Execution
Log Ingestion Success
Windows Event Log Analysis
Detection Query Results


SOC Analyst Conclusion
The repeated authentication failures indicate a potential brute-force attack attempt. In a real SOC environment, this would trigger:
Alert escalation to Tier 2 SOC
IP address investigation
Account lockout policy validation
Threat intelligence correlation


Skills Demonstrated
SIEM log ingestion & configuration
Security event analysis
Brute-force attack detection
SOC alert investigation workflow
SPL query development
Windows Event Log interpretation


Business / SOC Value
This project demonstrates practical SOC Tier 1 capabilities in:

Threat detection
Security monitoring
Incident analysis
Log-based investigation
