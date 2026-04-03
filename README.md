# OpenClaw Personal Assistant

A personal AI agent I designed and run on a cloud VPS to automate recurring life-admin tasks — the kind of low-stakes but time-consuming work that benefits from a system, not manual effort.

## The Problem
Certain tasks follow predictable patterns but require just enough effort to be time consuming: checking NYC parking suspension calendars tied to many religious holidays, remembering to act on upcoming birthdays with enough lead time, parsing event details out of email confirmations. None of it is hard, but together it burns time.

## What I Built
A personal AI assistant that monitors inputs (email, schedules, data files), takes action autonomously, and delivers outputs via Telegram and Google Calendar — without requiring me to remember to check anything.

Core automations:
- Weekly Sunday briefing covering upcoming parking suspensions, birthdays, events, and reminders for the week ahead
- Birthday tracker with tiered advance alerts (day-of, 1 week, 2 weeks prior)
- Email-to-event pipeline that parses forwarded event emails into structured calendar entries with venue, time, and guests
- NYC alternate side parking suspension tracking across the full calendar year, mapped to my specific street sides

## Product Decisions Worth Noting
- Dedicated bot email address restricted to an approved sender list — reduces prompt injection risk and limits the agent's data access to only emails I explicitly forward. Inspired by TripIt's model of forwarding confirmations to a parsing address rather than granting broad inbox access
- VPS hosting via Hostinger rather than a personal device — isolates the agent from broader device access and reduces risk during OpenClaw's beta period

## Integrations
- Google Calendar via API — creates events automatically from parsed emails
- Gmail via App Password — monitors dedicated inbox for forwarded content
- Telegram — primary delivery channel for all alerts and updates
- Syncs to GitHub — agent workspace version-controlled for transparency and recovery

## Built With
OpenClaw (agent framework), Claude (Anthropic), Google Calendar API, Gmail, Telegram, Himalaya CLI
