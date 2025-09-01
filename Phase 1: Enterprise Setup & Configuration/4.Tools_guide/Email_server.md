# 📧 Email Server - MailHog

## Prerequisites

- `[skynet-corp-svr]` is configured.
  - Docker is installed.
- Windows Server 2025 with Active Directory Domain Services (ADDS) enabled.

---

## CORP-SVR: Email Server

The first service we will run on `[skynet-corp-svr]` is an email server.

An **email server** sends, receives, stores, and manages emails. It typically uses:

- **SMTP** (Simple Mail Transfer Protocol) – for sending  
- **IMAP** or **POP3** – for receiving and managing emails

We'll configure **MailHog** to send and route emails to our workstation fleet.

> Today, most organisations use managed services like Gmail or Microsoft 365. Running your own mail server is complex due to spam, blacklisting, and reputation building. However, it's great for learning self-hosted email infrastructure and security.

---

## MailHog Overview

**MailHog** is a lightweight email testing tool that functions as a fake SMTP server. It captures outgoing emails without delivering them, viewable via a web interface or API.

**Ideal for:**

- Simulating business email infrastructure
- Phishing and email attack testing
- Debugging applications that send emails
- Avoiding spam filters or external dependencies

I'm using MailHog in our **Cyber Attack** to simulate a corporate mail system.

---

## MailHog Specifics

- **SMTP Server:**
  - Listens on port `1025`
  - Applications send mail via `localhost:1025`
- **Web UI:**
  - Accessible at `localhost:8025`
  - View messages, headers, attachments
- **API:**
  - Script and automate via endpoints

---

## Configure MailHog

MailHog has an official Docker image available on Docker Hub.

I'm using **Docker Compose** for repeatable setup.

```bash
cd /home
sudo mkdir mailhog && cd mailhog
sudo nano docker-compose.yml
```

Paste the following:

```yaml
services:
  mailhog:
    image: mailhog/mailhog
    container_name: mailhog
    ports:
      - "1025:1025"
      - "8025:8025"
```

Exit Nano: `CTRL+X`, then `Y`, then `Enter`

Start the container:

```bash
sudo docker compose up -d
```

Access MailHog UI in Firefox: [http://localhost:8025](http://localhost:8025)

---

## Create a Test Email

```bash
cd /home
sudo nano test_message.py
```

Paste this Python script:

```python
import smtplib
from email.message import EmailMessage

msg = EmailMessage()
msg.set_content("This is a test email from Ubuntu VM.")
msg["Subject"] = "Hello World from MailHog!"
msg["From"] = "corpserver@example.com"
msg["To"] = "user@example.com"

with smtplib.SMTP("localhost", 1025) as server:
    server.send_message(msg)
```

Make it executable and run:

```bash
sudo chmod +x test_message.py
sudo python3 test_message.py
```

You should see the test email appear in the MailHog UI.

---

## Create an Email Poller Script

Now let’s simulate an email notification system on `[skynet-linux-client]`.

Start the VM if it’s not already running.

Open a terminal as `janed@linux-client`:

Install dependencies:

```bash
sudo apt install curl jq
```

Go to home directory and create a new script:

```bash
cd /home
sudo nano email_poller.sh
```

Paste the following:

```bash
#!/bin/bash

MAILHOG_IP="10.0.0.8"  
TO_EMAIL="janed"
POLL_INTERVAL=30  # seconds

echo "📡 Janed's Mail Watcher started... polling every $POLL_INTERVAL seconds"
echo "🔎 Watching for new mail sent to: $TO_EMAIL@"

# Track seen message IDs
SEEN_IDS_FILE="/tmp/mailhog_seen_ids_janed.txt"
touch "$SEEN_IDS_FILE"

while true; do
  curl -s http://$MAILHOG_IP:8025/api/v2/messages | jq -c '.items[]' | while read -r msg; do
    TO=$(echo "$msg" | jq -r '.To[].Mailbox')
    ID=$(echo "$msg" | jq -r '.ID')

    if [[ "$TO" == "$TO_EMAIL" && ! $(grep -Fx "$ID" "$SEEN_IDS_FILE") ]]; then
      SUBJECT=$(echo "$msg" | jq -r '.Content.Headers.Subject[0]')
      BODY=$(echo "$msg" | jq -r '.Content.Body')

      echo -e "\n📬 New Email Received!"
      echo "Subject: $SUBJECT"
      echo "From: $(echo "$msg" | jq -r '.Content.Headers.From[0]')"
      echo "Date: $(echo "$msg" | jq -r '.Created')"
      echo -e "Message:\n$BODY"
      echo "-----------------------------------"

      echo "$ID" >> "$SEEN_IDS_FILE"
    fi
  done

  sleep "$POLL_INTERVAL"
done
```

Exit Nano: `CTRL+X`, then `Y`, then `Enter`

Make it executable and run:

```bash
chmod +x email_poller.sh
sudo ./email_poller.sh &
```

To stop the script:

```bash
pkill -f email_poller
```

📷 **Take Snapshot!**
