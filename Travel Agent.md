🤖 Multi-Agent Chat Planner Workflow (n8n)

This n8n workflow implements a two-stage AI agent system that turns a chat message into an actionable plan and executes real-world searches (flights, hotels, general web) using external APIs.

At a high level:

AI Agent interprets the user’s message.

Planner Agent decides what tools to call.

Search tools (Tavily + SerpAPI) fetch live data.

Structured Output Parsers ensure clean, machine-readable results.

🧠 Architecture Overview

Trigger → AI Agent → Planner Agent → Tools → Structured Output

Agents

AI Agent

Handles initial user intent understanding

Produces structured intermediate output

Planner Agent

Decides which tools to invoke

Can call multiple tools in parallel

Aggregates results into a structured response

Tools Used

Tavily Search

General web search

SerpAPI – Google Flights

Flight search

SerpAPI – Google Hotels

Hotel search

Models

OpenAI Chat Models are used by both agents

Each agent has its own memory and output parser

🧩 Workflow Diagram
When chat message received
        ↓
     AI Agent
        ↓
   Planner Agent
     ↙    ↓    ↘
 Tavily  Hotels  Flights
        ↓
 Structured Output

⚙️ Nodes Breakdown
1. When Chat Message Received

Trigger node

Starts the workflow when a user sends a chat message

2. AI Agent

Purpose: Intent extraction & reasoning

Components:

OpenAI Chat Model

Chat Memory

Structured Output Parser

Output:

Clean, structured interpretation of the user request

3. Planner Agent

Purpose: Task planning & tool orchestration

Components:

OpenAI Chat Model

Chat Memory

Structured Output Parser

Behavior:

Chooses which search tools to call

Can invoke multiple tools in parallel

Normalizes results into a single response

4. Search Tools

Search in Tavily

Used for general knowledge or web queries

Google Flights (SerpAPI)

Used when travel planning requires flight data

Google Hotels (SerpAPI)

Used for hotel availability and pricing

5. Structured Output Parsers

Enforces predictable JSON output

Makes downstream automation reliable

Prevents hallucinated formats from LLM responses

🔐 Requirements

Before running this workflow, make sure you have:

n8n (latest version recommended)

OpenAI API Key

Tavily API Key

SerpAPI API Key

Google Flights enabled

Google Hotels enabled

All credentials should be configured in n8n’s Credentials section.

🚀 Use Cases

✈️ Travel planning assistants

🧳 AI concierge bots

📊 Research agents with live data

🤝 Multi-agent reasoning systems

🧠 LLM-driven automation pipelines

🛠 Customization Tips

Swap out OpenAI models for different cost/performance tradeoffs

Add more tools (maps, events, restaurants, weather)

Tighten Structured Output schemas for stricter validation

Add a final “Response Formatter” node for UI-friendly output

📌 Notes

This workflow is tool-first: the planner decides when and how to search.

Designed for extensibility—new tools can be plugged into the Planner Agent easily.

Works best with clear system prompts and strict output schemas.
