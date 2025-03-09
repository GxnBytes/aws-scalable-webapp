# Security Tools Setup

This guide provides step-by-step instructions to install and configure essential security monitoring tools for a cybersecurity lab environment.

## Install & Configure Security Monitoring Tools

### Install Splunk (Free Version)
1. Download Splunk Free from the official [Splunk website](https://www.splunk.com/en_gb/download.html).
2. Install Splunk on your preferred system (Windows or Linux).
3. Set up an admin username and password.
4. Ensure Splunk is running and accessible via the web interface (`http://localhost:8000` by default).

### Install Winlogbeat & Sysmon on Windows VM
1. Download and install [Sysmon](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon) to enhance Windows logging.
2. Download [Winlogbeat](https://www.elastic.co/downloads/beats/winlogbeat) for forwarding logs to Splunk.
3. Configure `winlogbeat.yml` to send logs to Splunk:
   ```yaml
   output.logstash:
     hosts: ["<SPLUNK_IP>:5044"]

## Install Security Onion

Security Onion is a comprehensive security monitoring platform that includes Suricata IDS, Zeek, and Kibana.

### Steps to Install Security Onion:
1. Download the latest Security Onion ISO from [Security Onion Solutions](https://securityonion.net/).
2. Create a new virtual machine or use a dedicated server.
3. Boot from the ISO and follow the installation wizard.
4. Configure Security Onion for network monitoring.
5. Ensure all services (Zeek, Suricata, Elasticsearch, and Kibana) are running by using:
   ```sh
   sudo so-status

## Verify Log Collection & Connectivity

### Ensure Logs Are Being Collected in Splunk
To confirm that Splunk is receiving logs from your configured sources:

1. Open Splunk and navigate to **Search & Reporting**.
2. Run the following search query to check if Windows Event Logs, Sysmon logs, and Firewall logs are being ingested:
   ```splunk
   index=winlogbeat OR index=sysmon OR index=firewall
