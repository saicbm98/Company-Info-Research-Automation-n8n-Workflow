# Company Info Research Automation | n8n Workflow

> **Automating company research with intelligent web scraping, LLM analysis, and document generation**

![n8n Workflow Screenshot](./assets/workflow-screenshot.png)
*Add your n8n canvas screenshot here showing the complete workflow*

---

## 🎯 Project Overview

An end-to-end automation workflow that transforms company website URLs into actionable outreach intelligence for job seekers. Built to demonstrate production-ready AI operations skills through practical application.

**The Problem:** Researching companies for job applications is time-consuming and inconsistent. Manually visiting websites, extracting key information, and structuring outreach materials takes 30-45 minutes per company.

**The Solution:** A no-code AI workflow that scrapes company websites, analyzes content using GPT-4o-mini, and generates structured research reports in Google Docs—reducing research time by ~85% (to under 5 minutes per company).

---

## 🚀 What This Demonstrates

### **AI Operations & Automation Engineering Skills**
- **End-to-end workflow design**: Form trigger → HTTP scraping → data transformation → LLM processing → document automation
- **Prompt engineering**: Crafted system messages and user prompts to extract structured, actionable insights from unstructured web content
- **Error handling & debugging**: Implemented data validation, credential management, and workflow testing
- **Integration orchestration**: Connected 5+ services (n8n, OpenAI GPT-4o-mini, Google Docs, HTTP APIs) into a cohesive pipeline

### **Operational Thinking**
This project applies the same operational mindset I've used across insurance analysis, community operations, and customer ops: **identify inefficiency → automate with AI → measure impact**.

---

## 🏗️ Architecture & Workflow

### **High-Level Flow**
```
User Input (Form) → Web Scraping → HTML Cleaning → AI Analysis → Document Generation
```

### **Technical Components**

| Node | Technology | Function |
|------|------------|----------|
| **Form Trigger** | `n8n-nodes-base.formTrigger` | Public form for URL submission, webhook-based trigger |
| **HTTP Request** | `n8n-nodes-base.httpRequest` | Fetches raw HTML from target company website |
| **Markdown Converter** | `n8n-nodes-base.markdown` | Transforms HTML → clean Markdown for LLM processing |
| **AI Agent** | `@n8n/n8n-nodes-langchain.agent` | GPT-4o-mini analysis with structured output |
| **Google Docs** | `n8n-nodes-base.googleDocs` | Appends report to centralized research document |

### **AI Agent Output Structure**

The AI extracts 6 categories of intelligence:
1. **Core business** - One-liner + detailed explanation
2. **Products/services** - Features, users, integrations
3. **Culture/values** - Evidence-based only (no guessing)
4. **Leadership** - Names and backgrounds
5. **Ideal candidate fit** - 6-12 actionable bullets
6. **Outreach fuel** - Angles, questions, email templates

---

## 🧠 Prompt Engineering

### **System Message Strategy**
```
Role definition: "You are a website research assistant for job-seeker outreach"
Constraints: "Use ONLY information present in the provided text. Do not guess."
Output structure: 6 sections with specific formatting (bullets, headings, word counts)
Quality controls: "Avoid buzzwords. Translate marketing language into plain English."
```

### **User Message Strategy**
- Dynamic context injection from form input
- Explicit fallback instructions: "If leadership details are not in the text, write 'Not found on website'"
- Structured output request: "Return plain text with exact headings requested"

This separation ensures consistent AI behavior across all company analyses while allowing dynamic data input.

---

## 📊 Results

| Metric | Value |
|--------|-------|
| **Time savings** | ~85% reduction (30-45 min → 5 min per company) |
| **Processing time** | ~17 seconds per company |
| **Output consistency** | 100% structured format across all analyses |
| **Throughput** | 10+ companies/hour vs. 1-2 manually |

---

## 🛠️ Technical Stack

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Workflow Engine** | n8n (cloud) | Visual automation platform |
| **LLM** | OpenAI GPT-4o-mini | Cost-effective natural language analysis |
| **Web Scraping** | HTTP Request node | Company website data extraction |
| **Data Transformation** | Markdown node | HTML → clean text conversion |
| **Output Storage** | Google Docs API | Centralized research repository |
| **Trigger** | Form Trigger (webhook) | User input collection |

---

## 🔧 Setup & Deployment

### **Prerequisites**
- n8n instance (cloud or self-hosted)
- OpenAI API key
- Google Cloud project with Docs API enabled
- OAuth2 credentials for Google Docs

### **Installation**

1. **Import Workflow**
```bash
   # In n8n: Settings → Import from File → Select workflow.json
```

2. **Configure Credentials**
   - OpenAI: Add API key in n8n credentials
   - Google Docs: Complete OAuth2 flow for document access

3. **Activate & Test**
   - Toggle workflow to "Active"
   - Copy the form URL from the trigger node
   - Submit a company URL and check the Google Doc output

### **Customization Options**
- **Change output format**: Modify AI Agent system message
- **Add data sources**: Insert additional HTTP Request nodes before AI analysis
- **Switch LLM provider**: Replace OpenAI node with Anthropic/Gemini
- **Change output destination**: Replace Google Docs with Notion, Airtable, or email

---

## 🎓 Challenges & Solutions

| Challenge | Solution |
|-----------|----------|
| HTML noise (nav, footers, scripts) | Markdown conversion before LLM processing |
| Inconsistent AI outputs | Explicit constraints and examples in system prompt |
| Google OAuth token expiry | Fresh credential creation workflow |
| AI skipping sections | Added explicit "write 'Not found'" instructions |

---

## 📂 Repository Structure
```
n8n-research-bot/
├── assets/
│   └── workflow-screenshot.png
├── workflow.json
└── README.md
```

---

## 🤝 Connect

**Creator:** Sai Medicherla  
**Specialties:** AI Operations • Automation Engineering • No-Code AI Solutions

**Let's Connect:**
- 🌐 Portfolio: [linkedin-replacer](https://linkedin-replacer-127790892770.us-west1.run.app/)
- 🐦 X/Twitter: [@mscb160798](https://x.com/mscb160798)
- 💼 Wellfound: [Sai Medicherla](https://wellfound.com/u/sai-medicherla)
- 💻 GitHub: [@saicbm98](https://github.com/saicbm98)

**Open to:** AI Operations • Automation Engineering • Product Operations  
**Availability:** 🟢 Immediate start

---

## 📜 License

MIT License - fork, modify, and use freely.

---

⭐ **If this helped you, consider starring the repo!**
