# 🛠️ Exercise: Perform Automated IOC Enrichment Using VirusTotal on Shuffle

## 🎯 Objective
Create a SOAR workflow in Shuffle that automates the enrichment of IOCs (IP addresses, file hashes, or URLs) using VirusTotal. The goal is to reduce manual effort and quickly assess threat severity for faster triage.

---

## 🔧 Lab Requirements

- 🟢 Shuffle Instance
- 🟢 VirusTotal API Key
- 🟢 HTTP Trigger App or form input to provide IOC
- 🟢 Slack / Email / TheHive (optional for notifications or case creation)

---

## 🪜 Step-by-Step Tasks

### 1. Trigger the Workflow
- Use the HTTP Trigger app to start the workflow when an IOC is received.
- Alternatively, allow manual IOC input using a form app in Shuffle.

### 2. Identify IOC Type
- Add a logic or function step to determine the IOC type (IP address, domain, URL, or file hash).
- Based on the type, route the IOC to the appropriate VirusTotal query node.

### 3. Query VirusTotal
- Use the VirusTotal app in Shuffle to perform the lookup.
- Retrieve analysis data such as:
  - Last analysis stats
  - Malicious and suspicious detection counts
  - Threat labels and tags
  - Community votes and relations

### 4. Evaluate Threat Severity
- Based on the enrichment results, categorize the IOC:
  - Malicious (e.g., >5 malicious detections)
  - Suspicious
  - Harmless or unknown

### 5. Take Action Based on Severity
- If the IOC is malicious:
  - Send a notification to SOC via Slack or email.
  - Create a case in TheHive with all enrichment context.
- If the IOC is not malicious:
  - Log the result to a database, sheet, or case tracking system for documentation.

### 6. Document and Output Results
- Format the enrichment results in a clear summary.
- Send the summary to the analyst team or attach it to the created case.

---

## ✅ Outcome

- IOCs are enriched automatically with context from VirusTotal.
- SOC teams are informed only when threat severity is confirmed.
- Manual lookup effort is reduced and response time is improved.
- Alerts and investigations are more data-driven and actionable.

---

## 🧩 Optional Enhancements

- Integrate with other sources like MISP or AbuseIPDB for multi-source enrichment.
- Build a historical enrichment log using Google Sheets or a database.
- Automatically tag or label IOCs based on detection categories (e.g., malware, phishing, C2).

---

Need the JSON template for this workflow in Shuffle or want it visualized in a diagram? Let me know!
