# n8n AI Agents

![n8n](https://img.shields.io/badge/Built%20With-n8n-blue) ![AI](https://img.shields.io/badge/Powered%20by-OpenAI-lightgrey)

## Table of Contents

* [Linkedin Job Scraping Agent](#linkedin-job-scraping-agent)
* [Personal AI Assistant Agent](#personal-ai-assistant-agent)
* [RAG Agent with Pinecone Vector Store](#rag-agent-with-pinecone-vector-store)
* [RAG Agent with Deepseek Intelligence](#rag-agent-with-deepseek-intelligence)
* [Cold DM LinkedIn AI Agent](#cold-dm-linkedin-ai-agent)
* [AI Sales Agent](#ai-sales-agent)

This repository contains a collection of AI-powered agents designed to integrate seamlessly with [n8n](https://n8n.io/), an open-source workflow automation platform. Each agent is tailored to perform specific tasks such as job scraping, sales outreach, personal assistance, and information retrieval.

---

## Linkedin Job Scraping Agent

**Description:**
Scrapes job listings from LinkedIn using search criteria and formats them for downstream processing.

**Usage:**
To use this agent, follow these steps:

1. Import the JSON file into your n8n instance.
2. Update the job keywords and filters in the HTTP Request node.
3. Run the workflow manually or schedule it via Cron.

**Example Use Case:**

* Use this agent to collect a list of software engineering jobs from LinkedIn every morning and push the results to a Google Sheet.
* Use this agent to gather job postings for daily analysis or automate alerts for relevant job roles.

---

## Personal AI Assistant Agent

**Description:**
Acts as a general-purpose AI assistant for reminders, planning, and intelligent task execution.

**Usage:**

1. Import the JSON file into your n8n instance.
2. Connect Google Sheets or any task management tool.
3. Use manual or automated triggers to log tasks or retrieve responses.

**Example Use Case:**

* Set up a reminder and logging system that stores and retrieves tasks through Google Sheets based on natural language inputs.
* Keep track of your weekly tasks, set reminders, and receive personalized suggestions.

---

## RAG Agent with Pinecone Vector Store

**Description:**
AI-enhanced workflow involving OpenAI and custom automation logic.

**Usage:**

1. Import the workflow into n8n.
2. Set up vector document embedding and retrieval with Pinecone.
3. Enable OpenAI integration for context-aware response generation.

**Example Use Case:**

* Answer technical questions by matching queries to previously embedded documentation.
* Build a knowledge bot that provides factual answers from your documentation.

---

## RAG Agent with Deepseek Intelligence

**Description:**
Performs RAG (Retrieval-Augmented Generation) using DeepSeek's intelligence engine to analyze and answer queries.

**Usage:**

1. Import into n8n and configure API keys for Deepseek.
2. Provide access to the document index or API endpoint.
3. Trigger queries and extract summarized answers using Deepseek.

**Example Use Case:**

* Retrieve in-depth answers from research PDFs using semantic search and summarization.
* Perfect for researchers or teams that need semantic search over large corpora.

---

## Cold DM LinkedIn AI Agent

**Description:**
Sends personalized cold DMs to LinkedIn users using AI-generated messages based on lead data.

**Usage:**

1. Import the agent JSON into n8n.
2. Configure the source of leads (CSV, Google Sheet, or API).
3. Run the workflow to generate and send messages via the LinkedIn API or browser automation.

**Example Use Case:**

* Reach out to startup founders with custom DMs introducing your AI consulting services.
* Save time by letting this agent handle your cold outreach campaigns to hundreds of targeted users.

---

## AI Sales Agent

**Description:**
This AI-powered sales agent helps automate lead engagement, follow-ups, and intelligent messaging for closing deals.

**Usage:**

1. Import into n8n and connect your email or LinkedIn account.
2. Configure conditions for responses and action logic.
3. Trigger workflows based on lead interactions or CRM updates.

**Example Use Case:**

* Use this agent as a virtual SDR (Sales Development Rep) to initiate and maintain client communications.

---
