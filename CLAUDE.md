# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Legacy Path Explorer is a single-page chat application for Legacy Investing that helps potential clients understand wealth-building services. It features an AI-powered Wealth Advisor chat interface that uses OpenRouter API to process conversations.

## Architecture

**Frontend**: Single `index.html` file containing all HTML, CSS, and JavaScript. Uses vanilla JS with no build step. The chat panel slides in from the right side and streams AI responses in real-time.

**Backend**: Two server options:
- `server.js` - Local Node.js development server (no dependencies)
- `api/chat.js` - Vercel Edge Function for production deployment

Both servers proxy requests to OpenRouter API to keep the API key server-side.

**AI Context**: The system prompt in `SYSTEM_PROMPT.md` defines the Wealth Advisor persona and knowledge about Legacy Investing's three service paths (A, B, C).

## Commands

```bash
# Local development
node server.js        # Runs on http://localhost:3000

# Production deployment
vercel                # Deploy to Vercel (requires vercel CLI)
```

## Environment Setup

For Vercel deployment, set `OPENROUTER_API_KEY` in Vercel Environment Variables.

For local development, `server.js` has a hardcoded API key (development only).
