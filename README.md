# CPQ Alert System for Meta Ads

## Table of Contents

1. [Overview](#overview)  
2. [Features](#features)  
3. [Prerequisites](#prerequisites)  
   - [Python Libraries](#1-python-libraries)  
   - [Environment Variables](#2-environment-variables)  
4. [Key Functions](#key-functions)  
   - [Meta Ads Metrics](#1-meta-ads-metrics)  
   - [Pipefy Metrics](#2-pipefy-metrics)  
   - [Email Alerts](#3-email-alerts)  
   - [Slack Notifications](#4-slack-notifications)  
   - [CPQ Calculation and Alerting](#5-cpq-calculation-and-alerting)  
5. [Cost-Free Automation](#cost-free-automation)

---
   
## Overview

The CPQ Alert System for Meta Ads addresses the critical need for performance monitoring in advertising campaigns. By calculating the Cost Per Qualification (CPQ), this project helps businesses identify underperforming campaigns or ads in real-time.

With a focus on actionable insights, the project automates the detection of campaigns where the CPQ exceeds a specified threshold. Alerts are sent via email and Slack, enabling prompt decision-making and performance optimization. By integrating data from Meta Ads and Pipefy, it provides a comprehensive view of campaign effectiveness by connecting spend metrics with lead qualification data.

---

## Features

- **Meta Ads API Integration**: Retrieves campaign metrics like spend and campaign details.
- **Pipefy API Integration**: Fetches leads and their qualification status.
- **Email Alerts**: Sends performance alerts when the CPQ exceeds the defined threshold.
- **Slack Notifications**: Posts alerts to a Slack channel.
- **Dynamic Data Filtering**: Filters data based on recency for accurate and actionable insights.
- **Cost Analysis**: Calculates CPQ at the ad and campaign levels for focused optimization.

---

## Prerequisites

### 1. Python Libraries
Install the required Python packages using:

```bash
pip install -r requirements.txt
```

### 2. Environment Variables
Ensure the following environment variables are set:

| **Variable**           | **Name**                     | **Description**                                      |
|------------------------|------------------------------|------------------------------------------------------|
| `META_ACCESS_TOKEN`    | Meta Ads API Token           | Access token for the Meta Ads API.                   |
| `AD_ACCOUNT_ID`        | Meta Ads Account ID          | Meta Ads account ID.                                 |
| `SLACK_TOKEN`          | Slack API Token              | Token for Slack API authentication.                  |
| `PIPEFY_TOKEN`         | Pipefy API Token             | Token for Pipefy API authentication.                 |
| `PIPEFY_PIPE_ID`       | Pipefy Pipe ID               | Token for Pipefy's Pipe identification               |
| `PIPEFY_REPORT_ID`     | Pipefy Report ID             | Token for Pipefy's report identification             |
| `EMAIL`                | Email Sender Address         | Email address to send alerts from.                   |
| `EMAIL_TO`             | Email Recipient Address      | Email address to send alerts to.                     |
| `EMAIL_PASSWORD`       | Email Password               | Password for the app created in the email account.   |

> Set these variables in your `.env` file or directly in your environment.


---
## Key Functions
### 1. Meta Ads Metrics
Fetches campaign data such as spend and campaign details using Meta's API:

```python
def get_meta_ads_metrics():
    ...
```

### 2. Pipefy Metrics
Integrates data from Pipefy's GraphQL API to analyze leads:

```python
def get_pipefy_metrics():
    ...
```

### 3. Email Alerts
Sends an email notification when performance thresholds are exceeded:

```python
def send_email(subject, message):
    ...
```

### 4. Slack Notifications
Posts a message to a specified Slack channel:

```python
def send_slack_message(message):
    ...
```

### 5. CPQ Calculation and Alerting
Combines data from Meta Ads and Pipefy to calculate CPQ and trigger alerts:

```python
def check_metrics():
    ...
```

---

## Cost-Free Automation
This project leverages GitHub Actions to automate the script execution without incurring infrastructure costs. The included workflow file (.github/workflows/check_metrics.yml) schedules the script to run hourly and allows manual execution when needed. Key details of this automation setup include:

* Schedule Execution: The cron setting ensures the script runs consistently every day at the specified time.
* Manual Execution: The workflow_dispatch trigger allows users to run the script on demand.
* Dependency Management: The workflow automatically installs dependencies specified in requirements.txt during execution.
* Environment Variables: Sensitive data such as API tokens and email credentials are securely stored and accessed via GitHub Secrets.
* By using GitHub Actions, the project ensures regular execution without the need for external servers or additional hosting services, making it highly cost-efficient for continuous monitoring.
