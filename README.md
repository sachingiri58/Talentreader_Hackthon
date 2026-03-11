"# Talentreader_Hackthon" 
# 🦅 TalentRadar — Autonomous Hiring Intelligence Platform

> Powered by **TinyFish Web Agent API** · Built for TinyFish Hackathon 2026

Live Demo: (https://talentreader-hackthon.vercel.app/ )
[![Powered by TinyFish](https://img.shields.io/badge/Powered%20by-TinyFish-orange)](https://tinyfish.ai)

---

## 🎯 What is TalentRadar?

TalentRadar deploys **parallel autonomous web agents** to scrape live job boards and company careers pages in real-time — extracting salary data, required skills, seniority levels, and hiring trends across your competitors.

**No mock data. No static pages. Real agents navigating real websites.**

---

## 🚨 The Problem

Recruiting teams and talent ops leaders spend **hours every week** manually checking:
- What are competitors paying for the same roles?
- Which skills are most in demand right now?
- Who is hiring aggressively vs. freezing headcount?

Existing tools (Radford, Levels.fyi Pro, Greenhouse Market Data) cost **$10,000–$20,000/month**.

**TalentRadar does this in 90 seconds for free.**

---

## ⚡ How It Works

TalentRadar deploys **7 autonomous TinyFish agents in parallel**:

| Agent | Target | What It Does |
|-------|--------|-------------|
| 💼 LinkedIn Jobs | linkedin.com/jobs | Searches, scrolls, extracts listings |
| 🔍 Indeed | indeed.com | Finds salary ranges + posting dates |
| 🚪 Glassdoor | glassdoor.com | Extracts compensation data (stealth mode) |
| 🏢 Stripe | stripe.com/careers | Navigates careers page, finds roles |
| 🏢 OpenAI | openai.com/careers | Finds matching job titles + pay |
| 🏢 Figma | figma.com/careers | Extracts open engineering roles |
| 🏢 Vercel | vercel.com/careers | Pulls live job postings |

Each agent:
1. **Navigates** to the target URL
2. **Searches** for the specified role
3. **Scrolls** through results
4. **Extracts** structured JSON data
5. **Streams** real-time events via SSE back to the dashboard

---

## 🧠 Intelligence Generated

After agents complete their mission, TalentRadar generates:

- 📊 **Jobs Table** — 85+ real postings with salary, level, skills, location
- 💰 **Salary by Seniority** — median pay at each level (junior → staff → principal)
- 🔧 **Top Skills Heatmap** — most demanded technologies across all postings
- 📈 **Level Distribution** — senior vs mid vs junior hiring ratio
- 🔔 **Intel Alerts** — automatic signals like "competitor is out-of-market on comp"

---

## 🏗️ Technical Architecture

```
User Input (role, companies, location)
        ↓
Mission Builder → generates N agent configs
        ↓
Parallel fetch() → TinyFish SSE API
  POST https://agent.tinyfish.ai/v1/automation/run-sse
  Headers: X-API-Key, Content-Type
  Body: { url, goal, browser_profile }
        ↓
SSE Stream → real-time event parsing
  NAV / SEARCH / SCROLL / CLICK / READ / COMPLETE
        ↓
JSON extraction → normalization → analytics
        ↓
Dashboard: Jobs Table + Intelligence Brief + Alerts
```

**Key Technical Choices:**
- **Stealth browser profile** for LinkedIn & Glassdoor (anti-bot bypass)
- **Parallel Promise.allSettled()** — all agents run simultaneously
- **Structured extraction prompts** — agents return normalized JSON directly
- **SSE stream parsing** — every agent action shown in real-time
- **Zero backend** — pure frontend, single HTML file

---

## 💼 Business Case

**Target Buyer:** Recruiting leads, talent ops, VC-backed startups scaling engineering

**Pain Point:** Manual competitive salary benchmarking costs 5–10 hours/week per recruiter

**Value Prop:** 90-second automated competitive intelligence sweep

**Revenue Model:**
- Free tier: 3 runs/month
- Pro: $299/month — unlimited runs, Slack alerts, CSV export
- Enterprise: $999/month — API access, custom sources, team seats

**TAM:** $4.2B HR analytics market, 50,000+ companies hiring engineers globally

---

## 🚀 Live Results (Demo Run)

- ✅ **85 jobs found** in one run
- ✅ **$219k median salary** extracted from live data
- ✅ **7 agents** ran in parallel
- ✅ **3 intelligence signals** auto-generated
- ✅ Real data from Vercel, OpenAI, Stripe, LinkedIn

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Web Agent API | TinyFish (`/v1/automation/run-sse`) |
| Frontend | Vanilla HTML/CSS/JS (single file) |
| Hosting | Vercel |
| Font | Fraunces + IBM Plex Mono |
| Data Export | JSON / CSV |

---

## 🔧 Setup & Usage

1. Get a free TinyFish API key at [agent.tinyfish.ai](https://agent.tinyfish.ai)
2. Open the app
3. Paste your API key in the sidebar
4. Enter a job role (e.g. "Senior Software Engineer")
5. Add competitor company domains
6. Select data sources (LinkedIn, Indeed, Glassdoor, Careers Pages)
7. Click **Deploy Agents**
8. Watch agents navigate live websites in real-time
9. View jobs table + intelligence brief

---

## 📁 Project Structure

```
talentreader.html    ← entire app (single file)
README.md            ← this file
```

---

## 👤 Builder

**Sachin Giri**
- GitHub: [@sachingiri58](https://github.com/sachingiri58)
- Email: sachinggiri01@gmail.com

---

## 🏆 Hackathon

Built for the **TinyFish Web Agent Hackathon 2026**

> *"If your application can be built without a web agent navigating real websites, it's not a fit."*
> — TinyFish Hackathon Brief

TalentRadar **cannot** function without real browser agents. Every data point comes from live web navigation. This is not a wrapper. This is not a chatbot. This is an autonomous agent doing real labor on the live web.

---

*Made with ☕ and TinyFish agents*