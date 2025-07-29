# 🛠️ Exercise#2: Receive Wazuh Alerts with Shuffle Based on a Rule ID

## 🎯 Objective
Automate the triage of Wazuh alerts in Shuffle and filter them based on specific **rule IDs** (e.g., `100015`, `18107`). Only alerts matching selected rule IDs should be enriched, escalated, or notified to the SOC team.

---

## 🔧 Lab Requirements

- 🟢 Wazuh Manager with active alerting
- 🟢 Shuffle Instance
- 🟢 Shuffle Webhook App (HTTP Receiver)
- 🟢 TheHive / Slack / Email (for optional case creation or alerting)

---

## 🪜 Step-by-Step Tasks

### 1. Configure Wazuh Alert Forwarding
- Set up your Wazuh Manager to forward alerts in JSON format.
- Use Logstash, Filebeat, or a custom script to POST alerts to the Shuffle webhook URL.

### 2. Set Up HTTP Trigger in Shuffle
- Use the HTTP Trigger App to receive alerts from Wazuh.
- Ensure the workflow starts when a new alert is received.

### 3. Filter by Rule ID
- Add a logic step to inspect the rule ID in the incoming alert.
- Proceed only if the rule ID matches one of the predefined values (e.g., `100015`, `18107`).
- Ignore or log alerts with other rule IDs.

### 4. Enrich the Alert (Optional)
- Extract indicators of compromise (IOCs) such as IPs, hashes, or URLs from the alert.
- Enrich the IOCs using external threat intelligence platforms like VirusTotal, AbuseIPDB, or MISP.

### 5. Create a Case or Notify the Analyst
- If the alert is relevant, create an incident case in TheHive or generate a notification via Slack or Email.
- Include key details such as the rule ID, affected host, timestamp, and IOC summary.

### 6. Handle Non-Matching Alerts
- For alerts that do not match the specified rule IDs:
  - Log them to a file or external system.
  - Optionally stop the workflow silently without generating a case or alert.

---

## ✅ Outcome

- Shuffle receives and processes real-time alerts from Wazuh.
- Only specific alerts based on rule ID are escalated for further action.
- Noise is reduced and analyst focus is improved.
- High-value alerts are enriched and passed along with context.


