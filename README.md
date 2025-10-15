<img width="709" height="168" alt="image" src="https://github.com/user-attachments/assets/c917ad10-aae5-4b65-9931-6d01dc43c8f2" />

# 📰 Auto News Publisher to X (Twitter) with AI & Tracking

A professional, automated workflow to discover breaking news, generate AI-based social content, and publish it directly to X (Twitter) — all while logging results and sending email notifications. Ideal for news organizations, content creators, social media managers, and businesses wanting to stay current and engaged.

---

## 🚀 Features

- 📝 **Form-Based Input** – Clean web interface to submit keywords and country.
- 📰 **Real-Time News Fetching** – Uses BrightData's Google News dataset.
- 🤖 **AI Content Generation** – GPT-4o powered tweet creation with smart hashtags.
- 📱 **Auto X Publishing** – Direct tweet posting with URL generation.
- 📊 **Google Sheets Logging** – Track all published tweets.
- 🔔 **Email Notifications** – Sends success email with tweet link.
- 🌍 **Multi-Country Support** – Localized news for US 🇺🇸, India 🇮🇳, UK 🇬🇧, and Australia 🇦🇺.
- ⚡ **Status Monitoring** – Real-time progress tracking with retry logic.
- 🛡 **Error Handling** – Robust error management and intelligent loops.

---

## 🧠 What This Workflow Does

### 🔹 Input:
- **News Name** – Keyword or topic (e.g., "AI breakthrough")
- **Country** – Select from `US`, `IN`, `GB`, `AU`

### 🔹 Processing Flow:

1. **Form Submission** → Webhook captures data.
2. **News Scraping** → BrightData fetches latest articles.
3. **Progress Check** → Intelligent status monitoring loop.
4. **Data Fetch** → Retrieve scraped articles.
5. **AI Tweet Generation** → GPT-4o crafts social post with hashtags.
6. **Publishing** → Posts to X (Twitter) automatically.
7. **Tracking** → Saves tweet content + URL to Google Sheets.
8. **Notification** → Sends success email with tweet link.

---

## 📥 Output Example

| Field         | Description                          | Example                                                                 |
|---------------|--------------------------------------|-------------------------------------------------------------------------|
| TweetMessage  | AI-generated tweet                   | "Breaking: AI transforming healthcare with 40% efficiency gains. #AI"  |
| TweetURL      | Direct tweet link                    | https://twitter.com/i/web/status/1234567890123456789                   |

---

## 🛠️ Setup Instructions

### ✅ Prerequisites:

- n8n instance (self-hosted or cloud)
- OpenAI GPT-4o access
- BrightData account (with Google News dataset)
- Twitter Developer account (API v2 access)
- Google Sheets & Gmail access

---

### 🔧 Step-by-Step Configuration

#### 1️⃣ Import the Workflow into n8n
- Go to n8n dashboard → **Add Workflow → Import from JSON**
- Paste the provided workflow JSON.

#### 2️⃣ Configure API Credentials
- **Twitter API:** Set up Twitter OAuth2 credential in n8n.
- **OpenAI API:** Add your GPT-4o key under OpenAI credential.
- **Gmail:** Configure Gmail OAuth2 and grant email-sending permissions.
- **BrightData API:** Use token `5662edde-6735-4c5d-a6c6-693043a5a9a5`.
- **Google Sheets:** Set up Sheets OAuth2 and authorize access.

#### 3️⃣ Google Sheets Setup
- Create a sheet named: `Publish Latest News on Social Media Platforms Using Keyword`
- Tab name: `Data`
- Columns:
  - `Tweet Message`
  - `Tweet URL`
- Update the **Sheet ID** in the workflow to match your sheet.

#### 4️⃣ Web Form Configuration
- Configure the form in the “On form submission” node.
- Fields:
  - News Name (Text)
  - Country (Dropdown: US, IN, GB, AU)
- Copy the webhook URL and test submission.

#### 5️⃣ Email Notifications
- Update Gmail node recipient to your email.
- Includes tweet message and URL.

---

## 🧪 Testing the Workflow

| News Name               | Country | Expected Result                              |
|-------------------------|---------|----------------------------------------------|
| artificial intelligence | US      | US-based AI news with tech hashtags          |
| cricket world cup       | IN      | India-specific cricket news content          |
| brexit update           | GB      | UK political news with #Brexit               |
| bushfire news           | AU      | Environmental updates from Australia         |

---

## 📊 Track Your Content

### 🔹 Google Sheets
- Stores tweet message and URL.
- Functions as your publishing audit log.

### 🔹 Email
- Confirms successful post with tweet link.

### 🔹 Twitter/X
- Engaging AI-optimized tweets with relevant hashtags.

---

###
MIT License

Copyright (c) 2025
