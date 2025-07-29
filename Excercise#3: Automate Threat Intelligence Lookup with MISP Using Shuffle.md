# 🛠️ Exercise#3: Automate Threat Intelligence Lookup with MISP Using Shuffle

## 🎯 Objective
Build a SOAR workflow in Shuffle that automatically performs a threat intelligence lookup for IPs, URLs, or hashes using MISP. This workflow helps SOC analysts quickly assess the threat context of observed indicators.

---

## 🔧 Lab Requirements

- 🟢 MISP Instance (self-hosted or cloud)
- 🟢 Shuffle Instance
- 🟢 MISP API key and URL
- 🟢 HTTP Trigger App or manual IOC input
- 🟢 Slack / Email / TheHive (optional for alerting or case management)

---

## 🪜 Step-by-Step Tasks

### 1. Trigger the Workflow
- Use HTTP Trigger to start the workflow when a new IOC is received.
- Alternatively, use a scheduled input or form-based input in Shuffle to initiate the lookup manually.

### 2. Normalize the IOC Input
- Add a function step to check the type of IOC (IP, domain, URL, hash).
- Normalize the input for MISP format if needed.

### 3. Perform MISP Lookup
- Use the MISP app in Shuffle to query the provided IOC against your threat intel database.
- Look for existing attributes, sightings, threat levels, tags, and related events.

### 4. Analyze the Lookup Results
- Inspect the results returned from MISP:
  - If the IOC is found and marked as malicious or suspicious, escalate it.
  - If not found or marked as benign, document and store it for reference.

### 5. Take Action Based on Threat Context
- If the IOC is malicious:
  - Notify the SOC team via Slack or email.
  - Create an incident case in TheHive or another ticketing system.
- If the IOC is not malicious:
  - Log the result in a report or Google Sheet for auditing.

### 6. Optional - Enrich Further or Add to MISP
- Optionally enrich with other sources (e.g., VirusTotal).
- Add new indicators back into MISP for community or internal use.

---

## ✅ Outcome

- Threat intelligence lookups are automated via MISP.
- Analysts get enriched context instantly for any IOC.
- Decisions on containment or investigation are faster and more informed.
- IOC lifecycle is documented within the workflow.

