# 🛠️ Exercise#5: Build a Workflow to Create an Incident on ServiceNow Using Shuffle

## 🎯 Objective
Automate the process of creating incidents in **ServiceNow** using a Shuffle workflow. This helps ensure that critical alerts or IOC findings are promptly tracked and assigned for response.

---

## 🔧 Lab Requirements

- 🟢 Shuffle Instance
- 🟢 ServiceNow Instance (with REST API enabled)
- 🟢 ServiceNow credentials (username, password/API token)
- 🟢 HTTP Trigger App (or integrated alert source like Wazuh, Splunk, Email, etc.)

---

## 🪜 Step-by-Step Tasks

### 1. Trigger the Workflow
- Start the workflow using the HTTP Trigger app or any integrated source.
- The trigger should contain alert details like severity, description, source IP, and timestamp.

### 2. Normalize Alert Data
- Add a step to extract and organize relevant fields:
  - Incident title
  - Description or log message
  - Alert category or type
  - Source system name or hostname
  - Severity or priority level

### 3. Format Payload for ServiceNow
- Create a new JSON body or data structure required by ServiceNow API.
- Include key fields such as:
  - `short_description`
  - `description`
  - `urgency`
  - `category`
  - `caller_id` or system identifier

### 4. Connect to ServiceNow
- Use the **ServiceNow App** in Shuffle or generic **HTTP App** to send a POST request to:
