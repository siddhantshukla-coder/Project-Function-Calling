# Project Function Calling

A simple AI Agent built using the Gemini API that demonstrates how Large Language Models (LLMs) can use external tools through function calling.

## Overview

This project implements a basic ReAct-style (Reason + Act) agent from scratch without using frameworks such as LangChain or CrewAI.

The agent can:

* Retrieve real-time weather information for a city.
* Retrieve country information using an external API.
* Decide when a tool is needed.
* Execute tools automatically.
* Feed tool results back to the LLM.
* Generate a final response based on tool outputs.

## How It Works

The agent follows a ReAct-style loop:

1. User sends a message.
2. Gemini analyzes the request.
3. Gemini decides whether a tool is required.
4. If a tool is needed:

   * Gemini returns a function call.
   * Python executes the corresponding tool.
   * Tool output is sent back to Gemini.
5. Gemini produces the final answer.

## Tools

### Weather Tool

Uses the wttr.in API to fetch real-time weather information.

Example:

```text
What is the weather in Tokyo right now?
```

### Country Information Tool

Uses the Rest Countries API to fetch country details.

Example:

```text
Tell me about Japan.
```

## Tech Stack

* Python
* Gemini API
* Pydantic
* Requests
* dotenv

## Project Structure

```text
.
├── main.py
├── .env
├── .gitignore
├── requirements.txt
└── README.md
```

## Example

Input:

```text
What is the weather in Tokyo right now?
```

Tool Call:

```text
get_weather(city="Tokyo")
```

Tool Output:

```text
Tokyo: 🌤️ +20°C
```

Final Response:

```text
The weather in Tokyo right now is 🌤️ +20°C.
```

## What I Learned

* Function Calling with Gemini
* Tool Registration
* ReAct Agent Loops
* Pydantic Schema Validation
* Agent Architecture Fundamentals
* LLM Tool Execution Workflow

## Future Improvements

* Multiple tool calls in a single turn
* Conversation memory
* Streaming responses
* Additional travel-related tools
* Dynamic tool registration
* Multi-agent workflows
