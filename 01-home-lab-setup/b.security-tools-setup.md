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

## Install Zeek and Suricata

Zeek and Suricata are powerful security monitoring tools that provide in-depth network analysis and intrusion detection capabilities.

### Steps to Install Zeek and Suricata:

1. **Install Suricata:**
   - Download and install Suricata from the official website: [Suricata](https://suricata.io/download/).
   - Follow the installation instructions for your operating system.

2. **Install Zeek:**
   - Download and install Zeek from the official website: [Zeek](https://zeek.org/get-zeek/).
   - Follow the installation instructions for your operating system.

3. **Configure Zeek and Suricata for Network Monitoring:**
   - Ensure that both tools are configured correctly to monitor your network traffic.
   - Edit the configuration files for Zeek (`/opt/zeek/etc/zeekctl.cfg`) and Suricata (`/etc/suricata/suricata.yaml`) to adjust for your network setup.

4. **Start Zeek and Suricata Services:**
   - Start Zeek by running:
     ```sh
     sudo zeekctl start
     ```
   - Start Suricata by running:
     ```sh
     sudo systemctl start suricata
     ```

5. **Verify that Zeek and Suricata are Running:**
   - Check the status of Zeek:
     ```sh
     sudo zeekctl status
     ```
   - Check the status of Suricata:
     ```sh
     sudo systemctl status suricata
     ```

6. **Monitor and Analyse Logs:**
   - Zeek logs are typically located in `/opt/zeek/logs/`.
   - Suricata logs are typically located in `/var/log/suricata/`.
   - Use tools like Kibana or Splunk to visualise and analyse the logs for deeper insights into network activities.

## Verify Log Collection & Connectivity

### Ensure Logs Are Being Collected in Splunk
To confirm that Splunk is receiving logs from your configured sources:

1. Open Splunk and navigate to **Search & Reporting**.
2. Run the following search query to check if Windows Event Logs, Sysmon logs, and Firewall logs are being ingested:
   ```splunk
   index=winlogbeat OR index=sysmon OR index=firewall
