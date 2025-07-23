# 🎓 Academic Stack Planner (n8n Workflow)

This project is an **automated academic planning tool** built with **n8n**, designed to generate a personalized semester-specific roadmap for students pursuing **B.Tech / B.S** or **BCA**. It uses **Google Gemini API** to intelligently construct HTML roadmaps and automatically sends them via Gmail and schedules tasks into **Google Calendar**.

---

## ✨ Features

- 🗓️ Builds a 6-month academic roadmap for the chosen tech stack (AI/ML, Full Stack, Cybersecurity, etc.)
- ✉️ Automatically emails a personalized plan in HTML format
- 📆 Adds each roadmap task to your Google Calendar
- ⚡ Parses HTML output and converts it into structured calendar events
- ✅ Fully customizable and extensible in n8n's visual editor

---

## ⚙️ How It Works

1. Student fills a form with name, year, stack, level, etc.
2. Gemini AI generates a clean HTML-based semester roadmap
3. A code node extracts the email and HTML body for Gmail
4. Another code node splits roadmap into timed tasks over the semester
5. Gmail sends the email with the roadmap
6. Google Calendar schedules each task evenly across 6 months

---

## 📁 Setup Instructions

### 🧠 Step 1: Import the Workflow

1. Clone this repository or download `academic_stack_planner_email_updated.json`
2. Open your local or cloud **n8n** instance
3. Go to **Workflows → Import**
4. Paste or upload the workflow JSON

### 🔐 Step 2: Set Required Credentials

| Service           | Type              | Scope                                      |
|-------------------|-------------------|---------------------------------------------|
| Gmail             | Gmail OAuth2      | `https://www.googleapis.com/auth/gmail.send` |
| Google Calendar   | Calendar OAuth2   | `https://www.googleapis.com/auth/calendar`   |
| Gemini AI         | API Key / Gemini  | Use Google AI Studio                        |

---

## 🧪 Sample Input Form

```json
{
  "Enter is your name?": "Krishna",
  "Enter is your discipline of study?": "B.Tech / B.S",
  "Enter year are you in?": "3",
  "Which stack would you like the roadmap to be on?": "AI/ML",
  "Enter is your current level of understanding?": "Intermediate",
  "Briefly describe your current skills (only keywords)?": "Python, ML basics",
  "Enter is your email id?": "krishnabhatia09@gmail.com"
}
```

---

## 🛠 Notes

- Email ID fallback is set to `prateek6394121233singh@gmail.com` if not extracted automatically.
- Semester duration is July 15 – Nov 15 (can be edited in Code node).
- Works well with hosted n8n or self-hosted instance.
- Highly adaptable for other educational use cases.

---

## 📌 Status

✅ Ready to use  
🧠 Gemini AI included  
📅 Calendar Automation included  
📤 Gmail sending configured

---

## 📂 File

This repo contains:

- `academic_stack_planner_email_updated.json` — n8n workflow export file
- `README.md` — this documentation
