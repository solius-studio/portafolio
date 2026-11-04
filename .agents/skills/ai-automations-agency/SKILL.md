---
name: ai-automations-agency
description: >-
  Playbook and technical specifications for building, selling, and deploying commercial AI automations
  for Solius Studio (conversational agents, lead qualification, WhatsApp/CRM bots, n8n/Make workflows).
  Use whenever designing or implementing AI automations, chatbots, webhook integrations, or backend agents.
---

# Commercial AI Automations Playbook

## 1. Agency Value Proposition & Solution Types
Solius Studio specializes in 3 high-demand commercial automation products:

1. **Autonomous Lead Qualification & Intake Agent**:
   - Qualifies inbound prospects 24/7 via web chat or WhatsApp.
   - Collects budget, timeline, and project needs before a human sales call.
   - Routes qualified leads directly into CRM (Notion, Google Sheets, Airtable, or HubSpot).

2. **Smart Booking & Customer Service Agent (Local Businesses & Clinics)**:
   - Answers FAQs (pricing, location, services, availability).
   - Syncs with Google Calendar / Calendly for appointment scheduling.
   - Hands off gracefully to a human operator when human intervention is detected.

3. **Backend Business Workflow Automation**:
   - Webhook-driven pipelines with **n8n** or **Make.com**.
   - Automatic generation of invoices, summaries, and email/WhatsApp notifications upon form submissions.

---

## 2. Conversation Agent Architecture & System Prompt Standards
When writing prompts for business agents:
- **Tone**: Professional, concise, empathetic, and action-driven. Never sound robotic or overly verbose.
- **Guardrails**:
  - Never fabricate pricing or services outside the defined knowledge base.
  - Do not answer off-topic questions unrelated to the business.
  - State clearly that the assistant is an automated AI coordinator.
- **Fallback Rule**:
  - If the user asks 2 consecutive unanswerable questions, offer to connect directly with a team member via WhatsApp.

### System Prompt Template for Client Agents:
```text
Role: You are [Agent Name], the digital assistant for [Client Business].
Objective: Assist prospects by answering questions regarding services, qualifying their requirements, and scheduling appointments.

Rules:
1. Always keep answers under 3 short sentences.
2. Ask one qualifying question at a time.
3. Information to collect: Name, Service Needed, Estimated Timeline, Contact (Email/Phone).
4. If the user indicates urgency or high interest, invite them to book a consultation call: [Booking Link].
```

---

## 3. Webhook Integration Patterns (n8n & Make)
- In the frontend form or chat component, send a clean JSON payload to an endpoint or webhook:
  ```json
  {
    "lead_source": "website_landing_contact",
    "timestamp": "2026-11-04T17:00:00Z",
    "contact": {
      "name": "Jane Doe",
      "email": "jane@example.com",
      "phone": "+5491122334455"
    },
    "requirements": {
      "service": "AI Automation",
      "budget_range": "USD 500 - 1500",
      "notes": "Looking to automate client intake."
    }
  }
  ```

---

## 4. WhatsApp Integration Standard
- For client deliverables, prioritize:
  - **WhatsApp Business Cloud API** (official, scalable, template messages).
  - **Evolution API** or **Baileys** for direct self-hosted integration when clients require lower initial costs.
- Always include direct **click-to-chat WhatsApp links** on web interfaces:
  `https://wa.me/<number>?text=Hola%20Solius%20Studio,%20quiero%20cotizar...`
