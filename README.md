# 🤖 MailAgent – AI Email Intelligence Agent

MailAgent is an AI-powered Email Intelligence Agent that connects to Gmail, monitors incoming emails, analyzes them using Google Gemini AI, identifies important information, and automatically sends an informative notification email when an important message is detected.

---

## 📌 Project Overview

Students and professionals receive many emails every day, including:

- Job opportunities
- Internship notifications
- Placement updates
- College announcements
- Registration notices
- Interview invitations
- Exams and deadlines
- Important documents
- General notifications

It is easy to miss an important email.

**MailAgent** solves this problem by continuously monitoring the Gmail inbox and using AI to understand incoming emails.

The agent determines whether an email is important and, if required, automatically sends a summarized notification email to a configured recipient.

---

## 🚀 Main Workflow

```text
                Incoming Email
                      │
                      ▼
                 Gmail Inbox
                      │
                      ▼
                  MailAgent
                      │
                      ▼
              Extract Email Data
                      │
                      ▼
                 Gemini AI
                      │
                      ▼
                Analyze Email
                      │
                      ▼
                Is Important?
                  /       \
                YES        NO
                 │          │
                 ▼          ▼
          Create Email    Ignore
                 │
                 ▼
             Gmail SMTP
                 │
                 ▼
        Send Notification Email
```

---

## ✨ Features

- 📧 Connects to Gmail
- 📥 Monitors unread incoming emails
- 🔍 Extracts sender, subject, body, and links
- 🤖 Uses Google Gemini AI for email analysis
- 🚨 Detects important emails
- 📊 Determines email priority
- 🏷️ Categorizes emails
- ✅ Detects whether an action is required
- 📅 Extracts explicitly mentioned deadlines
- 🏢 Identifies organizations
- 🔗 Extracts relevant registration/action links
- 📝 Generates AI-powered summaries
- 💡 Provides recommended actions
- 📤 Sends informative emails for important messages
- 🌐 Provides a web-based dashboard
- 🔄 Continuously monitors the inbox
- 🛡️ Avoids inventing information not present in the email

---

## 🧠 AI Email Analysis

For every incoming email, MailAgent analyzes:

```text
Importance
Priority
Category
Action Required
Action Type
Organization
Deadline
Registration Required
Registration URL
Summary
Reason
Recommended Action
```

### Example

```text
Email:

ABC Technologies is hiring Software Developer Interns.
Applications are open until 25 August 2026.

AI Analysis:

Important: TRUE
Priority: HIGH
Category: INTERNSHIP
Action Required: TRUE
Action Type: REGISTRATION
Organization: ABC Technologies
Deadline: 25 August 2026
```

---

## 🏗️ Project Architecture

```text
                    MAILAGENT
                        │
          ┌─────────────┼─────────────┐
          │             │             │
          ▼             ▼             ▼
      FRONTEND       BACKEND          AI
       Gradio         Python        Gemini
          │             │             │
          │             ▼             │
          │           Gmail            │
          │           IMAP              │
          │             │               │
          │             └──────┬────────┘
          │                    │
          │                    ▼
          │              AI Analysis
          │                    │
          │                    ▼
          │               Important?
          │                /       \
          │              YES        NO
          │               │           │
          │               ▼           ▼
          │          Gmail SMTP     Ignore
          │               │
          │               ▼
          │        Notification Email
          │
          ▼
      Web Dashboard
```

---

## 📁 Project Structure

```text
mailagent-ai-email-intelligence-agent/
│
├── frontend/
│   ├── app.py
│   ├── dashboard.py
│   ├── components.py
│   ├── callbacks.py
│   └── styles.py
│
├── backend/
│   ├── gmail.py
│   ├── email_parser.py
│   ├── email_sender.py
│   ├── agent.py
│   └── state.py
│
├── ai/
│   ├── analyzer.py
│   ├── prompts.py
│   └── response_parser.py
│
├── config/
│   ├── config.py
│   └── .env.example
│
├── data/
│   └── processed_emails.json
│
├── app.py
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 🛠️ Technologies Used

### Frontend

- Gradio
- HTML
- CSS

### Backend

- Python
- Gmail IMAP
- Gmail SMTP
- Python Email Library

### AI

- Google Gemini AI
- Google GenAI SDK

### Email Processing

- BeautifulSoup
- Python `email` module
- Regular Expressions
- JSON

---

# 💻 Requirements

Before running the project, install:

- Python 3.10+
- VS Code
- Gmail account
- Gmail App Password
- Google Gemini API Key
- Internet connection

---

# ⚙️ Installation

## 1. Clone the Repository

Open the VS Code terminal:

```bash
git clone https://github.com/YOUR_USERNAME/mailagent-ai-email-intelligence-agent.git
```

Go to the project folder:

```bash
cd mailagent-ai-email-intelligence-agent
```

---

## 2. Create Virtual Environment

Windows:

```bash
python -m venv venv
```

If `python` does not work:

```bash
py -m venv venv
```

---

## 3. Activate Virtual Environment

### Windows PowerShell

```bash
venv\Scripts\Activate.ps1
```

### Windows CMD

```bash
venv\Scripts\activate
```

After activation, you should see:

```text
(venv)
```

in your terminal.

---

## 4. Install Required Packages

```bash
pip install -r requirements.txt
```

If `requirements.txt` is missing or packages are missing:

```bash
pip install google-genai beautifulsoup4 gradio python-dotenv
```

---

# 🔐 Configuration

Create a `.env` file in the root project folder:

```text
mailagent-ai-email-intelligence-agent/
│
├── .env
├── app.py
├── frontend/
├── backend/
├── ai/
└── config/
```

Add:

```env
GMAIL_ADDRESS=your_email@gmail.com
GMAIL_APP_PASSWORD=your_gmail_app_password
GEMINI_API_KEY=your_gemini_api_key
FRIEND_EMAIL=recipient@gmail.com
CHECK_INTERVAL=30
GEMINI_MODEL=your_working_gemini_model
```

Replace the values with your actual credentials.

---

# 🔑 Gmail App Password

MailAgent uses Gmail IMAP to read emails and Gmail SMTP to send notification emails.

You should use a **Gmail App Password**, not your normal Gmail password.

Before creating an App Password:

1. Open your Google Account.
2. Enable 2-Step Verification.
3. Open App Passwords.
4. Create an App Password for MailAgent.
5. Copy the generated password.
6. Put it inside your `.env` file.

Example:

```env
GMAIL_APP_PASSWORD=abcdefghijklmnop
```

Do not upload this password to GitHub.

---

# 🤖 Gemini API Key

MailAgent uses Google Gemini AI to analyze emails.

Create your Gemini API key and add it to:

```env
GEMINI_API_KEY=your_api_key
```

Never publish your API key on GitHub.

---

# 🛡️ Security

Never upload:

```text
.env
venv/
__pycache__/
*.pyc
```

Your `.gitignore` should contain:

```text
.env
venv/
__pycache__/
*.pyc
```

---

# ▶️ Run the Project

After installation and configuration, activate the virtual environment:

```bash
venv\Scripts\activate
```

Then run the application:

```bash
python app.py
```

If your main application file is inside the frontend folder, use:

```bash
python frontend/app.py
```

---

# 🌐 Open the Web Application

After starting the application, the terminal should display something similar to:

```text
Running on local URL:
http://127.0.0.1:7860
```

Open the URL in your browser:

```text
http://127.0.0.1:7860
```

Your MailAgent web dashboard will now be available.

---

# 🖥️ Complete VS Code Commands

If someone downloads this project from GitHub, the complete setup is:

```bash
git clone https://github.com/YOUR_USERNAME/mailagent-ai-email-intelligence-agent.git
```

```bash
cd mailagent-ai-email-intelligence-agent
```

```bash
python -m venv venv
```

```bash
venv\Scripts\activate
```

```bash
pip install -r requirements.txt
```

Create `.env` and configure the credentials.

Then:

```bash
python app.py
```

Open:

```text
http://127.0.0.1:7860
```

---

# 🧪 How to Test

## Step 1 – Start the Application

```bash
python app.py
```

---

## Step 2 – Open the Dashboard

Open:

```text
http://127.0.0.1:7860
```

---

## Step 3 – Start MailAgent

Click the **Start Agent** button in the dashboard.

The agent will connect to Gmail and begin monitoring unread emails.

---

## Step 4 – Send a Test Email

Send an email to the Gmail account connected to MailAgent.

Example:

```text
Subject:
Software Developer Internship

Body:

ABC Technologies is hiring Software Developer Interns.

Applications are open until 25 August 2026.
Please complete the application before the deadline.
```

---

## Step 5 – Gemini Analysis

MailAgent reads the email and sends the relevant content to Gemini AI.

Example result:

```text
Important: TRUE
Priority: HIGH
Category: INTERNSHIP
Action Required: TRUE
Action Type: REGISTRATION
Organization: ABC Technologies
Deadline: 25 August 2026
```

---

## Step 6 – Notification Email

If the email is classified as important, MailAgent creates an informative notification email and sends it to the configured recipient.

---

# 📧 Example Notification

```text
Subject:
🚨 Important: ABC Technologies - INTERNSHIP

Hi,

I received an important email and MailAgent analyzed it.

Category:
INTERNSHIP

Priority:
HIGH

Organization:
ABC Technologies

Action Required:
TRUE

Deadline:
25 August 2026

AI Summary:
ABC Technologies is offering Software Developer
Internship opportunities with an application deadline
of 25 August 2026.

Recommended Action:
Complete the internship application before the deadline.

Regards,
MailAgent
AI Email Intelligence Agent
```

---

# 🔄 Continuous Monitoring

MailAgent continuously monitors the Gmail inbox.

```text
Check Gmail
     ↓
Find unread emails
     ↓
Extract email information
     ↓
Send content to Gemini
     ↓
Analyze email
     ↓
Important?
     ↓
 ┌───┴────┐
YES       NO
 │         │
 ▼         ▼
Send      Ignore
Email
 │
 ▼
Wait
 │
 ▼
Check Gmail Again
```

The monitoring interval is configured using:

```env
CHECK_INTERVAL=30
```

The value is in seconds.

---

# 🛡️ Safety and Limitations

MailAgent does **not** automatically:

- Apply for jobs
- Register for opportunities
- Submit forms
- Make payments
- Send job applications
- Change account information
- Perform external actions

MailAgent only:

```text
Read Email
     ↓
Analyze Email
     ↓
Generate Summary
     ↓
Notify User
```

Users should verify important information from the original email before taking any important action.

---

# 🎯 Project Objective

The objective of MailAgent is to develop an AI-powered email assistant that can automatically understand incoming emails, identify important information, prioritize messages, generate useful summaries, and notify users about emails that require attention.

---

# 🔮 Future Scope

Future improvements can include:

- Gmail OAuth 2.0 authentication
- Database integration
- Job application tracking
- Automatic follow-up reminders
- Calendar integration
- AI-generated email replies
- Email search and filtering
- Mobile application
- Cloud deployment
- WhatsApp or Telegram notifications
- Job application deadline tracking
- Resume matching with job emails

---

# 👩‍💻 Author

**Vijaya Pawar**

B.Tech – Computer Science and Engineering

DKTE's Textile & Engineering Institute, Ichalkaranji

---

# 📄 License

This project is developed for educational and academic purposes.
