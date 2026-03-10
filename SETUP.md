# Setup Guide

## Prerequisites

- Claude Code CLI installed
- Node.js 18+ (for MCP servers)
- Brave Search API key (for web research)

## MCP Server Setup

### 1. Brave Search (required for /discover)

Get an API key at https://brave.com/search/api/

Add to your environment:
```bash
export BRAVE_API_KEY="your-key-here"
```

MCP server is configured in `.mcp.json` — no additional setup needed once the env var is set.

### 2. Fetch (included, no setup needed)

The `@anthropic-ai/mcp-server-fetch` server is included and requires no API key.

## Future MCP Servers (when you reach Sprint 4+)

### Vercel (for landing page deployment)
```bash
npm install -g @vercel/mcp-server
export VERCEL_TOKEN="your-vercel-token"
```

### GitHub (for product repos)
```bash
export GITHUB_TOKEN="your-github-token"
```

### Google Analytics (for reading validation results)
Follow GA4 setup guide — requires OAuth credentials.

## Project Initialization

When starting a new project, create the project folder and brief:

```bash
mkdir -p projects/[project-slug]/research projects/[project-slug]/validation
```

Then add `projects/[project-slug]/brief.md` with:
- The initial idea or domain
- Any constraints (budget, timeline, geography)
- What success looks like

Or just run `/discover [domain]` — it will create the structure automatically.

## Environment Variables Summary

| Variable | Required | Used by |
|---|---|---|
| `BRAVE_API_KEY` | Yes (Sprint 2+) | `/discover` skill |
| `VERCEL_TOKEN` | Sprint 4+ | `landing-page-builder` agent |
| `GITHUB_TOKEN` | Sprint 5+ | `product-builder` agent |
| `STRIPE_SECRET_KEY` | Sprint 4+ | preorder goal |
| `GA4_CREDENTIALS` | Sprint 6+ | `analytics-reader` agent |
