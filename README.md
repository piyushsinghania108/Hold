# Hold

**Enterprise AI Governance Platform** — Centralized oversight of every AI system, autonomous agent, and API across your organization. Built for compliance, security, and risk teams who need complete visibility and enforceable control.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Next.js 16](https://img.shields.io/badge/Next.js-16-black)](https://nextjs.org/)
[![React 19](https://img.shields.io/badge/React-19-61DAFB)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-6-blue)](https://www.typescriptlang.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16+-336791)](https://www.postgresql.org/)
[![Prisma](https://img.shields.io/badge/Prisma-6-2D3748)](https://www.prisma.io/)

---

## Why Hold?

Organizations are deploying AI at unprecedented speed — but governance hasn't kept pace. Hold closes the gap with a **single platform** that discovers, registers, risks, governs, and audits every AI touchpoint across your enterprise.

| Challenge | Hold's Answer |
|-----------|---------------|
| **Shadow AI sprawl** | 6+ discovery sources (Google Workspace, M365, Hexnode, CrowdStrike, DNS/proxy/Netskope, endpoint agent) with automated blocklist feed + IdP enforcement |
| **Regulatory compliance** | EU AI Act classification wizard (Art. 5/6/27/50, Annex I/III, GPAI/FRIA) + 96 seeded controls across NIST AI RMF, ISO 42001, EU AI Act, SOC 2 with 107 crosswalk links |
| **Agent autonomy risk** | Full lifecycle governance: charter → approve → run → review → retire, with proxy-enforced kill switch, MCP tool allowlists, human-review queue, behaviour baselines |
| **Data leakage** | Scheduled gateway probes + inline DLP on proxy traffic (secrets, PII, system prompts, exfiltration) |
| **Cost & usage opacity** | Normalized telemetry across 15+ providers/gateways (Anthropic, OpenAI, Google, Azure, Helicone, OpenRouter, Portkey, LiteLLM, Cursor, GitHub Copilot, ChatGPT Enterprise) with per-system cost attribution and per-person rollups |
| **Developer AI blind spots** | Per-surface dashboards for Claude Platform, Claude Code, Cowork, Cursor, GitHub Copilot with session traces (waterfall of turns, model calls, tool use) |
| **Audit readiness** | Custom reporting suite (PDF/CSV/JSON, scheduled email), policy-as-code enforcement with denials log, evidence artifacts, governance incidents |

---

## Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────┐
│                         HOLD PLATFORM                                │
├─────────────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌────────────┐  │
│  │   Registry  │  │   Agents    │  │ Shadow AI   │  │  Endpoints │  │
│  │  (Systems)  │  │ (Lifecycle) │  │ (Discovery) │  │  (Agent)   │  │
│  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └─────┬──────┘  │
│         │                │                │                │         │
│         └────────────────┼────────────────┼────────────────┘         │
│                          ▼                ▼                          │
│              ┌─────────────────────────────────────┐                 │
│              │         GOVERNANCE ENGINE           │                 │
│              │  Approvals • Risk • Compliance      │                 │
│              │  Policy-as-Code • Evidence • Alerts │                 │
│              └────────────────┬────────────────────┘                 │
│                               │                                      │
│              ┌────────────────┼────────────────────┐                 │
│              ▼                ▼                    ▼                 │
│       ┌─────────────┐ ┌─────────────┐      ┌─────────────┐         │
│       │  AI PROXY   │ │  TELEMETRY  │      │  REPORTING  │         │
│       │ (Enforcement)│ │ (Normalized)│      │ (Executive) │         │
│       └─────────────┘ └─────────────┘      └─────────────┘         │
└─────────────────────────────────────────────────────────────────────┘
```

**Core Stack:** Next.js 16 (App Router) + React 19 + TypeScript 6 + Prisma + PostgreSQL + NextAuth  
**Runtime Enforcement:** Azure Functions–based AI Proxy (Anthropic, OpenAI, Azure OpenAI, Gemini, Bedrock + general HTTPS)  
**Deployment:** Vercel (app) + Azure Functions (proxy) — fully self-hosted, data never leaves your infrastructure

---

## Key Capabilities

### 🎯 AI System & Agent Registry
- Central inventory with ownership, lifecycle status, risk tier, approval state
- EU AI Act classification wizard (stepped: role → Art. 5 → Annex I/III → Art. 6(3) → Art. 50 → GPAI → Art. 27 FRIA)
- Staged approval workflows: Owner → Security → Legal → Compliance with evidence artifacts
- Time-bound exceptions, governance incidents, renewal automation, ownership escalation

### 🤖 Autonomous Agent Governance
- Charter & approval gate with scope enforcement (`accessLevel` + `connectedSystems`)
- **Proxy-enforced kill switch** (`suspendedAt` → immediate 403 on all proxy traffic)
- Human-review triggers: hold tool calls until compliance approves (pending review queue)
- MCP server/tool allowlists per agent (monitor/enforce modes) with observed activity tracking
- Behaviour baselines + 6-dimension posture score (bias, security, privacy, fairness, performance, transparency)

### 👁 Shadow AI Discovery & Enforcement
| Source | Method | Coverage |
|--------|--------|----------|
| Google Workspace | OAuth activity + Admin SDK | 164-tool registry, confidence scoring |
| Microsoft 365 | Graph delegated apps + service principals | Weighted vendor matching |
| Hexnode UEM | Device app inventory | MDM-managed fleet |
| CrowdStrike Falcon | Sensor telemetry | Endpoint process visibility |
| DNS/Proxy/Netskope | Log ingestion (CSV presets + native webhook) | Network-layer visibility |
| Endpoint Agent | macOS/Windows installed apps, browser AI hosts, local model runtimes | **Only source seeing off-VPN, personal-tier, loopback inference** |

**Three enforcement layers:** (1) In-path network proxy block, (2) Blocklist feed for network controls, (3) IdP app-disable

### ⚖️ Risk Center
- Multi-dimensional scoring across 6 dimensions with interactive heat maps
- Agent-aware overlays (agent autonomy adds risk vectors)
- Branching contextual questions, use-case templates, reassessment triggers
- Radar charts, trend lines, residual vs. inherent risk tracking

### 📋 Compliance & Policy-as-Code
- **96 seeded controls** across 4 frameworks with 107 crosswalk links:
  - NIST AI RMF (19) | ISO/IEC 42001 Annex A (38) | EU AI Act (19) | SOC 2 (20)
- Per-system control assessment with evidence artifacts, coverage roll-ups
- **Machine-readable policy rules** enforced at proxy (off / dry-run / enforce)
- Advisory vs. blocking semantics, exception-aware evaluation, ~30s policy cache
- Policy Denials log (filterable, CSV-exportable) with dangerous-prompt content blocks

### 🔒 Sensitive Scan & Inline DLP
- Scheduled gateway probes: system prompt, credential, PII leakage
- Live proxy traffic inspection (both directions): secrets, exfiltration, pasted sensitive data
- Redacted excerpts only — never full prompts/responses stored

### 📊 AI Oversight & Telemetry
**Normalized pipeline:** `UsageBucket` / `CostBucket` / `AssistantDailyStat` (hourly/day aggregates with full attribution)

| Provider/Gateway | Data Ingested |
|------------------|---------------|
| Anthropic Admin API | Usage, costs, API key inventory, members, Compliance API feed, Enterprise Analytics |
| OpenAI Admin API | Org usage, costs, assistant inventory |
| Google Gemini/Vertex | BigQuery billing export |
| AI Gateways | Helicone, OpenRouter, Portkey, LiteLLM (normalized) |
| Developer Tools | Claude Code, Cursor (OTel), GitHub Copilot (usage metrics + seats), ChatGPT Enterprise |
| Proxy Traffic | Real-time usage + cost (dual-write to `APIUsageLog` + `UsageBucket`) |

**Cost attribution:** Per-provider default system + per-API-key override map; workspace-level inheritance logic

### 👥 Usage by Person & Directory Sync
- One row per human, totalled across **every surface** (proxy, gateways, developer tools)
- Identity resolution via Google Workspace / Microsoft Entra ID directory sync
- Alias folding, department rollups, offboarding suspension, `usage_after_deactivation` alerts

### 📈 Custom Reporting Suite
- 9 data sources (including computed Usage by Person rollup)
- 10 starter templates (executive, auditor, regulator, board-ready)
- Detail/grouped output, PDF/CSV/JSON export, scheduled email delivery (Resend)

### 🏢 Vendor Governance
- Vendor profiles: contract posture, lifecycle, renewal queue, security review, data residency, subprocessors
- Approved use-case tracking, composite vendor risk scoring

### 🩺 Proxy Health Live-Ops Board
- Azure Monitor heartbeat + real-time DB counters (usage, flagged, policy denials)
- Per-function metrics: invocations, response time, HTTP status distribution

---

## Quick Start

### Prerequisites
- Node.js 22+
- PostgreSQL 16+ (local or managed: Neon, Supabase, Azure, RDS)
- Google/Microsoft OAuth credentials (production)
- Azure Functions Core Tools (for proxy development)

### Local Development

```bash
# Clone and enter
git clone https://github.com/piyushsinghania108/Hold.git
cd Hold

# Install dependencies
npm install

# Configure environment
cp .env.example .env
# Edit .env with your DATABASE_URL, NEXTAUTH_URL, NEXTAUTH_SECRET, SETTINGS_ENCRYPTION_KEY

# Database setup
npm run db:migrate
npm run db:seed

# Start development server
npm run dev
# → http://localhost:3001
```

### Demo Mode
Set `DEMO_MODE=true` and `NEXT_PUBLIC_DEMO_MODE=true` for a pre-seeded evaluation workspace with sample data (admin@ / demo-password).

### Production Deployment

1. **Vercel (App):** Connect repo → add environment variables → deploy
2. **Azure Functions (Proxy):** `cd ai-proxy && func azure functionapp publish <name>`
3. **Database:** Run `npm run db:deploy` against production PostgreSQL
4. **Cron Jobs:** Configured via `vercel.json` (guarded by `CRON_SECRET`)

See [Install Guide](./docs/install-guide.md) for complete production hardening, TLS, secrets management, and scaling guidance.

---

## Environment Variables (Key)

| Variable | Purpose | Required |
|----------|---------|----------|
| `DATABASE_URL` | PostgreSQL connection string | ✅ |
| `NEXTAUTH_URL` | Public app URL | ✅ |
| `NEXTAUTH_SECRET` | Auth session encryption | ✅ |
| `SETTINGS_ENCRYPTION_KEY` | Encrypts all stored secrets (API keys, service accounts) | ✅ |
| `CRON_SECRET` | Guards all scheduled jobs | ✅ |
| `GOOGLE_CLIENT_ID/SECRET` | Google OAuth sign-in | Production |
| `MICROSOFT_CLIENT_ID/SECRET/TENANT_ID` | Entra ID sign-in | Production |
| `PROXY_SECRET` | Auth for proxy endpoints & webhooks | ✅ |
| `ANTHROPIC_API_KEY` / `OPENAI_API_KEY` | AI provider for risk suggestions, gap analysis | Optional |
| `CLAUDE_CODE_TELEMETRY_SECRET` / `CURSOR_TELEMETRY_SECRET` | OTel ingest auth | Optional |
| `RESEND_API_KEY` / `REPORT_EMAIL_FROM` | Scheduled report delivery | Optional |

Full list with descriptions: [.env.example](./.env.example)

---

## Project Structure

```
Hold/
├── src/
│   ├── app/
│   │   ├── (dashboard)/       # Main product UI (registry, agents, shadow-ai, risk, compliance, oversight, reports, integrations, proxy-health)
│   │   ├── (auth)/            # Login, callbacks
│   │   └── api/               # Route handlers (telemetry, cron, proxy, webhooks, reports, settings)
│   ├── components/            # UI components (Radix + Tailwind)
│   ├── lib/                   # Core logic: integrations, telemetry, policy, risk, reporting, auth
│   └── types/                 # TypeScript declarations
├── prisma/
│   ├── schema.prisma          # 50+ models (governance, telemetry, identity)
│   └── migrations/            # Versioned schema changes
├── ai-proxy/                  # Azure Functions proxy (runtime enforcement)
│   ├── src/
│   │   ├── functions/         # Anthropic, OpenAI, Azure, Gemini, Bedrock, Network proxies
│   │   └── lib/               # Policy enforcement, MCP governance, DLP, tool activity
│   └── host.json
├── ops/
│   ├── endpoint-agent/        # macOS/Windows agent (Go)
│   ├── otel-collector/        # OpenTelemetry collector config
│   └── cursor-hook/           # Cursor OTel hook
├── docs/                      # Installation, user guide, implementation guide, architecture
├── scripts/                   # Seed, validation, drift checks
└── vercel.json                # Cron job definitions
```

---

## Extending Hold

| Extension Point | How |
|-----------------|-----|
| **New Shadow AI Source** | Add ingest route in `src/app/api/discovered-tools/ingest/`, register cron + Settings UI, extend 164-tool registry |
| **New Provider Telemetry** | Implement sync in `src/lib/integrations/`, map to `UsageBucket`/`CostBucket`/`AssistantDailyStat` |
| **Custom Policy Rules** | UI at `/alerts/prompt-rules` (ReDoS-validated) or add `PolicyRule` evaluated in `ai-proxy/src/lib/policy-enforcement.ts` |
| **New Framework Controls** | Seed via `prisma/seed.ts` → `FrameworkControl` + `ControlCrosswalk` |
| **Custom Reports** | Add data source in `src/lib/reporting/sources/`, create `ReportTemplate` |
| **New Developer AI Surface** | Add OTel ingest route in `src/app/api/telemetry/`, define metrics schema, add dashboard page |

---

## Security & Compliance Posture

- **Secrets encryption at rest** — All integration credentials encrypted via `SETTINGS_ENCRYPTION_KEY`
- **Zero prompt/response storage** — Proxy strips prompt/code text at OTel ingest; only metadata, decisions, verdicts persisted
- **PII redaction** — Dangerous-prompt alerts store redacted excerpts only
- **Idempotent ingest** — Content-hash dedupe keys prevent duplicate telemetry
- **ReDoS protection** — Prompt-risk patterns validated against ReDoS shapes + 50ms runtime probe
- **Configurable retention** — Per-data-type prune crons (Settings → General)
- **Full audit trail** — `AuditLog` on all mutations with user, action, before/after, IP
- **RBAC** — Admin / Compliance Officer / Viewer enforced in middleware + API route guards
- **Self-hosted** — No SaaS dependency; all data in your PostgreSQL; proxy in your Azure subscription

---

## License

MIT License — see [LICENSE](LICENSE) for details.

Copyright (c) 2024 Hold

---

## Enterprise Support & Consulting

**Hold** is designed for organizations that need production-grade AI governance without vendor lock-in. 

For enterprise deployments, custom integrations, compliance program alignment, or strategic advisory:

**Piyush Singhania** — Founder, Hold  
📧 piyush@hold.ai  
🌐 hold.ai  
💼 Available for: Platform implementation, EU AI Act readiness, NIST AI RMF operationalization, shadow AI remediation, developer AI oversight programs

---

## Contributing

Issues and PRs welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) (to be added) for guidelines.

---

**Hold** — Governance that holds.  
*Built for the enterprise AI era.*