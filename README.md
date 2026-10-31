# Automated Sales Data Pipeline (n8n)

## Overview
This project is an end-to-end automated data pipeline built in **n8n**. It extracts raw sales data from an external API, applies conditional logic to filter delivered orders, aggregates regional sales totals, and automatically generates and emails an executive summary report with a dynamically generated CSV attachment.

## Business Impact
* **Eliminates Manual Data Entry:** Replaces manual CSV exports and spreadsheet math with instant API extraction.
* **Improves Accuracy:** Programmatically filters out unfulfilled orders before processing financial totals.
* **Speeds Up Reporting:** Instantly delivers actionable metrics (Total Revenue, Top Region, Order Count) directly to management inboxes.

## Technical Architecture
* **Trigger:** Manual trigger (can be adapted to Webhook or Cron Schedule for continuous execution).
* **Data Extraction:** `HTTP Request` node fetching JSON payloads from an external REST API.
* **Data Transformation:** `Item Lists` (Split Orders), `Set` nodes (math calculations), and `Aggregate` nodes to group data by region.
* **Routing:** `IF` node conditional logic to isolate "delivered" orders from pending statuses.
* **Output:** `Convert to CSV` and `Send Email` (SMTP) nodes handling binary file attachments and dynamic data expressions.

## Visual Proof
### 1. Complete Workflow Logic
*(Demonstrates branching logic, data aggregation, and API handling)*
![n8n Workflow](Screenshot%20from%202026-10-31%2014-16-44.png)

### 2. Automated Executive Output
*(Demonstrates dynamic variable injection and binary file handling)*
![Email Output](Screenshot%20from%202026-10-31%2014-17-26.png)


