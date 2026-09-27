# Hosted MCP Servers

**One-click cloud deployments for any Model Context Protocol server.**
Get a live HTTPS URL + bearer token in 30 seconds. Paste it into Claude Desktop, Cursor, Continue, or any MCP-compatible agent. No `npm install`, no Docker, no infrastructure to manage.

> 🚀 **[Deploy a hosted MCP free →](https://mcpplaygroundonline.com/mcp-hosted)**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![MCP Spec](https://img.shields.io/badge/MCP-Specification-blue)](https://modelcontextprotocol.io)
[![Try free](https://img.shields.io/badge/Try-Free%20Tier-success)](https://mcpplaygroundonline.com/mcp-hosted)

---

## Table of contents

- [Why hosted MCP servers exist](#why-hosted-mcp-servers-exist)
- [What you get](#what-you-get)
- [The catalog — 50+ pre-baked servers](#the-catalog--30-pre-baked-servers)
- [Quickstart](#quickstart)
  - [Claude Desktop](#claude-desktop)
  - [Cursor](#cursor)
  - [MCP Agent Studio (in-browser)](#mcp-agent-studio-in-browser)
  - [Your own code](#your-own-code)
- [Architecture](#architecture)
- [Hosted vs self-hosted](#hosted-vs-self-hosted)
- [Pricing](#pricing)
- [Real-world use cases](#real-world-use-cases)
- [FAQ](#faq)
- [Roadmap](#roadmap)
- [Links](#links)

---

## Why hosted MCP servers exist

The [Model Context Protocol](https://modelcontextprotocol.io) gives AI agents a uniform way to call external tools — read files, query databases, post to Slack, etc. The protocol works. The runtime is where everything falls apart:

1. Find an MCP server you want to use
2. `git clone`, `npm install`, debug Node version mismatch
3. Configure auth env vars
4. Add it to your AI client's config
5. Restart the client
6. Hope nothing collides

That's 15+ minutes **per server**. Most developers stop after one. The protocol's promise of "any tool, any agent" never materializes.

**Hosted MCP servers solve the runtime problem.** Pick a server from a curated catalog, paste your API key/token into a form, click Deploy. 30 seconds later you have an HTTPS URL + bearer token that works in any MCP-aware agent.

[Deploy your first hosted MCP server →](https://mcpplaygroundonline.com/mcp-hosted)

---

## What you get

Every hosted MCP deployment includes:

- **Live HTTPS endpoint** — a unique URL per deployment
- **Bearer token** — only your agent can call the server
- **Isolated sandbox** — each deployment runs in its own secure cloud sandbox; no shared filesystem with other users
- **Latest server version** — we pull updates from official MCP server releases
- **Wall-clock runtime budget** — fair-use cap per billing period

Nothing to install. Nothing to update. Works on your laptop, your phone, your CI, your friend's machine — anywhere an MCP client can reach an HTTPS URL.

---

## The catalog — 50+ pre-baked servers

Pick any of these on [mcpplaygroundonline.com/mcp-hosted](https://mcpplaygroundonline.com/mcp-hosted) and deploy in one click.

### Development & DevOps

| Server | What it does | Source |
|---|---|---|
| **GitHub** | Read repos, manage issues and PRs | [official](https://github.com/modelcontextprotocol/servers/tree/main/src/github) |
| **CircleCI** | Inspect pipelines, jobs, failures | [official](https://github.com/circleci/mcp-server-circleci) |
| **Docker Hub** | Search registries, inspect tags | [official](https://hub.docker.com/r/mcp/dockerhub) |
| **Heroku** | Manage apps, dynos, releases | [official](https://github.com/heroku/heroku-mcp-server) |
| **Render** | Manage services and deploys | [official](https://render.com/docs/mcp-server) |
| **Hostinger** | Manage hosting + domains | [official](https://hub.docker.com/r/mcp/hostinger-api) |
| **AWS Documentation** | Search AWS reference docs | [official](https://awslabs.github.io/mcp/) |
| **Azure** | Query Azure services | [official](https://github.com/Azure/azure-mcp) |
| **Cloudflare Docs** | Workers, R2, D1, KV reference | [official](https://github.com/cloudflare/mcp-server-cloudflare) |

### Databases

| Server | What it does | Source |
|---|---|---|
| **Postgres (Read-only)** | Safe SQL queries with auto-rollback | [official](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres) |
| **Postgres (Read/Write)** | Full CRUD via scoped role | [npm](https://www.npmjs.com/package/mcp-postgres-server) |
| **MongoDB** | Queries, aggregation, schema inspection | [official](https://github.com/mongodb-js/mongodb-mcp-server) |
| **Oracle Database** | Read-only Oracle JDBC access | [official](https://hub.docker.com/r/mcp/oracle) |
| **Elasticsearch** | Search + aggregations | [official](https://github.com/elastic/mcp-server-elasticsearch) |

### Business apps

| Server | What it does | Source |
|---|---|---|
| **Slack** | Post messages, read channels | [official](https://github.com/modelcontextprotocol/servers/tree/main/src/slack) |
| **Discord** | Read + post to channels via bot token | [official](https://hub.docker.com/r/mcp/discord) |
| **HubSpot** | Read + write CRM data | [official](https://hub.docker.com/r/mcp/hubspot) |
| **Stripe** | Customers, charges, invoices | [official](https://github.com/stripe/agent-toolkit) |
| **LinkedIn** | Scrape profiles, run job searches | [official](https://hub.docker.com/r/mcp/linkedin) |
| **Atlassian (Jira + Confluence)** | Issues, sprints, pages | [official](https://github.com/sooperset/mcp-atlassian) |
| **Dodo Payments** | Payments, subscriptions, taxes | [official](https://hub.docker.com/r/mcp/dodo-payments) |
| **Statsnet** | Background check any company in the world: registration, executives, courts and finances. Remote: `https://statsnet.co/mcp` | [usenetstate/statsnet-mcp](https://github.com/usenetstate/statsnet-mcp) |


### Web + observability

| Server | What it does | Source |
|---|---|---|
| **Playwright** | Headless Chrome in the cloud | [official](https://github.com/microsoft/playwright-mcp) |
| **Puppeteer** | Headless Chrome alternative | [official](https://github.com/modelcontextprotocol/servers/tree/main/src/puppeteer) |
| **Brave Search** | Web search via Brave API | [official](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search) |
| **Google Maps** | Geocoding, places, directions | [official](https://hub.docker.com/r/mcp/google-maps) |
| **OpenWeather** | Weather + 5-day forecast | [official](https://hub.docker.com/r/mcp/openweather) |
| **Prometheus** | Query metrics with PromQL | [official](https://github.com/pab1it0/prometheus-mcp-server) |
| **Grafana** | Dashboards, datasources, alerts | [official](https://github.com/grafana/mcp-grafana) |

### Zero-config utility servers

| Server | What it does |
|---|---|
| **Hacker News** | Stories, comments, user data |
| **llms.txt** | Discover llms.txt files from websites |
| **Wikipedia** | Search articles |
| **YouTube Transcript** | Pull video transcripts |
| **Sequential Thinking** | Step-by-step reasoning aid |
| **Memory** | Per-session key-value store |

See the full live list at [mcpplaygroundonline.com/mcp-hosted](https://mcpplaygroundonline.com/mcp-hosted).

---

## Quickstart

Pick a hosted server, fill the credentials form, copy the URL + bearer token. Then plug it into your client.

### Claude Desktop

`~/Library/Application Support/Claude/claude_desktop_config.json` (macOS) or `%APPDATA%\Claude\claude_desktop_config.json` (Windows):

```json
{
  "mcpServers": {
    "github": {
      "transport": {
        "type": "http",
        "url": "https://YOUR_HOSTED_MCP_URL",
        "headers": {
          "Authorization": "Bearer YOUR_HOSTED_MCP_TOKEN"
        }
      }
    }
  }
}
```

Restart Claude Desktop. The GitHub tools show up immediately.

### Cursor

`~/.cursor/mcp.json` (or via Cursor's Settings → MCP):

```json
{
  "mcpServers": {
    "github": {
      "url": "https://YOUR_HOSTED_MCP_URL",
      "type": "http",
      "headers": {
        "Authorization": "Bearer YOUR_HOSTED_MCP_TOKEN"
      }
    }
  }
}
```

### MCP Agent Studio (in-browser)

If you don't want to leave the browser, [open MCP Agent Studio](https://mcpplaygroundonline.com/mcp-agent-studio) — pick the hosted deployment from the dropdown, choose a model (Claude, GPT, Gemini, Grok — 40+ supported), and chat.

### Your own code

```typescript
import { createClient } from '@modelcontextprotocol/sdk/client';

const client = createClient({
  transport: 'http',
  endpoint: process.env.MCP_HOSTED_URL,
  auth: {
    type: 'bearer',
    token: process.env.MCP_HOSTED_TOKEN,
  },
});

await client.connect();

const tools = await client.listTools();
const result = await client.callTool('list_issues', {
  owner: 'modelcontextprotocol',
  repo: 'servers',
  state: 'open',
});
```

Works in Node, Bun, Deno, or anywhere with `fetch`.

---

## Architecture

```
┌───────────────────────┐        ┌────────────────────────┐        ┌──────────────────────┐
│  Your MCP client      │        │  HTTPS endpoint        │        │  Managed sandbox     │
│  (Claude / Cursor /   │ ────▶  │  (with bearer auth)    │ ────▶  │  - Isolated FS       │
│   Continue / custom)  │        │                        │        │  - Public internet   │
└───────────────────────┘        └────────────────────────┘        │  - The actual MCP    │
                                                                   │    server process    │
                                                                   └──────────────────────┘
```

Each deployment runs in its own secure, isolated cloud sandbox — separate filesystem per deployment, no shared state with other users, ephemeral by default. The bearer token gates the endpoint; without it, any request is rejected with 401.

When your sandbox is idle, we pause it to save quota; the next request wakes it back up. URL + bearer token stay stable for the lifetime of the deployment — *Cursor and Claude Desktop never need to reconfigure*.

For a deeper dive on the security model, see our [MCP server security guide](https://mcpplaygroundonline.com/blog/why-security-matters-in-mcp-servers).

---

## Hosted vs self-hosted

| Aspect | Self-hosted (npx / Docker) | Hosted on MCP Playground |
|---|---|---|
| Setup time per server | 5–30 min | ~30 sec |
| HTTPS + bearer auth | You configure | Issued automatically |
| Updates & patches | Your job | We pull latest versions |
| Sandboxing | Docker if you bother | Isolated cloud sandbox per deployment |
| Reachable from anywhere | Only if you tunnel | Public HTTPS by default |
| Cost at small scale | Server + DNS + TLS | Free tier available |
| Best for | VPC-internal resources | Everything else |

Self-host when you need an MCP server reaching private VPC resources — that's the case where you genuinely need a server you fully own. For everything else, the time you save with [hosted MCP servers](https://mcpplaygroundonline.com/mcp-hosted) is worth it.

---

## Real-world use cases

The seven we hear about most often:

1. **Prototype agents in 30 seconds** — paste the URL into Cursor instead of `npm install`-ing every MCP locally
2. **Customer-support agent over real Postgres + Stripe + HubSpot data** — three hosted MCPs, one agent, real lookups
3. **Internal "ask the docs" agent over Atlassian Jira + Confluence** — search Confluence in plain English from any chat
4. **Run Playwright in the cloud** — headless Chrome without installing Chrome on your laptop
5. **Multi-MCP agents** — GitHub + Linear + Slack in one conversation, no juggling local processes
6. **Demo MCP to your team** — share a hosted URL, not a `git clone` README
7. **CI/CD agents** — stdio doesn't work in CI; hosted HTTPS does

We unpack each one with prompts and code in [Hosted MCP Server: 7 Real Use Cases Developers Are Building in 2026](https://mcpplaygroundonline.com/blog/hosted-mcp-server-use-cases).

---

## FAQ

### Does this work with Claude Desktop and Cursor?

Yes. Both speak MCP-over-HTTP. Paste the URL + bearer token into the client's config and restart. See the [quickstart](#quickstart) above.

### Is there a free tier?

Yes. **Hobby** is free forever — 1 hosted deployment, 10 minutes of runtime per month. Enough to evaluate; upgrade when you need parallelism.

### How is this different from running an MCP server in my own Docker container?

You don't run anything. No `docker pull`, no port forwarding, no TLS cert renewal. We handle the runtime, you fill in API keys via a form. For VPC-internal databases you still want self-hosting — for SaaS APIs and public-internet resources, hosted is faster.

### Where do the sandboxes run?

In secure, isolated cloud sandboxes managed by MCP Playground. Each deployment is its own ephemeral sandbox with no filesystem sharing between users.

### What MCP transports are supported?

HTTP and SSE today. Stdio servers from the catalog are automatically wrapped to expose HTTP/SSE — you don't have to think about it.

### Can I deploy a custom MCP server, not just the catalog?

Catalog covers 50+ popular servers today. Custom GitHub-repo deployment is on the roadmap; until then, file a request and we'll add servers we don't yet have.

### How do credits relate to hosted MCP runtime?

Two separate things. **Credits** are consumed by agent runs (model + tool calls) inside [MCP Agent Studio](https://mcpplaygroundonline.com/mcp-agent-studio). **Hosted runtime minutes** are wall-clock minutes your hosted sandbox is alive. You can buy more of either independently.

### What happens when I run out of runtime minutes?

Active deployments stop at the cap; you can deploy again next billing period, or [upgrade your plan](https://mcpplaygroundonline.com/settings/credits) for more headroom.

### Can a hosted MCP server reach my private database?

Only if the database is reachable from the public internet — Supabase pooler, Neon, RDS public endpoint, etc. Localhost or VPC-only databases need a tunnel (Tailscale Funnel, ngrok). The Postgres MCPs force SSL by default.

---

## Roadmap

- **Idle pause + auto-wake** *(in progress)* — sandboxes pause after 5 min idle; next request wakes them transparently. URL stays stable for clients.
- **Custom-repo deployment** — drop any GitHub MCP repo URL into the deploy form
- **Team workspaces** — share hosted deployments across org members
- **Persistent storage** — opt-in disk for the few servers that actually need state (filesystem, memory)
- **More servers** — Cloudflare R2, Vercel, Notion, Asana, ClickUp, Sentry. [File a request](https://mcpplaygroundonline.com/support) for what you need.

---

## Links

- 🚀 **[Deploy a hosted MCP](https://mcpplaygroundonline.com/mcp-hosted)** — start here
- 💬 **[MCP Agent Studio](https://mcpplaygroundonline.com/mcp-agent-studio)** — chat with hosted servers across 40+ models
- 📖 **[Use case guide](https://mcpplaygroundonline.com/blog/hosted-mcp-server-use-cases)** — 7 real things developers build with hosted MCPs
- 🔒 **[MCP security guide](https://mcpplaygroundonline.com/blog/why-security-matters-in-mcp-servers)**
- 📚 **[Full MCP server directory](https://mcpplaygroundonline.com/mcp-registry)** — 10,000+ servers
- 🛠️ **[Test any MCP server](https://mcpplaygroundonline.com/mcp-test-server)** — free, no sign-up
- 📡 **[Model Context Protocol spec](https://modelcontextprotocol.io)**
- 🏢 **[MCP Playground](https://mcpplaygroundonline.com)** — the project behind hosted MCPs

---

## About

[MCP Playground](https://mcpplaygroundonline.com) builds developer tooling for the Model Context Protocol — a free browser-based MCP tester, an [Agent Studio](https://mcpplaygroundonline.com/mcp-agent-studio) that compares 40+ AI models side-by-side, a curated [server directory](https://mcpplaygroundonline.com/mcp-servers), and now [hosted MCP runtimes](https://mcpplaygroundonline.com/mcp-hosted). All from one place. No sign-up required for most tools.

If you're shipping anything that touches MCP, give us a follow — and ⭐ this repo if hosted MCPs save you a few hours.

## License

MIT
