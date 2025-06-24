# Threat Detection Home Lab

## Objective
This project involves building a security monitoring lab to explore threat detection and incident response in a controlled environment. It covers the setup of monitoring systems, log analysis, network visibility, and threat hunting techniques, with a focus on simulating real-world scenarios and improving defensive capabilities.

## Skills Learned
- Gained hands-on experience in security monitoring within a lab environment
- Configured and deployed network traffic analysis tools
- Created alerts and rules for detecting suspicious activity
- Investigated simulated security incidents and developed response procedures
- Explored log collection, parsing, and analysis for threat detection and insights

## Tools Used
- **Splunk** - SIEM for log analysis and threat detection
- **Sysmon** - Windows system monitoring for detailed event logging.
- **Suricata** - Network IDS for threat detection on network traffic.
- **Winlogbeat** - Lightweight agent to ship Windows logs to Splunk.

## Project Phases

### Phase 1: Home Lab Setup & Configuration
- **Virtual Machine Setup**: Installed VirtualBox; created Windows and Linux VMs
- **Security Tools Installation**: Installed Splunk Enterprise on Linux VM; installed Sysmon and Winlogbeat on Windows VM
- **Log Forwarding Configuration**: Configured Sysmon for detailed Windows event logging and Winlogbeat to forward logs to Splunk via HTTP Event Collector
- **(Optional) Network IDS Setup**: Installed and configured Suricata on Linux VM for network traffic monitoring and alerting

### Phase 2: SIEM Alerts & Dashboards
- **Event Data Ingestion**: Successfully ingested Windows Sysmon logs and Suricata alerts into Splunk
- **Alert Rules Configuration**: Created alerts for brute force login attempts, suspicious process creations, and privilege escalation indicators
- **Dashboard Development**: Built interactive Splunk dashboards to visualize endpoint and network security events in real-time

### Phase 3: Incident Response & Analysis
- **Simulated Attack Scenarios**: Generated test attacks (e.g., brute force, suspicious processes) to validate detection capabilities
- **Incident Documentation**: Developed basic SOC playbooks and incident reports based on lab detections and alert triggers
- **Continuous Improvement**: Tuned alert thresholds and log collection for reducing false positives and improving detection accuracy

## Challenges
*To be documented*

## Attack Simulations & Results
*To be documented*
