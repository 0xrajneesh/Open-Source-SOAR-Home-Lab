# 🛠️ Exercise#1: Build a Basic SOAR Workflow in Shuffle for Email Alert Triage

## 🎯 Objective
Automate the triage of phishing email alerts using Shuffle by parsing the email, enriching indicators, and creating a case.

---

## 🔧 Lab Requirements

- 🟢 **Shuffle Instance**
- 🟢 **Email Source (e.g., Gmail, Outlook, or Email Security Gateway)**
- 🟢 **VirusTotal or URLScan API Key**
- 🟢 **TheHive or Jira (optional for case management)**

---

## 🪜 Step-by-Step Tasks

### 1. Receive Email Alert
- **Trigger** the workflow using a webhook or email polling app.
- **Parse** the email subject, sender, body, and embedded URLs.

### 2. Extract IOCs
- Use Python or Regex parsing inside Shuffle to extract:
  - URLs
  - IP addresses
  - File hashes

### 3. Enrich Indicators
- Use external APIs to enrich the extracted indicators:
  - **VirusTotal** – to check the reputation of IPs, hashes, domains.
  - **URLScan** – to analyze and screenshot suspicious URLs.

### 4. Decide Threat Level
- If VirusTotal reports any indicator as **malicious** (score > 5):
  - Mark the email as **High Priority**.
  - Tag the case with “Phishing” or “Malicious”.

### 5. Create a Case
- Automatically create a case in:
  - **TheHive**, **Jira**, or another ticketing system.
- Include:
  - Alert summary
  - Parsed email content
  - Enrichment results

### 6. Notify Analyst
- Send an automated message to Slack, Teams, or email:
  - Include case ID, summary, threat score, and IOC highlights.

---

## ✅ Outcome

- Email alert triage is automated.
- Indicators are enriched using threat intelligence tools.
- A case is created for investigation with actionable data.
- SOC analyst is notified with necessary context.

