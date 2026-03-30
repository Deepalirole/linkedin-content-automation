# 🤖 LinkedIn Content Automation System

An end-to-end AI-powered LinkedIn content 
automation pipeline built with n8n.

## 🚀 What It Does

- Fetches trending topics every Monday automatically
- Researches each topic using real-time web data
- Generates LinkedIn posts using Google Gemini AI
- Creates matching banner images automatically
- Saves all assets to Google Drive
- Logs everything in a content calendar
- Runs fully autonomously every day

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| n8n | Workflow orchestration |
| Google Gemini API | AI content generation |
| Tavily API | Real-time web research |
| Pollinations.ai | AI image generation |
| Google Sheets | Content storage & calendar |
| Google Drive | Image storage |

## 📁 Workflows

### 1. Main Workflow
`workflows/linkedin-content-creator.json`
- Runs daily at 9am
- Picks topic → researches → generates → saves

### 2. Auto-fill Topic Workflow  
`workflows/topic-auto-refill.json`
- Runs every Monday at 8am
- Fetches 5 trending topics → adds to sheet

## ⚙️ Setup Instructions

### Prerequisites
- n8n account
- Google Gemini API key
- Tavily API key
- Google account (Sheets + Drive)

### Steps
1. Import both workflow JSON files into n8n
2. Add your API credentials
3. Set up Google Sheets with columns:
   - Topic, Status, Content, Image_URL
4. Activate both workflows
5. Done! 🎉

## 📊 Google Sheets Structure

### LinkedIn Posts Sheet
| Column | Purpose |
|--------|---------|
| Topic | Post topic |
| Status | To Do / Created |
| Content | Generated post |
| Image_URL | Drive image link |

### Calendar Tab
| Column | Purpose |
|--------|---------|
| Topic | Post topic |
| Date_Generated | Creation date |
| Character_Count | Post length |
| Status | Created |

## 🔄 Workflow Architecture
```
Schedule Trigger (9am daily)
        ↓
    Get Topic
        ↓
Tavily Web Research
        ↓
Content Creator (Gemini AI)
        ↓
Image Generation (Pollinations)
        ↓
Upload to Google Drive
        ↓
Update Google Sheets
        ↓
Update Content Calendar
```

## 📸 Workflow Screenshot

<img width="1742" height="772" alt="Screenshot 2026-03-20 202447" src="https://github.com/user-attachments/assets/2deebf9a-87f3-491b-a653-5e66813673c0" />





github.com/YOUR-USERNAME/linkedin-content-automation
