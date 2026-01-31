🤖 n8n AI Agent Chat Workflow

This repository contains an n8n workflow that implements a chat-based AI agent powered by OpenAI, with built-in memory and web search capabilities.

The workflow is designed to receive chat messages, reason about them using an LLM, optionally retrieve live information from the web, and respond conversationally while maintaining context.

✨ Features

💬 Chat-triggered AI agent

🧠 OpenAI Chat Model for reasoning and responses

🗂️ Conversation memory using Simple Memory

🌐 Web search via SerpAPI

🔌 Modular and easy to extend

🧩 Workflow Overview

Flow:

A chat message is received via the chat trigger

The AI Agent processes the message

The agent:

Uses the OpenAI Chat Model to reason and generate responses

Reads/writes conversation context using Simple Memory

Calls SerpAPI when real-time or factual information is needed

A single response is returned to the chat interface

🛠️ Nodes Used

When Chat Message Received
Trigger node that starts the workflow when a user sends a message.

AI Agent
Central orchestrator that manages reasoning, memory usage, and tool calls.

OpenAI Chat Model
Large language model used for understanding and generating responses.

Simple Memory
Stores short-term conversational context to enable follow-up questions.

SerpAPI
External tool for live web search when up-to-date information is required.

📦 Requirements

n8n (self-hosted or cloud)

OpenAI API key

SerpAPI API key

Chat UI enabled in n8n

🚀 Setup Instructions

Clone this repository

Import the workflow JSON into n8n

Configure credentials:

OpenAI API key

SerpAPI API key

Review the AI Agent system prompt (recommended)

Activate the workflow

Open the chat interface and start messaging

⚠️ Notes & Limitations

Simple Memory is short-term and not vector-based

Memory is session-scoped unless extended

SerpAPI usage depends on API limits and quotas

System prompt quality greatly affects agent behavior

🔧 Customization Ideas

Add a system prompt to control tone and rules

Replace Simple Memory with vector memory for long-term recall

Add logging or analytics nodes

Restrict or optimize tool usage

Format responses with Markdown or citations
