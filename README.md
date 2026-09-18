<img width="662" height="801" alt="picture of tool for cybersecurity" src="https://github.com/user-attachments/assets/e3dd667b-7981-49dd-95e3-24b2ef6f3be1" /># SOCLab with Wazuh: Building and Operating a Wazuh SIEM Environment

I recently completed a hands-on Security Operations Center (SOC) lab project using Wazuh, where I built and operated a small monitoring environment consisting of Windows and Linux endpoints.
The goal was not just to install Wazuh, but to understand the complete SOC workflow:
Telemetry → Detection → Investigation → Response → Reporting

During the project, I:
 Deployed a Wazuh SIEM environment(ubuntu server 24.04)
 Connected Windows 11 and Ubuntu Linux agents
 Collected and analyzed endpoint security telemetry
 Built a SOC monitoring dashboard
Configured File Integrity Monitoring (FIM)
Created and tested a custom Wazuh detection rule
Configured automated response capabilities
Investigated security alerts using endpoint and authentication logs
Documented the investigation in a SOC incident report

 Detection Scenario:
During testing, I simulated repeated failed SSH authentication attempts from a Windows endpoint:
Source: Windows — 192.168.73.133
Target: Ubuntu Linux — 192.168.73.131
Target Account: mydfir
Service: SSH (sshd)
Attempts: 3 failed authentication attempts
Time: 11:58:22 – 11:58:45 WAT
Detection: Wazuh brute-force correlation rule
MITRE ATT&CK: T1110 – Brute Force
Wazuh successfully correlated the repeated "Failed password" events and generated a Level 10 security alert.

 Investigation:
I then investigated the alert using the available endpoint telemetry and threat-intelligence sources.
The source IP was an internal  address and had no malicious reputation according to the threat-intelligence checks performed.
Because the activity originated from an internal system, I treated the alert as an investigation rather than completely blocking the IP.
Possible explanations included:
•	Misconfigured credentials 
•	A legitimate user entering an incorrect password 
•	An automated script with incorrect credentials 
•	Potential lateral movement or brute-force activity 
I also checked the appropriate next steps an analyst should take, including looking for a successful SSH login following the failed attempts.
 
 Key Takeaway
This project helped me move beyond simply learning cybersecurity tools and practice the actual SOC analyst workflow:
Detect → Validate → Investigate → Determine Severity → Respond → Document
It also gave me practical experience with SIEM, endpoint telemetry, log analysis, detection engineering, threat intelligence, MITRE ATT&CK mapping, FIM, and incident reporting.
I'm continuing to build my cybersecurity lab and strengthen my practical SOC skills through hands-on projects.
Tools:
Wazuh | Windows | Ubuntu Linux | SSH | MITRE ATT&CK | File Integrity Monitoring | SIEM | Threat Intelligence




