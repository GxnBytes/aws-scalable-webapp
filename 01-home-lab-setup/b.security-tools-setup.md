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
