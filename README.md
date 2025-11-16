# AI Meeting Intelligence Suite – 3-Agent Automation System

If you’re looking for a fully automated meeting assistant, the **AI Meeting Intelligence Suite** is a complete multi-agent system that joins your meetings, understands everything discussed, and automatically takes actions across Notion, Trello, Google Calendar, and Gmail — without any manual effort.

This project uses **three intelligent AI agents** (Joiner, Brain, Action) to create an end-to-end meeting automation pipeline.

## Overview

The **AI Meeting Intelligence Suite** is an advanced multi-agent application that automatically joins online meetings, generates high-quality transcripts, extracts decisions and tasks, and updates project management tools without human intervention.

The system includes:

- **Joiner Agent** → Joins Zoom/Meet, records, diarizes speakers, creates raw transcript  
- **Brain Agent** → Summarizes, extracts decisions, tasks, deadlines  
- **Action Agent** → Updates Notion/Trello, sends emails, adds calendar events  

This tool is ideal for teams, students, and businesses who want to automate meeting notes, follow-ups, and workflows.

---

## Features

- **Automatic Meeting Participation**  
  Joins Zoom or Google Meet using the meeting link.

- **Real-Time Audio-to-Text Conversion**  
  Powered by Whisper or Whisper.cpp.

- **Accurate Speaker Diarization**  
  Maps transcript segments to real participant names.

- **LLM-Based Summary Generation**  
  Uses OpenAI/Groq/Ollama models for summarization.

- **Decision & Action Item Extraction**  
  Detects tasks, deadlines, owners, blockers, and risks.

- **Workflow Automation**  
  Automatically updates:
  - Notion pages  
  - Trello boards  
  - Google Calendar events  
  - Gmail follow-up emails  

- **Memory-Based Follow-Ups**  
  The system remembers previous meeting tasks.

- **User-Friendly Web UI**  
  Optional Gradio/React interface for viewing outputs.

---

## Requirements

- Python 3.x  
- FFmpeg  
- Whisper or Whisper.cpp  
- Any LLM provider (OpenAI, Groq, Ollama, etc.)  
- APIs:  
  - Notion  
  - Trello  
  - Gmail  
  - Google Calendar  
- Gradio (optional frontend)  
- Requests library for API calls  

---

## Pre-Installation

Before running the application, ensure you have an LLM backend available.

If using **Ollama**:

```bash
# Example: Run Llama 3.1 locally
ollama run llama3.1
Installation

Follow these steps to set up and run the application:

Step 1: Clone the Repository
git clone https://github.com/your-username/AI-Meeting-Intelligence-Suite
cd AI-Meeting-Intelligence-Suite

Step 2: Install Dependencies
chmod +x setup.sh
./setup.sh

```
This script will:

Set up a Python virtual environment

Install all required packages

Install FFmpeg if missing

Download Whisper models

Configure APIs

Launch the main application

Step 3: Running the Application Manually
# Activate environment
```bash
source .venv/bin/activate 


# Start the application
python main.py
```
Usage
Step 1 — Join Meeting

The system automatically joins using:

Zoom link

Google Meet link

The Joiner Agent:

Records audio

Separates speakers

Creates transcript file

Step 2 — Brain Agent Processing

It generates:

Clean transcript

Short and detailed summary

List of tasks with deadlines

Decision log

Risks and blockers

Step 3 — Action Agent Execution

Automatically:

Creates tasks in Notion/Trello

Sends summary emails

Adds deadlines to Calendar

Updates existing project pages

You will receive:

Transcript.txt

Summary.md

Action_Items.json

Calendar events

Email follow-ups

# Customization
Changing Whisper Model

Edit config.py:
```bash

WHISPER_MODEL = "medium"

Switching LLM Model
```
Modify:
```bash

LLM_MODEL = "gpt-4"
# or "llama3.1" (Ollama)
# or "mixtral" (Groq)
```
Editing Agent Prompts

You can modify the behavior of each agent in:
```bash

agents/joiner_agent.py
agents/brain_agent.py
agents/action_agent.py
```
Adding More Integrations

Extend:
```bash

integrations/notion.py
integrations/trello.py
integrations/calendar.py
integrations/email.py
```
# Use-Cases

Corporate teams who hold frequent online meetings and struggle with manual note-taking and follow-ups.
Education: professors/teachers who record online lectures and want transcripts, summaries, action items for students.
Project-management: automating task tracking and updates from meeting outputs.
Research groups: capture all decisions, tasks, deadlines directly from discussions.