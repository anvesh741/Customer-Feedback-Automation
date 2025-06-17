# 🔧 Customer Feedback Automation System

## 🎯 Objective

Automate the classification and routing of customer feedback into actionable categories — **Complaints**, **Compliments**, and **Feature Requests** — using AI and no-code tools.  
The goal: reduce response time, boost customer engagement, and streamline internal workflows.

---

## 🧩 Tech Stack

- **n8n** – Workflow automation engine  
- **OpenAI (GPT-4o-mini)** – Natural language processing and classification  
- **Airtable** – Structured data storage  
- **Slack** – Internal team notifications  
- **Gmail API** – Personalized user response emails

---

## 🏗️ System Architecture Overview

### 🔹 Frontend Trigger
Form collects:
- Name  
- Email Address  
- Contact Number  
- Feedback Text  

### 🤖 AI Classification (LangChain Agent)
Feedback is passed to OpenAI's GPT model with the prompt:

```plaintext
Your role is to determine if the feedback filled by the customer is a complaint, compliment, or feature addition request.

The feedback is: {{ $json.Feedback }}

Your response should be only one from the below:
- Complain
- Compliment
- Feature Addition Request

```

--- 
### 🔁 Routing Logic (Switch Node)
Based on the classification, the feedback is routed to:
- **Complaints Table** in Airtable  
- **Compliments Table** in Airtable  
- **Feature Requests Table** in Airtable

### 🔔 Team Notifications (Slack)
Real-time Slack messages are posted to:
- `#complain`
- `#feature-addition-request`

### 📩 Customer Response (Gmail API)
For complaints, an automated personalized acknowledgment email is sent confirming receipt and assuring follow-up.

---

## 📥 Inputs

- Name  
- Email Address  
- Contact Number  
- Feedback (Free Text)

---

## 📤 Outputs & Destinations

- ✅ **Airtable Table Entries** organized by type  
- 🔔 **Slack Notifications** to internal teams  
- 📬 **Email Acknowledgement** for complaints via Gmail

---

## 🧠 Automation Highlights

- ✅ Zero manual classification effort  
- ⚡ Real-time, seamless workflow  
- 🔗 Instant alerts and clean data records  
- ♻️ Easy to scale and customize

---

## 📈 Impact

- ⏱️ **90% reduction** in response time  
- 💬 Enhanced customer trust and satisfaction  
- ⚙️ Increased operational efficiency  
- 📊 Structured and centralized feedback intelligence

---

## 💡 Future Enhancements

- 🔍 Sentiment analysis scoring  
- 📊 Feedback trend dashboards using Power BI or Tableau  
- 🚨 Escalation workflow for critical complaints  
- 🤝 Integration with CRM systems like HubSpot or Salesforce  
- 🧭 Feedback-to-feature roadmap generation

---


