AI Avatar Lead Qualification & Data Collection System
n8n + HeyGen LiveAvatar Automation Project
1. Overview

This project demonstrates a fully automated AI Avatar Lead Qualification System built using n8n, HeyGen LiveAvatar Streaming API, and Google Sheets.
The workflow collects inputs from a custom n8n form, launches a real-time avatar, extracts information from the avatar’s transcript, and stores data in Google Sheets for lead management and reporting.

This system is designed as a proof-of-concept for using real-time conversational AI for automated customer qualification, onboarding, and data collection.

2. Features

Collect avatar configuration from users through an n8n form

Generate a real-time HeyGen LiveAvatar session using API

Auto-generate a landing page with embedded avatar

Extract structured lead information from conversation transcripts

Save leads directly into Google Sheets

Calculate usage statistics (interaction minutes and estimated cost)

Full logging and error-handling path

Production-ready workflow design

Optional LLM integration using HeyGen’s built-in language model

3. Technologies Used

n8n (workflow engine and automation platform)

HeyGen LiveAvatar Streaming API

Google Sheets API

HTML & JavaScript for dynamic landing page generation

Regular Expressions (Regex) for data extraction

LLM (internal to HeyGen) for conversational responses

4. Role of LLM

Although the technical instructions allowed using external LLMs (OpenRouter, Gemini), this workflow does not require an external LLM node.

This is because HeyGen LiveAvatar already includes an integrated LLM that:

Processes user messages

Generates avatar responses

Maintains conversation context

Produces transcript text

Therefore, the system is compliant with LLM requirements while maintaining a simpler and more efficient architecture.

5. Workflow Summary

The automation follows this sequence:

User submits the form with:

Avatar image

Knowledge base + prompt

Preferred language

n8n prepares the session configuration

n8n creates a live avatar session via HeyGen API

n8n generates a custom HTML landing page

Avatar interacts with the user through real-time conversation

Transcript is processed and key data is extracted

Extracted lead information is written into Google Sheets

Usage report is calculated and stored

Avatar session is closed through API

This completes an end-to-end automated lead qualification cycle.

6.Architecture Diagram:


[User Form] 
      │
      ▼
[Prepare Session Request]
      │
      ▼
[HeyGen LiveAvatar API]
      │
      ▼
[Generated HTML Landing Page]
      │
      ▼
[Conversation Transcript]
      │
      ▼
[Regex Extraction]
      │
      ├──> [Error Logging]
      ▼
[Lead Formatting]
      │
      ▼
[Google Sheets Storage]
      │
      ▼
[Usage Report]
      │
      ▼
[Close Avatar Session]


7.Files Included in This Repository:

DOCUMENTATION.md – Full-text technical documentation of the project

n8n-workflow.json – Exported n8n workflow

README.md – This file
8.How to Import the n8n Workflow

Open n8n

Go to Workflows → Import

Upload or paste the n8n-workflow.json file

Save and activate the workflow

Configure required credentials (Google Sheets + HeyGen API Key)

9. How to Use This Project

Run the workflow

Fill the form with:

Avatar image

Knowledge base

Prompt

Language

n8n returns a landing page URL

Open the page and interact with the avatar

After the session:

Lead data appears in Google Sheets

Usage/cost data is calculated

10. Challenges & Solutions

Challenge: Real-time avatar testing required API credits
Solution: Used test data mode and placeholder transcripts

Challenge: Extracting structured data from transcripts
Solution: Implemented regex-based parsing

Challenge: Google Sheets authentication
Solution: Configured service account credentials

Challenge: Keeping the workflow stable
Solution: Added error logging, validation checks, and session cleanup

11. License

This project is released under the MIT License.

12. Author

Asmit
AI / Automation Developer
n8n | HeyGen | LLM Integrations
