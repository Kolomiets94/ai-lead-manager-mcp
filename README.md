# AI Lead Manager MCP

Early-stage **demo**, not production-ready. React + TypeScript dashboard, Express API, JSON-file persistence, and MCP stdio tools. No external AI API or paid services required. Drafts are clearly marked **templates**, not AI-generated text.

## Start

Requires Node.js 20+. Run `npm install` and `npm run dev`, then visit http://localhost:5173. The API runs at http://localhost:3001. The first lead is created from the UI. Run `npm run build` to check TypeScript and compile the frontend.

## MCP

From this repository: `npx tsx server/mcp.ts` (stdio). Configure your MCP client to execute that command with the project working directory. Tools: `list_leads`, `get_lead`, `create_lead`, `update_lead_status`, `draft_reply`.

## API

- GET /api/health
- GET /api/leads
- POST /api/leads with JSON `{name,contact,message}`
- PATCH /api/leads/:id with JSON `{status:'new'|'in_progress'|'closed'}`
- POST /api/leads/:id/draft

## Security and commercial readiness

**Do not deploy publicly yet.** API and MCP stdio currently have **no authentication or tenant separation**. Leads contain personal data stored in local `data/leads.json` (gitignored). Before handling real customers, add authentication, authorization, per-tenant isolation, secure database and backups, retention/deletion, rate limits, and privacy/legal review. No outgoing messages are sent. The draft endpoint is a deterministic demo template, not an LLM integration.

## Roadmap

Authentication and database, tests, real LLM provider behind server-side keys, explicit approval workflow, business-specific pricing/service catalog, deployment and monitoring.
