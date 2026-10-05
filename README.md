# AI Daily Calendar Assistant

## Overview

The AI Daily Calendar Assistant is an AI-powered meeting prioritization workflow built with n8n.

It reviews the events scheduled for the day, analyzes their importance, identifies the two most important meetings, and delivers a concise executive briefing by email.

The workflow is designed to help users quickly understand which meetings require the most attention and what they should focus on before the day begins.

## Problem Statement

A busy calendar can contain many meetings, but not every meeting has the same level of importance.

Manually reviewing the entire calendar every morning can be time-consuming and makes it easy to overlook high-impact meetings, important stakeholders, deadlines, or decisions.

The goal of this project is to automate this daily review and provide a focused briefing containing only the two most important meetings of the day.

## Solution

The workflow uses an n8n AI Agent connected to Google Calendar and Gmail.

Each morning, the workflow:

1. Reviews the day's calendar events.
2. Analyzes all scheduled events before selecting the top two.
3. Evaluates each event based on multiple importance factors.
4. Ranks the two highest-priority meetings.
5. Generates a concise executive briefing.
6. Sends the briefing to the user's email in a professional HTML format.

## Workflow Architecture

    Schedule Trigger
          |
          v
      AI Agent
       /     \
      v       v
    Google   Gmail
    Calendar
          |
          v
    Daily Meeting Briefing

The AI Agent acts as the central reasoning layer, using Google Calendar to retrieve the day's events and Gmail to deliver the final briefing.

## Workflow Structure

### Schedule Trigger

The workflow is triggered automatically every day at 6:00 AM.

The scheduled trigger starts the daily calendar analysis without requiring manual execution.

### AI Agent

The AI Agent analyzes the calendar events and determines the two most important meetings of the day.

It is connected to:

- OpenAI Chat Model
- Google Calendar
- Gmail

### Google Calendar

Google Calendar provides the events scheduled for the current day.

The AI Agent reviews the available calendar information before selecting the top two meetings.

### Gmail

Gmail is used to deliver the final daily briefing.

The generated briefing is formatted as a professional HTML email.

## Meeting Prioritization Logic

The AI Agent evaluates meetings using the following factors:

### 1. Event Title

The title is analyzed for indicators such as:

- Decisions
- Milestones
- Interviews
- Reviews
- Deadlines
- Client or stakeholder discussions
- High-impact activities

### 2. Description and Agenda

The meeting description and agenda are analyzed for:

- Objectives
- Deliverables
- Decisions
- Deadlines
- Action items

### 3. Attendees

Attendees are considered based on:

- Seniority
- Role
- Number of participants
- Relevance
- Leadership involvement
- Client involvement
- Hiring managers
- Cross-functional stakeholders

### 4. Context and Potential Impact

The AI Agent considers the potential impact of the meeting on:

- Work
- Projects
- Decisions
- Commitments
- Career-related activities

### 5. Urgency

The workflow gives importance to time-sensitive events involving:

- Deadlines
- Decisions
- Launches
- Reviews
- Interviews
- Urgent actions

The workflow does not simply select the first two meetings chronologically.

## End-to-End Request Flow

### 1. Scheduled Trigger

The workflow starts automatically at the configured daily schedule.

### 2. Calendar Review

The AI Agent reviews all events scheduled for the current day.

### 3. Importance Analysis

Each event is evaluated using its title, description, attendees, context, impact, and urgency.

### 4. Meeting Ranking

The AI Agent ranks the events based on their overall importance.

### 5. Top Two Selection

Exactly two meetings are selected as the highest-priority events for the day.

### 6. Briefing Generation

The AI Agent generates a concise briefing for each selected meeting.

### 7. Email Delivery

The final briefing is sent to the configured Gmail recipient.

## Daily Briefing Format

For each selected meeting, the email includes:

- Meeting title
- Date and time
- Attendees
- Why the meeting is important
- What to focus on
- Key outcome, decision, preparation, or action when available

The briefing is presented using a clean, professional HTML email layout with ranked meeting cards.

## Email Design

The generated email is designed to be:

- Professional
- Concise
- Easy to scan
- Visually structured
- Responsive

The two meetings are clearly ranked as:

- #1 — Most Important
- #2 — Second Most Important

The email uses visual separation, spacing, borders, and distinct sections to make the most important information easy to identify.

## AI Agent Instructions

The AI Agent is instructed to:

- Review all events scheduled for today.
- Select exactly two important meetings.
- Avoid selecting meetings only based on chronological order.
- Justify the ranking using available calendar information.
- Use accurate event times and attendees.
- Avoid inventing information.
- Clearly indicate when information is inferred from available data.
- Verify that the selected events belong to the current day.
- Generate a valid HTML email.
- Send the final briefing to the configured recipient.

## Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation and orchestration |
| OpenAI | AI reasoning and meeting prioritization |
| Google Calendar | Calendar event retrieval |
| Gmail | Daily briefing delivery |
| HTML | Professional email formatting |

## Key Capabilities

### Automated Daily Briefing

Automatically generates a focused calendar briefing every morning.

### Intelligent Meeting Prioritization

Ranks meetings based on importance rather than simply using chronological order.

### Multi-Factor Analysis

Considers meeting titles, descriptions, attendees, context, impact, and urgency.

### Executive-Focused Output

Provides a concise summary of the two meetings that require the most attention.

### Automated Email Delivery

Delivers the final briefing directly through Gmail.

### Professional HTML Formatting

Uses a structured and visually clear email format for quick daily scanning.

## Project Structure

    ai-daily-calendar-assistant/
    |
    ├── README.md
    └── workflow.json

## Setup

### Prerequisites

- n8n instance
- OpenAI credentials
- Google Calendar credentials
- Gmail credentials

### Installation

1. Import `workflow.json` into n8n.
2. Configure the required credentials.
3. Connect Google Calendar to the AI Agent.
4. Connect Gmail for email delivery.
5. Verify the AI Agent configuration.
6. Verify the daily schedule.
7. Test the workflow with calendar events.
8. Confirm that the generated briefing is delivered successfully.

## Security

Credentials and authentication information are not included in this repository.

Never commit:

- API keys
- OAuth tokens
- Access tokens
- Passwords
- Private credentials
- Session tokens
- Environment files containing secrets

Use n8n's credential management system for authentication.

## Project Objective

The objective of this project is to demonstrate how an AI Agent can transform a standard calendar into an intelligent daily meeting briefing.

Instead of manually reviewing an entire calendar, the workflow automatically analyzes the day's schedule, identifies the highest-priority meetings, and delivers an actionable executive summary.

## Author

Siddharth Rathi
