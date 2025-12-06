# Automated Task Reminder (n8n Workflow)

## Overview
This repository contains an automation workflow built using **n8n**. The system functions as a personal assistant that automates the tracking of daily tasks. It performs an **ETL (Extract, Transform, Load)** process by fetching data from a Google Sheet, filtering for pending items, and sending a consolidated email notification.

## 📂 Workflow Architecture

![Workflow Diagram](workflow-diagram.png)

### Logic Flow
The workflow consists of four main stages:
1.  **Schedule Trigger:** Initiates the workflow automatically every day at **9:00 AM**.
2.  **Data Extraction (Google Sheets):** Connects to a "Daily Tasks" spreadsheet and fetches all rows.
3.  **Transformation & Filtering (If Logic):**
    - Checks the status of each task.
    - **Condition:** Filters rows where the `Done` column equals `"NO"`.
4.  **Notification (Gmail):** Sends an automated email containing the **Task Name**, **Date**, and **Status** for every pending item found.

## 🛠️ Tech Stack & Integrations
- **Orchestration Tool:** [n8n](https://n8n.io/)
- **Data Source:** Google Sheets API
- **Notification Service:** Gmail API
- **Data Format:** JSON

## 🚀 How to Use
1.  **Install n8n:** You can run n8n locally using npm or Docker, or use the cloud version.
2.  **Import Workflow:**
    - Download the [`workflow.json`](workflow.json) file from this repository.
    - In your n8n editor, go to **Workflows** > **Import from File** and select the JSON file.
3.  **Configure Credentials:**
    - Update the **Google Sheets** and **Gmail** nodes with your own OAuth2 credentials.
    - Select your own Spreadsheet and Sheet Name.
4.  **Activate:** Toggle the workflow to "Active" to start receiving daily reminders.

---
*This project demonstrates proficiency in API integrations, logic design, and process automation.*
