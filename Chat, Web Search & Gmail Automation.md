🌦️🤖 n8n AI Agent – Chat, Web Search & Gmail Automation

This repository contains an n8n workflow that implements a chat-based AI agent capable of understanding natural language requests, retrieving live data from the web, maintaining conversational memory, and performing real-world actions such as sending emails via Gmail.

A common use case demonstrated by this workflow is fetching weather information for a city and emailing the results automatically.

✨ Features

💬 Chat-triggered AI agent

🧠 OpenAI-powered reasoning

🗂️ Conversation memory with Simple Memory

🌍 Live web search using SerpAPI

📧 Automated Gmail emails

🌦️ Supports real-world tasks like weather reports via natural language

🧩 Workflow Overview

End-to-end flow:

A user sends a chat message (e.g. “Check the weather of Bangalore and email it to me”)

The AI Agent interprets the request

The agent:

Uses the OpenAI Chat Model to reason about intent

Reads/writes context using Simple Memory

Calls SerpAPI to fetch up-to-date weather information

Formats the response into an email

The Gmail node sends the email automatically

The agent confirms completion back in chat

🛠️ Nodes Used

When Chat Message Received
Trigger that starts the workflow when a user sends a chat message.

AI Agent
The central orchestrator that:

Understands user intent

Uses tools and memory

Decides when to send emails

OpenAI Chat Model
Handles reasoning, natural language understanding, and response generation.

Simple Memory
Stores short-term conversational context for follow-up requests.

SerpAPI
Retrieves live web data such as current weather and forecasts.

Gmail – Send a Message
Sends formatted emails automatically based on the agent’s output.

📦 Requirements

n8n (self-hosted or cloud)

OpenAI API key

SerpAPI API key

Google/Gmail credentials configured in n8n

Chat UI enabled in n8n

🚀 Setup Instructions

Clone this repository

Import the workflow JSON into n8n

Configure credentials:

OpenAI

SerpAPI

Gmail

Review and customize the AI Agent system prompt

Activate the workflow

Start chatting and trigger actions using natural language

🧪 Example Commands

“Check the weather of Bangalore and email it to me”

“Send today’s Mumbai weather to my email”

“Email a 7-day weather outlook for Delhi”

⚠️ Notes & Limitations

Simple Memory is session-based and short-term

Emails are sent immediately once triggered

SerpAPI usage depends on API limits

Clear prompting is important to avoid unintended emails

🔐 Security Considerations

Protect Gmail credentials carefully

Add confirmation logic before sending emails if needed

Restrict email recipients for safety

Monitor usage to prevent abuse or spam

🔧 Customization Ideas

Require user confirmation before sending emails

Add daily or scheduled weather emails

Store sent email logs

Format emails with HTML

Extend to calendar, Slack, or CRM integrations
