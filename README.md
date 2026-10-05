# AI Daily Calendar Assistant

An AI-powered calendar assistant built with n8n that reviews the day's meetings, identifies the two most important events, explains their significance, and delivers a concise HTML briefing by email.

## Overview

The AI Daily Calendar Assistant automates daily calendar review and meeting prioritization.

Instead of requiring users to manually scan their entire calendar, the workflow analyzes all scheduled events for the day and identifies the two meetings that deserve the most attention.

The assistant evaluates each event using information available in the calendar, including:

- Event title
- Description and agenda
- Attendees
- Potential impact
- Urgency
- Decisions, deadlines, milestones, or other relevant context

It then generates a structured briefing explaining why the selected meetings are important and what the user should focus on.

## Key Features

- Retrieves the day's events from Google Calendar
- Reviews all available meetings before selecting the top two
- Prioritizes meetings based on context rather than chronological order
- Considers event titles, descriptions, and attendees
- Identifies meetings with higher potential impact or urgency
- Provides a reason for each selected meeting
- Highlights key preparation points or expected outcomes when available
- Generates a professionally formatted HTML email
- Automatically sends the daily briefing through Gmail
- Runs automatically using an n8n schedule trigger

## Workflow Architecture

```text
Schedule Trigger
       |
       v
   AI Agent
       |
       +------------------+
       |                  |
       v                  v
Google Calendar       OpenAI Chat Model
       |                  |
       +--------+---------+
                |
                v
       Meeting Prioritization
                |
                v
          Top 2 Meetings
                |
                v
        HTML Email Generation
                |
                v
              Gmail
                |
                v
        Daily Email Briefing
