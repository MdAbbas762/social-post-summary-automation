# 🚀 Social Post Summary Automation

This project implements a complete automation pipeline that accepts social media post URLs, extracts their content using platform-specific scrapers, summarizes each post with AI, and delivers the results in a structured email.

---

## 📖 Overview

This repository contains a Zapier automation that collects social media post URLs submitted through a Google Form and converts them into AI-generated summaries. The workflow integrates Google Forms, Apify, OpenAI, and Gmail to automate the complete process from data collection to email delivery.

Instead of manually opening posts across different social media platforms, reading their content, and creating summaries, the workflow performs every step automatically. Once the form is submitted, each social media link is processed independently, summarized using AI, and combined into a single email sent to the user.

---

## 🎯 Objective

The objective of this automation is to reduce the time required to review social media content from multiple platforms by creating a centralized AI-generated summary.

The workflow is designed to:

- Collect social media post URLs from a single Google Form.
- Extract post content from each platform automatically.
- Generate concise AI summaries for every submitted post.
- Deliver all summaries in a single organized email.

---

## 🏗️ Automation Architecture

The automation follows the pipeline below:

```text
Google Form
      │
      ▼
Capture Form Data
      │
      ▼
Apify Platform Tasks
(TikTok • Instagram • Facebook • LinkedIn)
      │
      ▼
Extract Post Content
      │
      ▼
OpenAI (ChatGPT)
      │
      ▼
Generate Individual Summaries
      │
      ▼
Compile Email Content
      │
      ▼
Send Email via Gmail
```

---

## ⚙️ Automation Flow

### Step 1 — Google Form Submission

The workflow begins when a user submits a Google Form.

The form collects:

- Name
- Email Address
- TikTok Post URL
- Instagram Post URL
- Facebook Post URL
- LinkedIn Post URL

This submission automatically triggers the Zapier workflow.

---

### Step 2 — Content Extraction with Apify

Apify is used to extract the actual content from every submitted social media post.

Instead of relying on a single scraper, a dedicated scraper was configured for each supported platform.

The implementation process included:

- Searching the Apify Store for the appropriate scraper.
- Selecting the most suitable Actor for each platform.
- Saving each Actor as an Apify Task.
- Calling each Task from Zapier to process the submitted URLs.

Platform-specific Tasks:

- TikTok → TikTok Post Scraper
- Instagram → Instagram Post Scraper
- Facebook → Facebook Post Scraper
- LinkedIn → LinkedIn Post Scraper

Each Task returns the textual content of its respective social media post, which becomes the input for the AI summarization stage.

---

## 🤖 AI Processing

After the content is extracted, each post is processed using OpenAI.

A structured prompt is provided to the language model for every platform independently. The model analyzes the extracted content and produces a concise summary that captures the main idea while removing unnecessary details.

Processing each platform separately keeps the summaries organized and prevents content from different posts from being mixed together.

---

## 📧 Email Delivery

After all summaries have been generated, Zapier compiles them into a single email.

The email contains separate sections for each submitted platform, allowing the recipient to review every summarized post from one place without opening the original social media links.

This provides a clean, centralized report of all submitted content.

---

## ✨ Key Features

- Automated Google Form trigger.
- Multi-platform social media support.
- Platform-specific Apify Tasks.
- AI-generated summaries using OpenAI.
- Fully automated end-to-end workflow.
- Consolidated email containing summaries from all submitted platforms.
- No manual review or summarization required.

---

## 🛠️ Technology Stack

| Technology | Purpose |
|------------|---------|
| Google Forms | Collect user information and post URLs |
| Zapier | Workflow orchestration |
| Apify | Social media content extraction |
| OpenAI (ChatGPT) | AI-powered summarization |
| Gmail | Email delivery |

---

## 📸 Workflow

![Workflow](screenshots/workflow.png)

---

## 💡 Use Case

This automation is suitable for content creators, digital marketers, agencies, researchers, and businesses that regularly review social media content from multiple platforms.

By automating content extraction and summarization, the workflow reduces manual effort while providing a consistent and easy-to-read overview of submitted posts.

---

## 📂 Repository Structure

```text
social-post-summary-automation/
│
├── README.md
└── screenshots/
    └── workflow.png
```

---

## 🤝 Connect With Me

**Muhammad Abbas**

Software Engineer • AI Automation Engineer

[![GitHub](https://img.shields.io/badge/GitHub-View%20Profile-0969DA?style=for-the-badge&logo=github&logoColor=white)](https://github.com/MdAbbas762)

[![Email](https://img.shields.io/badge/Email-Contact%20Me-F97316?style=for-the-badge&logo=gmail&logoColor=white)](mailto:abbas63891@gmail.com)