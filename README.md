# Hold

**Sovereign AI Governance · Runtime Security · Agent Control Infrastructure**

**The control plane for enterprise AI — self-hosted, runtime-enforced, audit-ready.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Next.js 16](https://img.shields.io/badge/Next.js-16-black)](https://nextjs.org/)
[![React 19](https://img.shields.io/badge/React-19-61DAFB)](https://react.dev/)
[![TypeScript 6](https://img.shields.io/badge/TypeScript-6-blue)](https://www.typescriptlang.org/)
[![PostgreSQL 16+](https://img.shields.io/badge/PostgreSQL-16+-336791)](https://www.postgresql.org/)
[![Prisma 6](https://img.shields.io/badge/Prisma-6-2D3748)](https://www.prisma.io/)

> **96** Framework Controls · **107** Crosswalk Links · **6** Risk Dimensions · **6+** Discovery Sources · **164** Tools Tracked · **15+** Telemetry Providers · **20+** Integrations · **50+** Data Models · **3** Enforcement Layers · **0** Prompts Stored

---

## Table of Contents

1. [What Hold Is](#what-hold-is)
2. [Category Positioning](#category-positioning)
3. [Who It's For](#who-its-for)
4. [Why Now](#why-now)
5. [The Problem-Solution Matrix](#the-problem-solution-matrix)
6. [Pillars](#pillars)
7. [Architecture Overview](#architecture-overview)
8. [Module Reference](#module-reference)
9. [Integration Reference](#integration-reference)
10. [Environment Variable Reference](#environment-variable-reference)
11. [Authentication & Identity](#authentication--identity)
12. [Settings & Secret Storage](#settings--secret-storage)
13. [Telemetry Architecture](#telemetry-architecture)
14. [Data Model Reference](#data-model-reference)
15. [API Route Reference](#api-route-reference)
16. [Project Structure](#project-structure)
17. [Local Development](#local-development)
18. [Deployment Options](#deployment-options)
19. [Extending Hold](#extending-hold)
20. [Security & Compliance Posture](#security--compliance-posture)
21. [Objection Handling](#objection-handling)
22. [Competitive Positioning](#competitive-positioning)
23. [Enterprise Support](#enterprise-support)
24. [Contributing](#contributing)

---

## What Hold Is

Hold is the **sovereign control plane for enterprise AI** — it discovers every AI touchpoint, governs every agent from charter to retirement, enforces policy in the request path, and proves compliance across **NIST AI RMF**, **ISO/IEC 42001**, **EU AI Act**, and **SOC 2**.

It is **self-hosted**, **MIT-licensed**, and **vendor-neutral**. No SaaS dependency. No prompt storage. No lock-in.

### One-Liner
> **Hold is open-source AI governance that actually enforces.** It discovers shadow AI across 6+ sources, governs autonomous agents with a proxy-enforced kill switch, and runs policy-as-code in the request path — not in a dashboard.

### 15-Second Pitch
> Hold is the control plane for enterprise AI. It discovers shadow AI, governs agents with a kill switch, enforces policy at the proxy, and maps everything to NIST AI RMF, ISO 42001, EU AI Act, and SOC 2 — self-hosted, MIT-licensed, no vendor lock-in.

### 5-Second Pitch
> **Sovereign AI governance. Runtime-enforced. Audit-ready.**

---

## Category Positioning

Hold sits at the intersection of three established markets and creates a new category: **Sovereign AI Governance**.

| Adjacent Market | What We Borrow | What We Add |
|---|---|---|
| **AI Governance Platforms** (Credo AI, Holistic AI) | Framework mapping, risk assessment, registry | Runtime enforcement, self-hosting, agent control |
| **Cloud Security Posture Management** (Wiz, Orca) | Discovery, posture scoring, continuous monitoring | AI-specific controls, agent lifecycle, policy-as-code |
| **API Gateways / Service Mesh** (Kong, Envoy) | In-path enforcement, DLP, rate limiting | Governance semantics, human-review queues, compliance evidence |

### Category Claim
> **Hold is not a dashboard. It is a control plane.** Where other AI governance tools stop at visibility, Hold enforces policy in the request path — with a proxy-enforced kill switch, inline DLP, and human-review queues that hold tool calls until compliance approves.

### UI Metaphor
> **Mission-control by interface. Control plane by architecture.**
> The dashboard your governance team deserves — real-time, operational, command-center clarity. The enforcement plane your CISO requires — in-path, policy-driven, kill-switch capable.

### Brand Narrative
> Every governance platform needs a story. Some reach for ancient law codes. Hold reaches for something more immediate: **the act of holding itself.**
>
> To hold is to contain. To hold is to retain. To hold is to pause — to stop an agent mid-execution, to freeze a tool call until compliance approves, to enforce a kill switch in the request path.
>
> **Hold is not just a name. It is the product's core verb.**

### SEO Keyword Integration
Enterprise AI governance platform · Open source AI governance · AI compliance software · EU AI Act compliance tool · NIST AI RMF platform · ISO 42001 compliance · Shadow AI discovery · AI agent governance · Runtime AI security · Self-hosted AI governance

---

## Who It's For

### Primary Buyer (Economic)
Compliance Officers · CISOs · VP Risk · General Counsel · CIO

### Primary User (Operational)
**Governance teams** — admin and compliance teams

### Secondary Users
- **Security teams** — runtime enforcement, DLP, shadow AI remediation
- **Risk teams** — risk scoring, heat maps, residual vs. inherent risk
- **Platform engineering** — proxy health, integrations, telemetry pipelines
- **Internal audit** — evidence artifacts, audit trails, reporting

### Audience Label
> **Built for governance teams — compliance officers, admins, and reviewers — with security, risk, and audit stakeholders in the loop.**

### RBAC Roles
| Role | Access |
|---|---|
| **Admin** | Full access — configuration, users, integrations, all modules |
| **Compliance Officer** | Governance, risk, compliance, reports |
| **Viewer** | Read-only dashboards |

---

## Why Now

> **Three forces are converging:**
>
> **1. Regulatory pressure.** The EU AI Act is phasing in. NIST AI RMF is becoming procurement table-stakes. ISO 42001 is the new SOC 2. Organizations need enforceable governance, not PDFs.
>
> **2. Agent autonomy.** AI agents now execute tool calls, access systems, and make decisions. A dashboard that shows you what happened is insufficient — you need a kill switch that stops it from happening.
>
> **3. Shadow AI sprawl.** Employees use personal-tier AI, off-VPN tools, and local models. Network logs miss it. Endpoint agents catch it. Most governance platforms don't have one.
>
> **Hold was built for this moment** — not retrofitted from a GRC tool.

---

## The Problem-Solution Matrix

| Challenge | Hold's Answer |
|-----------|---------------|
| **Shadow AI sprawl** | 6+ discovery sources (Google Workspace, M365, Hexnode, CrowdStrike, DNS/proxy/Netskope, endpoint agent) + automated blocklist feed + IdP enforcement + 164-tool registry + confidence scoring |
| **Regulatory compliance** | EU AI Act classification wizard (Art. 5/6/27/50, Annex I/III, GPAI/FRIA) + 96 seeded controls across NIST AI RMF, ISO 42001, EU AI Act, SOC 2 with 107 crosswalk links |
| **Agent autonomy risk** | Full lifecycle: charter → approve → run → review → retire. Proxy-enforced kill switch, MCP tool allowlists, human-review queue, behaviour baselines, scope enforcement |
| **Data leakage** | Scheduled gateway probes + inline DLP on proxy traffic (secrets, PII, system prompts, exfiltration) + dangerous-prompt detection (5 built-in rules + custom, ReDoS-validated, 50ms probe) |
| **Cost & usage opacity** | Normalized telemetry across 15+ providers/gateways with per-system cost attribution and per-person rollups |
| **Developer AI blind spots** | Per-surface dashboards (Claude Platform, Claude Code, Cowork, Cursor, GitHub Copilot) with session traces |
| **Audit readiness** | Custom reporting suite, policy-as-code enforcement, denials log, evidence artifacts, governance incidents, full audit trail on all mutations |
| **AI vendor lock-in** | Provider-agnostic governance intelligence — Anthropic, OpenAI, or both |
| **Deployment sovereignty** | Self-hosted on your Vercel + Azure + PostgreSQL. Data never leaves your boundary. MIT licensed. |

---

## Pillars : Platform Architecture & Governance Framework

Hold is built on three unique architectural pillars that define *how* it protects your enterprise, and it natively operationalizes the complete 7-pillar AI Governance Framework that defines *what* modern compliance requires.

### Part 1: The 3 Architectural Pillars (How Hold is Built)

#### 1. Sovereign AI Governance
*Your AI estate. Your infrastructure. Your rules.*
- **Self-hosted** — Deploy to your Vercel + Azure + PostgreSQL. Data never leaves your boundary.
- **Regulatory alignment** — EU AI Act wizard (Art. 5/6/27/50, Annex I/III, GPAI/FRIA) + 96 seeded controls across NIST AI RMF, ISO 42001, EU AI Act, SOC 2 with 107 crosswalk links.
- **Policy-as-code** — Machine-readable rules with evidence, exceptions, and audit trails.
- **No vendor lock-in** — Open source, standard stack, portable anywhere.
- **Provider-agnostic AI** — Use Anthropic, OpenAI, or both for risk classification, gap analysis, and agent reviews. Your governance brain is not captive to one AI vendor.

#### 2. Runtime Security
*Policy enforced in the request path — not in a dashboard.*
- **Transparent AI Proxy** — Anthropic, OpenAI, Azure OpenAI, Gemini, Bedrock + general HTTPS with off/dry-run/enforce modes.
- **Proxy-enforced kill switch** — Immediate 403 on suspended agents.
- **Inline DLP** — Secrets, PII, system prompts, exfiltration detection on live traffic.
- **Dangerous-prompt detection** — 5 built-in rules + custom, ReDoS-validated, 50ms probe.
- **Shadow AI enforcement** — Three layers: in-path proxy, blocklist feed, IdP app-disable.
- **Advisory vs. blocking semantics** — Roll out enforcement gradually with dry-run mode.

#### 3. Agent Control Infrastructure
*Autonomous agents, governed from charter to retirement.*
- **Full lifecycle** — Charter → approve → run → review → retire.
- **MCP governance** — Per-agent server/tool allowlists (monitor + enforce modes).
- **Human-review queue** — Holds tool calls until compliance approves.
- **Behaviour baselines** — 6-dimension posture scoring (bias, security, privacy, fairness, performance, transparency).
- **Scope enforcement** — `accessLevel` + `connectedSystems` enforced per `scopeEnforcement`.
- **Agent-aware risk overlays** — Additional risk vectors for autonomy and branching contextual questions.

---

### Part 2: The 7-Pillar AI Governance Framework (What Hold Covers)

While Hold's architecture is built on the three pillars above, the platform natively operationalizes the complete 7-pillar industry framework required by enterprise compliance teams.

#### 🏛️ 01. Policy
*Set the rules for how AI is built, bought, and used at work.*
- **Capabilities:** Acceptable use policy, approved AI tools, data usage rules, shadow AI controls, vendor AI policy, prompt/output rules, IP/copyright rules, disclosure, and exception processes.
- **Hold's Approach:** Translated into enforceable policy-as-code at the proxy with off/dry-run/enforce modes.

#### ⚠️ 02. Risk Assessment
*Identify, score, and treat AI risks before and after deployment.*
- **Capabilities:** Risk tiering, impact assessment, threat modeling, bias/privacy/security/vendor risk, residual risk, and a centralized risk register.
- **Hold's Approach:** 6-dimension scoring in the Risk Center, including agent-aware risk overlays and continuous reassessment triggers.

#### 🗂️ 03. Model Inventory
*Track every model, agent, and AI system running in the enterprise.*
- **Capabilities:** Model registry, model cards, ownership mapping, version tracking, data lineage, agent catalog, third-party models, and retirement tracking.
- **Hold's Approach:** The Registry module acts as the single source of truth, paired with autonomous Agent lifecycle management and a 164-tool Shadow AI registry.

#### ⚖️ 04. Compliance
*Map AI systems to laws, standards, and internal obligations.*
- **Capabilities:** EU AI Act, NIST AI RMF, ISO 42001, GDPR, DPDP Act, sector regulations, data residency, and regulatory reporting.
- **Hold's Approach:** 96 seeded controls with 107 crosswalks, per-system assessment, and automated evidence collection.

#### 🤝 05. Ethics & Responsible AI
*Keep AI decisions fair, transparent, and aligned with human values.*
- **Capabilities:** Fairness testing, bias mitigation, explainability, transparency notices, human oversight, and ethics review boards.
- **Hold's Approach:** Dangerous-prompt detection, human-review queues that hold agent tool calls, and strict PII redaction.

#### 👤 06. Accountability
*Assign clear ownership for every AI decision and outcome.*
- **Capabilities:** AI council, executive sponsors, model owners, RACI mapping, approval gates, incident ownership, and decision logs.
- **Hold's Approach:** Staged approval workflows (Owner → Security → Legal → Compliance), strict RBAC (Admin/Officer/Viewer), and full immutable audit trails.

#### 🔍 07. Audit & Assurance
*Prove AI systems work as intended with evidence and independent review.*
- **Capabilities:** Audit trails, model audits, bias audits, access reviews, prompt logs, control testing, and evidence collection.
- **Hold's Approach:** Built-in audit readiness with custom reporting, denials log exports, and a fully immutable `AuditLog` database.

---

- **Full lifecycle** — Charter → approve → run → review → retire.
- **MCP governance** — Per-agent server/tool allowlists (monitor + enforce modes).
- **Human-review queue** — Holds tool calls until compliance approves.
- **Behaviour baselines** — 6-dimension posture scoring (bias, security, privacy, fairness, performance, transparency).
- **Scope enforcement** — `accessLevel` + `connectedSystems` enforced per `scopeEnforcement`.
- **Agent-aware risk overlays** — Additional risk vectors for autonomy and branching contextual questions.

---

## Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────┐
│                         HOLD PLATFORM                                │
├─────────────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌────────────┐  │
│  │   Registry  │  │   Agents    │  │ Shadow AI   │  │ Endpoints  │  │
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
│       │(Enforcement)│ │ (Normalized)│      │ (Executive) │         │
│       └─────────────┘ └─────────────┘      └─────────────┘         │
└─────────────────────────────────────────────────────────────────────┘
```

### Core Stack
- **Next.js 16 (App Router)** + **React 19** + **TypeScript 6** + **Prisma** + **PostgreSQL 16+** + **NextAuth**

### Runtime Enforcement
- **Azure Functions–based AI Proxy** — Anthropic, OpenAI, Azure OpenAI, Gemini, Bedrock + general HTTPS

### Deployment
- **App:** Vercel (or any Next.js host)
- **Proxy:** Azure Functions (or containerized on any Kubernetes)
- **Database:** Managed PostgreSQL (Neon, Supabase, Azure, RDS) or self-managed
- **Cron:** Vercel Cron (guarded by `CRON_SECRET`)

### Architecture Principles
- **Control plane / enforcement plane separation** — Dashboard and proxy operate independently for latency-sensitive governance.
- **Zero prompt/response storage** — Proxy strips prompt/code text at OTel ingest; only metadata, decisions, verdicts persisted.
- **Idempotent ingest** — Content-hash dedupe keys prevent duplicate telemetry.
- **Provider-agnostic** — Governance intelligence and enforcement both work across all major AI vendors.

---

## Module Reference

### 1. Registry
**The single source of truth for every AI system in your estate.**

| Capability | Detail |
|---|---|
| **Central inventory** | Ownership, lifecycle status, risk tier, approval state |
| **EU AI Act wizard** | Art. 5/6/27/50, Annex I/III, GPAI/FRIA classification |
| **Staged approvals** | Owner → Security → Legal → Compliance |
| **Evidence artifacts** | Attached to each system for audit readiness |
| **Exceptions** | Time-bound, tracked, auditable |
| **Incidents** | Governance incidents linked to systems |
| **Renewal automation** | Scheduled review triggers |
| **Escalations** | Route to stakeholders on SLA breach |

**Data Model:** `AiSystem`, `Approval`, `Evidence`, `Exception`, `Incident`

---

### 2. Agents
**Autonomous agents, governed from charter to retirement.**

| Capability | Detail |
|---|---|
| **Full lifecycle** | Charter → approve → run → review → retire |
| **Charter gate** | Agent cannot run until charter approved |
| **Proxy-enforced kill switch** | `suspendedAt` triggers immediate 403 on all proxy traffic |
| **MCP governance** | Per-agent server/tool allowlists (monitor + enforce modes) |
| **Human-review queue** | Holds tool calls until compliance approves |
| **Behaviour baselines** | 6-dimension posture scoring (bias, security, privacy, fairness, performance, transparency) |
| **Scope enforcement** | `accessLevel` + `connectedSystems` enforced per `scopeEnforcement` |
| **Agent-aware risk overlays** | Additional risk vectors for autonomy and branching contextual questions |

**Data Model:** `Agent`, `AgentCharter`, `McpServer`, `McpTool`, `AgentBaseline`, `HumanReviewQueue`

---

### 3. Shadow AI
**Discover the AI you didn't know you had — then enforce against it.**

| Discovery Source | What It Sees |
|---|---|
| **Google Workspace** | OAuth scan of employee AI app usage |
| **Microsoft 365** | Delegated-app scan via Graph |
| **Hexnode UEM** | Device app inventory |
| **CrowdStrike Falcon** | Endpoint process visibility |
| **DNS/proxy/Netskope** | Network-layer AI traffic |
| **Endpoint agent** | Installed apps, browser AI hosts, local model runtimes, loopback inference — **only source seeing off-VPN, personal-tier, local inference** |

| Enforcement Layer | Mechanism |
|---|---|
| **In-path proxy** | Block requests at the AI Proxy |
| **Blocklist feed** | Export to network controls (Netskope, DNS) |
| **IdP app-disable** | Disable OAuth apps in Google/Microsoft |

**Registry:** 164-tool registry with confidence scoring.

**Data Model:** `DiscoveredTool`, `ShadowAiSource`, `BlocklistEntry`, `ConfidenceScore`

---

### 4. Endpoints
**The only source that sees off-VPN, personal-tier, and loopback inference.**

| Capability | Detail |
|---|---|
| **Managed macOS/Windows machines** | Go-based endpoint agent |
| **Installed apps** | Inventory of AI applications |
| **Browser AI hosts** | Detect ChatGPT, Claude, Gemini, Perplexity, etc. |
| **Local model runtimes** | Ollama, LM Studio, llama.cpp, etc. |
| **Loopback inference** | Catches localhost AI calls network logs miss |
| **Enrollment** | `ENDPOINT_AGENT_ENROLLMENT_SECRET` (low-value org secret) |

**Data Model:** `Endpoint`, `EndpointApp`, `EndpointBrowserHost`, `EndpointLocalRuntime`

---

### 5. Risk Center
**Multi-dimensional risk scoring that understands agents.**

| Capability | Detail |
|---|---|
| **6-dimension scoring** | Bias, security, privacy, fairness, performance, transparency |
| **Heat maps** | Interactive, filterable by system/agent/team |
| **Radar charts** | Per-system and per-agent |
| **Trend lines** | Historical posture over time |
| **Branching questions** | Context-aware assessment flow |
| **Use-case templates** | Pre-populated assessment flows |
| **Residual vs. inherent risk** | Track both independently |
| **Agent-aware overlays** | Additional vectors for autonomy |
| **Reassessment triggers** | Event-driven (e.g., model change, incident) |

**Data Model:** `RiskAssessment`, `RiskDimension`, `RiskVector`, `RiskTemplate`

---

### 6. Compliance
**Policy-as-code, enforced at the proxy — not filed in a binder.**

| Capability | Detail |
|---|---|
| **Framework controls** | 96 seeded controls: NIST AI RMF (19), ISO/IEC 42001 Annex A (38), EU AI Act (19), SOC 2 (20) |
| **Crosswalks** | 107 links between frameworks |
| **Per-system assessment** | Map each system to applicable controls |
| **Policy-as-code** | Machine-readable rules evaluated at proxy |
| **Enforcement modes** | Off / dry-run / enforce |
| **Advisory vs. blocking** | Gradual rollout semantics |
| **Exception-aware evaluation** | Exceptions respected during policy evaluation |
| **~30-second policy cache** | Performance-optimized |
| **Denials log** | Exportable audit of blocked requests |
| **Evidence artifacts** | Attached to controls |
| **Governance incidents** | Linked to compliance posture |

**Data Model:** `FrameworkControl`, `ControlCrosswalk`, `PolicyRule`, `PolicyEvaluation`, `DenialLog`, `ComplianceEvidence`

---

### 7. Oversight
**Every provider, every gateway, every surface — normalized into one telemetry plane.**

| Capability | Detail |
|---|---|
| **15+ providers/gateways** | Anthropic, OpenAI, Google Gemini/Vertex, Azure, Helicone, OpenRouter, Portkey, LiteLLM, Claude Code, Cursor, GitHub Copilot, ChatGPT Enterprise, and more |
| **Per-system cost attribution** | Default per-provider, override per-API-key, workspace inheritance |
| **Per-person rollups** | Usage and cost per employee |
| **Per-surface dashboards** | Claude Platform, Claude Code, Cowork, Cursor, GitHub Copilot |
| **Session traces** | OTel-based developer AI visibility |
| **Anomaly detection** | Usage and cost outliers |
| **Vendor governance** | Provider-level posture |

**Data Model:** `UsageBucket`, `CostBucket`, `AssistantDailyStat`, `ProviderSyncRun`, `ProviderSyncWatermark`, `ProviderRawSnapshot`, `ApiUsageLog`

---

### 8. Reports
**Board-ready, auditor-ready, regulator-ready — in one click.**

| Capability | Detail |
|---|---|
| **9 data sources** | Systems, agents, risk, compliance, usage, cost, incidents, exceptions, audit |
| **10 starter templates** | Executive, auditor, regulator, board-ready, and more |
| **Export formats** | PDF, CSV, JSON |
| **Scheduled delivery** | Email via Resend |
| **Custom builder** | Compose reports from any data source |

**Data Model:** `ReportTemplate`, `ReportSchedule`, `GeneratedReport`

---

### 9. Integrations
**20+ integrations, configurable at runtime — no redeploy required.**

See [Integration Reference](#integration-reference) for complete detail.

**Data Model:** `Integration`, `IntegrationCredential`, `IntegrationSync`

---

### 10. Proxy Health
**Live-ops board for the enforcement plane.**

| Capability | Detail |
|---|---|
| **Azure Monitor heartbeat** | Proxy liveness |
| **Real-time DB counters** | Usage, flagged, denials |
| **Operational visibility** | For platform engineering |

**Data Model:** `ProxyHealthEvent`, `ProxyCounter`

---

## Integration Reference

| Integration | Purpose | Credentials | Configure In |
|---|---|---|---|
| **OpenAI Admin API** | Org usage, costs, assistant discovery | Admin API key | Settings → Provider Admin APIs |
| **Anthropic Admin API** | Usage, API key inventory, members, Compliance feed, Analytics | Admin key + Compliance key + Analytics key | Settings → Provider Admin APIs |
| **Google Gemini / Vertex** | Cost oversight via BigQuery billing export | Service account JSON + project ID + dataset + table + location | Settings → Provider Admin APIs |
| **Google Workspace** | Shadow AI discovery + optional directory sync | Service account JSON + admin email + domain-wide delegation | Settings → Shadow AI / Users & Identity |
| **Microsoft 365** | Shadow AI discovery via Graph | Tenant ID + client ID + secret (Graph application permissions) | Settings → Shadow AI |
| **Hexnode UEM** | Device app inventory | API key + subdomain | Settings → Shadow AI |
| **CrowdStrike Falcon** | Endpoint process visibility | Client ID + client secret + cloud region | Settings → Shadow AI |
| **Helicone** | AI gateway telemetry | API key + base URL | Settings → Integrations |
| **OpenRouter** | AI gateway telemetry | Provisioning key | Settings → Integrations |
| **Portkey** | AI gateway telemetry | API key + base URL + workspace slug | Settings → Integrations |
| **LiteLLM** | Self-hosted gateway telemetry | API key + base URL | Settings → Integrations |
| **Claude Code / Cowork** | OTel-based session traces | `CLAUDE_CODE_TELEMETRY_SECRET` | Settings + telemetry secrets |
| **Cursor** | OTel-based session traces | `CURSOR_TELEMETRY_SECRET` | Settings + telemetry secrets |
| **Endpoint Agent** | macOS/Windows installed apps & local models | `ENDPOINT_AGENT_ENROLLMENT_SECRET` | Settings → Endpoint Agent |
| **GitHub Copilot** | Usage metrics + seats | Admin token | Settings → Provider Admin APIs |
| **ChatGPT Enterprise** | Compliance feed, user activity, Codex | Compliance API key | Settings → Provider Admin APIs |
| **Resend** | Scheduled report email delivery | `RESEND_API_KEY` + `REPORT_EMAIL_FROM` | Environment / Settings |
| **Datadog** | Alert/event forwarding | `DATADOG_API_KEY` + `DATADOG_APP_KEY` + `DATADOG_SITE` | Environment / Settings |
| **Azure Monitor** | Proxy Health board metrics | Azure credentials | Settings → Integrations |
| **Netskope** | Native log-shipper ingestion | Netskope credentials | Settings → Shadow AI |
| **Google OAuth** | Employee sign-in | OAuth client ID + secret | Settings → Users & Identity |
| **Microsoft Entra ID** | Employee sign-in | App registration | Settings → Users & Identity |

### Google Setup Split
| Area | Purpose | Credentials |
|---|---|---|
| **Settings → Users & Identity** | Employee sign-in via OAuth | OAuth client ID + secret |
| **Settings → Shadow AI** | Google Workspace discovery | Service account JSON + admin email + domain-wide delegation |

### Microsoft Setup Split
| Area | Purpose | Credentials |
|---|---|---|
| **Settings → Users & Identity** | Entra ID sign-in | Standard app registration |
| **Settings → Shadow AI** | M365 delegated-app discovery | Tenant ID + client ID + secret (Graph application permissions) |

---

## Environment Variable Reference

### Core (Required)

| Variable | Description | Example |
|---|---|---|
| `DATABASE_URL` | PostgreSQL connection string | `postgresql://user:pass@host:5432/hold` |
| `NEXTAUTH_URL` | Public app URL | `http://localhost:3001` |
| `NEXTAUTH_SECRET` | Auth session encryption (32+ chars) | `openssl rand -hex 32` |
| `SETTINGS_ENCRYPTION_KEY` | Encrypts ALL stored secrets — **never rotate after data saved** | `openssl rand -hex 32` |
| `CRON_SECRET` | Guards all `/api/cron/**` routes | `openssl rand -hex 32` |
| `PROXY_SECRET` | Auth for proxy endpoints & webhooks (must match Azure) | `openssl rand -hex 32` |
| `PROMPT_HASH_SALT` | Salt for prompt hashing (must match Azure) | `openssl rand -hex 32` |

### Authentication

| Variable | Description | Required |
|---|---|---|
| `GOOGLE_CLIENT_ID` / `GOOGLE_CLIENT_SECRET` | Google OAuth (production sign-in) | Production |
| `MICROSOFT_CLIENT_ID` / `MICROSOFT_CLIENT_SECRET` / `MICROSOFT_TENANT_ID` | Entra ID OAuth | Production |
| `ENABLE_DEV_LOGIN` | Credentials-based dev login | Dev only |
| `ENABLE_LOCAL_AUTH` | Password-backed local accounts | Dev only |

### Demo Mode

| Variable | Description |
|---|---|
| `DEMO_MODE` | Server-side demo mode |
| `NEXT_PUBLIC_DEMO_MODE` | Client-side demo mode |

**Demo login:** `admin@example.com` / `demo-password`

### Shadow AI Discovery (Fallbacks — UI settings take precedence)

| Variable | Description |
|---|---|
| `GOOGLE_SCAN_ENABLED` / `GOOGLE_SCAN_LOOKBACK_DAYS` / `GOOGLE_SCAN_INTERVAL_HOURS` | Google Workspace OAuth scan |
| `MICROSOFT_SHADOW_AI_TENANT_ID` / `MICROSOFT_SHADOW_AI_CLIENT_ID` / `MICROSOFT_SHADOW_AI_CLIENT_SECRET` / `MICROSOFT_SHADOW_AI_SCAN_ENABLED` / `MICROSOFT_SHADOW_AI_SCAN_INTERVAL_HOURS` | M365 delegated-app scan |
| `HEXNODE_API_KEY` / `HEXNODE_SUBDOMAIN` / `HEXNODE_SCAN_ENABLED` / `HEXNODE_SCAN_INTERVAL_HOURS` | Hexnode UEM device scan |
| `CROWDSTRIKE_CLIENT_ID` / `CROWDSTRIKE_CLIENT_SECRET` / `CROWDSTRIKE_CLOUD` | CrowdStrike Falcon scan |

### Provider & Gateway Telemetry (Optional — UI settings take precedence)

| Variable | Description |
|---|---|
| `OPENAI_API_KEY` / `ANTHROPIC_API_KEY` | AI provider for risk suggestions, gap analysis |
| `ANTHROPIC_COMPLIANCE_KEY` | Compliance Access Key (read:compliance_activities) |
| `ANTHROPIC_ANALYTICS_KEY` | Enterprise Analytics key (read:analytics) |
| `HELICONE_API_KEY` / `HELICONE_API_BASE_URL` | Helicone gateway |
| `OPENROUTER_PROVISIONING_KEY` | OpenRouter gateway |
| `PORTKEY_API_KEY` / `PORTKEY_API_BASE_URL` / `PORTKEY_WORKSPACE_SLUG` | Portkey gateway |
| `LITELLM_API_KEY` / `LITELLM_API_BASE_URL` | LiteLLM gateway (self-hosted) |
| `GEMINI_BILLING_SERVICE_ACCOUNT_KEY` / `GEMINI_BILLING_PROJECT_ID` / `GEMINI_BILLING_DATASET` / `GEMINI_BILLING_TABLE` / `GEMINI_BILLING_LOCATION` | Gemini/Vertex BigQuery billing export |

### Telemetry Ingest & Agents

| Variable | Description |
|---|---|
| `CLAUDE_CODE_TELEMETRY_SECRET` / `CLAUDE_CODE_TELEMETRY_RETENTION_DAYS` | Claude Code / Cowork OTel ingest |
| `CURSOR_TELEMETRY_SECRET` | Cursor OTel ingest |
| `ENDPOINT_AGENT_ENROLLMENT_SECRET` | Low-value org secret for agent enrollment |
| `NETWORK_PROXY_MODE` | General HTTPS proxy: `off` \| `monitor` \| `enforce` |

### Reporting & Alerts

| Variable | Description |
|---|---|
| `RESEND_API_KEY` / `REPORT_EMAIL_FROM` | Scheduled report email delivery |
| `DATADOG_ENABLED` / `DATADOG_API_KEY` / `DATADOG_APP_KEY` / `DATADOG_SITE` | Alert/event forwarding |
| `ORG_TIMEZONE` | Organization timezone for cron scheduling — `UTC` |

---

## Authentication & Identity

### Production
- **Google OAuth** — Configure in Google Cloud Console → Authorized redirect: `https://your-domain.com/api/auth/callback/google`
- **Microsoft Entra ID** — Configure in Azure Portal → Redirect: `https://your-domain.com/api/auth/callback/azure-ad`

### Local Development
- `ENABLE_DEV_LOGIN=true` — Credentials-based login (first user becomes ADMIN)
- `ENABLE_LOCAL_AUTH=true` — Password-backed local accounts

### RBAC Roles
- **Admin** — Full access
- **Compliance Officer** — Governance, risk, compliance, reports
- **Viewer** — Read-only dashboards

RBAC enforced in middleware + API route guards.

---

## Settings & Secret Storage

All sensitive values are **encrypted at rest** using `SETTINGS_ENCRYPTION_KEY` before storage in the `AppSetting` table:

- Provider API keys & admin keys
- Google Workspace / Gemini service account JSON
- Microsoft 365 Shadow AI client secrets
- Proxy secrets
- Any credential stored via Settings UI

> **⚠️ Critical:** Never rotate `SETTINGS_ENCRYPTION_KEY` after data is saved — you will lose access to all encrypted values. Back it up with database backups.

---

## Telemetry Architecture

### Normalized Pipeline (Phase 2)

| Table | Purpose | Granularity |
|---|---|---|
| `UsageBucket` | Normalized usage aggregates | Hourly/Day |
| `CostBucket` | Normalized cost aggregates (same attribution as UsageBucket) | Hourly/Day |
| `AssistantDailyStat` | Per-person, per-day coding-assistant metrics | Day |
| `ProviderSyncRun` | Tracks each sync attempt | Per run |
| `ProviderSyncWatermark` | Incremental sync windows | Per provider |
| `ProviderRawSnapshot` | Raw provider payloads for audit/debug | Per fetch |
| `ApiUsageLog` | Legacy per-request log (dual-written from proxy) | Per request |

### Proxy Traffic Dual-Write
Every proxied request creates `ApiUsageLog` + idempotent hourly `UsageBucket`/`CostBucket` upsert (linked to synthetic `ProviderSyncRun` with `syncType="proxy_live"`).

### Cost Attribution
- **Per-provider default system** — Each provider maps to a default system
- **Per-API-key override map** — Override attribution per key
- **Workspace-level inheritance** — When all keys map to same system

### Ingestion Guarantees
- **Idempotent** — Content-hash dedupe keys prevent duplicates
- **Incremental** — Watermarks track sync windows
- **Auditable** — Raw snapshots retained for debug
- **Privacy-preserving** — Zero prompt/response storage; PII redaction in alerts

---

## Data Model Reference

**50+ Prisma models** across governance, telemetry, identity. Grouped by domain:

### Governance
`AiSystem`, `Approval`, `Evidence`, `Exception`, `Incident`, `Agent`, `AgentCharter`, `AgentBaseline`, `AgentReview`, `McpServer`, `McpTool`, `HumanReviewQueue`, `ScopeEnforcement`

### Discovery
`DiscoveredTool`, `ShadowAiSource`, `BlocklistEntry`, `ConfidenceScore`, `Endpoint`, `EndpointApp`, `EndpointBrowserHost`, `EndpointLocalRuntime`

### Risk
`RiskAssessment`, `RiskDimension`, `RiskVector`, `RiskTemplate`, `RiskTrend`

### Compliance
`FrameworkControl`, `ControlCrosswalk`, `PolicyRule`, `PolicyEvaluation`, `DenialLog`, `ComplianceEvidence`, `ComplianceIncident`

### Telemetry
`UsageBucket`, `CostBucket`, `AssistantDailyStat`, `ProviderSyncRun`, `ProviderSyncWatermark`, `ProviderRawSnapshot`, `ApiUsageLog`

### Reporting
`ReportTemplate`, `ReportSchedule`, `GeneratedReport`

### Integrations
`Integration`, `IntegrationCredential`, `IntegrationSync`

### Identity & Audit
`User`, `Account`, `Session`, `AuditLog`, `AppSetting`

### Operations
`ProxyHealthEvent`, `ProxyCounter`, `CronRun`

---

## API Route Reference

### Dashboard Pages (`src/app/(dashboard)/`)
`registry/`, `agents/`, `shadow-ai/`, `endpoints/`, `risk-center/`, `compliance/`, `oversight/`, `reports/`, `integrations/`, `proxy-health/`, `settings/`

### Auth Pages (`src/app/(auth)/`)
`login/`, `callbacks/`

### API Route Handlers (`src/app/api/`)
| Route | Purpose |
|---|---|
| `telemetry/` | OTel ingest (Claude Code, Cursor) |
| `cron/` | Scheduled jobs (guarded by `CRON_SECRET`) |
| `proxy/` | AI provider proxies + network proxy |
| `discovered-tools/` | Shadow AI ingestion + blocklist |
| `reports/` | Generation, export, schedules |
| `settings/` | Config CRUD + connection tests |
| `webhooks/` | External integrations (shared-secret secured) |

---

## Project Structure

```
Hold/
├── src/
│   ├── app/
│   │   ├── (dashboard)/          # Main product UI
│   │   │   ├── registry/         # AI System Registry
│   │   │   ├── agents/           # AI Agent Registry + MCP governance
│   │   │   ├── shadow-ai/        # Discovery + triage + enforcement
│   │   │   ├── endpoints/        # Endpoint agent fleet
│   │   │   ├── risk-center/      # Risk assessments + heat maps
│   │   │   ├── compliance/       # Policies, frameworks, denials, evidence
│   │   │   ├── oversight/        # Usage, costs, per-surface dashboards
│   │   │   ├── reports/          # Custom report builder
│   │   │   ├── integrations/     # External connections
│   │   │   ├── proxy-health/     # Live-ops board
│   │   │   └── settings/         # All configuration surfaces
│   │   ├── (auth)/               # Login & callbacks
│   │   └── api/                  # Route handlers
│   │       ├── telemetry/        # OTel ingest (Claude Code, Cursor)
│   │       ├── cron/             # Scheduled jobs (guarded by CRON_SECRET)
│   │       ├── proxy/            # AI provider proxies + network proxy
│   │       ├── discovered-tools/ # Shadow AI ingestion + blocklist
│   │       ├── reports/          # Generation, export, schedules
│   │       └── settings/         # Config CRUD + connection tests
│   ├── components/               # UI (Radix + Tailwind + CVA)
│   │   ├── ui/                   # Primitives
│   │   ├── layout/               # Sidebar, top bar, page header
│   │   ├── dashboard/            # Stat cards, heat maps, charts
│   │   ├── forms/                # Entity forms
│   │   └── compliance/           # Framework controls, coverage
│   ├── lib/                      # Core logic
│   │   ├── integrations/         # Provider/gateway clients
│   │   ├── telemetry/            # Normalization, attribution
│   │   ├── policy/               # Policy-as-code runtime
│   │   ├── risk/                 # Scoring, templates
│   │   ├── reporting/            # Sources, templates, export
│   │   ├── auth/                 # NextAuth config, guards
│   │   ├── settings/             # Encrypted settings store
│   │   ├── audit/                # Audit logging
│   │   ├── validations/          # Zod schemas
│   │   └── utils/                # Helpers
│   └── types/                    # TypeScript declarations
├── prisma/
│   ├── schema.prisma             # 50+ models (governance, telemetry, identity)
│   └── migrations/               # Versioned schema changes
├── ai-proxy/                     # Azure Functions proxy (runtime enforcement)
│   ├── src/functions/            # Provider proxies + network proxy
│   └── src/lib/                  # Policy enforcement, MCP governance, DLP
├── ops/
│   ├── endpoint-agent/           # macOS/Windows agent (Go)
│   ├── otel-collector/           # OpenTelemetry collector config
│   └── cursor-hook/              # Cursor OTel hook
├── docs/                         # Install, User, Implementation guides
├── public/                       # Logos, favicon
├── scripts/                      # Seed, validation, drift checks
├── package.json
├── .env.example
├── vercel.json                   # Cron definitions
├── LICENSE
└── SECURITY.md
```

### Documentation Guides

| Guide | Audience | Location |
|---|---|---|
| **Install Guide** | Engineers deploying locally or to production | [docs/install-guide.md](./docs/install-guide.md) |
| **User Guide** | Compliance officers, admins, reviewers | [docs/user-guide.md](./docs/user-guide.md) |
| **Implementation Guide** | Developers extending or customizing | [docs/implementation-guide.md](./docs/implementation-guide.md) |

---

## Local Development

### Prerequisites
- Node.js 22+
- PostgreSQL 16+ (local or managed: Neon, Supabase, Azure, RDS)
- Google / Microsoft OAuth credentials (required for production)

### Quick Start

```bash
git clone https://github.com/piyushsinghania108/Hold.git
cd Hold

npm install

cp .env.example .env
# Edit .env — see Environment Variable Reference

npm run db:migrate
npm run db:seed

npm run dev
# → http://localhost:3001
```

### Demo Mode
```bash
# In .env
DEMO_MODE=true
NEXT_PUBLIC_DEMO_MODE=true
```
Login: `admin@example.com` / `demo-password`

---

## Deployment Options

Hold is built on portable, standard components — **Next.js**, **Azure Functions runtime**, and **PostgreSQL** — so you are not locked into a single deployment path. Choose the model that matches your operational preferences and security requirements.

### 1. Documented Cloud Path (Vercel + Azure Functions)

The reference deployment. Fastest to production.

| Component | Target | Command |
|---|---|---|
| **App** | Vercel (or any Next.js host) | `vercel --prod` |
| **Proxy** | Azure Functions | `cd ai-proxy && func azure functionapp publish <name>` |
| **Database** | Managed PostgreSQL (Neon, Supabase, Azure, RDS) | `npm run db:deploy` |
| **Cron Jobs** | Vercel Cron (guarded by `CRON_SECRET`) | Defined in `vercel.json` |

**Production checklist:**
- [ ] `DEMO_MODE=false`, `NEXT_PUBLIC_DEMO_MODE=false`
- [ ] `ENABLE_DEV_LOGIN=false`
- [ ] Strong `SETTINGS_ENCRYPTION_KEY` (backed up)
- [ ] `PROXY_SECRET` identical on Vercel + Azure
- [ ] `PROMPT_HASH_SALT` identical on Vercel + Azure
- [ ] Google/Microsoft OAuth configured with production redirect URIs
- [ ] Branch protection on `main` (PR required, CI passing, linear history)
- [ ] Environments: `production`, `staging` (protected branches only)
- [ ] Security: Dependabot, CodeQL, Secret scanning enabled

### 2. Containerized Deployment (Docker / Docker Compose)

Run the entire platform on any Linux host — including a laptop for development or small-scale production.

- **Next.js app** — official Docker support
- **Azure Functions proxy** — can be run as a Docker container image
- **PostgreSQL** — official Docker image

This model provides portability and consistency across environments. A `docker-compose.yml` can orchestrate all three components.

### 3. Kubernetes / Helm (Production-Grade, Multi-Cloud)

For highly available, production-grade deployments on any Kubernetes cluster (EKS, GKE, AKS, or on-prem).

- **Next.js app** — standard containerized workload
- **Proxy** — run the containerized Azure Functions using **KEDA (Kubernetes-based Event Driven Autoscaling)** for serverless scaling, or deploy as a standard long-running service
- **Database** — self-managed PostgreSQL via an operator like **CloudNativePG**, or connect to a managed service

A **Helm chart** can package these components for easy installation and lifecycle management.

### 4. Alternative Cloud & PaaS Platforms

If you prefer managed services but want to avoid Vercel or Azure Functions specifically:

| Component | Alternative Targets |
|---|---|
| **Next.js app** | Netlify, AWS ECS/Fargate, Google Cloud Run, Render.com |
| **Proxy** | Any Kubernetes cluster (via KEDA) — including AWS, GCP, or on-prem |
| **Database** | Any PostgreSQL 16+ instance — Google Cloud SQL, Crunchy Bridge, self-managed on cloud VMs, or CloudNativePG |

This decouples the enforcement plane from a single cloud provider.

### 5. Air-Gapped / Fully Offline

For high-security environments requiring zero internet connectivity.

- Deploy all components (app, proxy, database) using Docker images or Helm charts
- No external dependencies required at runtime
- Ideal for regulated industries, defense, and government

### 6. Hybrid Deployments

Split components across environments to meet specific security or latency requirements.

- **Control plane** (Next.js app + database) — host in your cloud of choice for accessibility
- **Enforcement plane** (proxy) — deploy on-premises or in a separate, hardened network segment close to your AI traffic

This model aligns with the control plane / enforcement plane separation that is core to Hold's architecture.

---

## Extending Hold

| Extension Point | How |
|---|---|
| **New Shadow AI Source** | Add ingest route in `src/app/api/discovered-tools/ingest/`, register cron + Settings UI, extend 164-tool registry |
| **New Provider Telemetry** | Implement sync in `src/lib/integrations/`, map to `UsageBucket`/`CostBucket`/`AssistantDailyStat` |
| **Custom Policy Rules** | UI at `/alerts/prompt-rules` (ReDoS-validated) or add `PolicyRule` evaluated in `ai-proxy/src/lib/policy-enforcement.ts` |
| **New Framework Controls** | Seed via `prisma/seed.ts` → `FrameworkControl` + `ControlCrosswalk` |
| **Custom Reports** | Add data source in `src/lib/reporting/sources/`, create `ReportTemplate` |
| **New Developer AI Surface** | Add OTel ingest route in `src/app/api/telemetry/`, define metrics schema, add dashboard page |
| **Webhook Integrations** | Add route in `src/app/api/webhooks/`, secure with shared secret |

---

## Security & Compliance Posture

- **Secrets encryption at rest** — All credentials encrypted via `SETTINGS_ENCRYPTION_KEY`
- **Zero prompt/response storage** — Proxy strips prompt/code text at OTel ingest; only metadata, decisions, verdicts persisted
- **PII redaction** — Dangerous-prompt alerts store redacted excerpts only
- **Idempotent ingest** — Content-hash dedupe keys prevent duplicate telemetry
- **ReDoS protection** — Prompt-risk patterns validated against ReDoS shapes + 50ms runtime probe
- **Configurable retention** — Per-data-type prune crons (Settings → General)
- **Full audit trail** — `AuditLog` on all mutations with user, action, before/after, IP
- **RBAC** — Admin / Compliance Officer / Viewer enforced in middleware + API route guards
- **Self-hosted** — No SaaS dependency; all data in your PostgreSQL; proxy in your Azure subscription

---

## Objection Handling

| Objection | Response |
|---|---|
| **"We already have a GRC tool."** | Hold is not a GRC tool. It is a control plane that enforces policy in the request path. Your GRC tool documents risk; Hold prevents it. |
| **"We use [Credo AI / Holistic AI / Vanta]."** | Those are visibility and assessment platforms. Hold adds runtime enforcement — a proxy-enforced kill switch, inline DLP, and human-review queues. And it's self-hosted, MIT-licensed, no lock-in. |
| **"We're not ready for runtime enforcement."** | Start in dry-run mode. Policy-as-code has off / dry-run / enforce modes. Roll out gradually with advisory semantics before switching to blocking. |
| **"Self-hosted is too much operational overhead."** | Deploy to your Vercel + Azure + PostgreSQL. Two deployment targets, standard stack. We provide install guides, implementation guides, and enterprise support. |
| **"How do you handle prompt privacy?"** | Zero prompt/response storage. Proxy strips prompt/code text at OTel ingest. Only metadata, decisions, and verdicts are persisted. PII is redacted in alerts. |
| **"What about agent risk?"** | Agents are first-class citizens. Full lifecycle, proxy-enforced kill switch, MCP allowlists, human-review queues, behaviour baselines, scope enforcement. |
| **"We need EU AI Act compliance."** | 96 seeded controls with 107 crosswalks across NIST AI RMF, ISO 42001, EU AI Act, and SOC 2. EU AI Act wizard covers Art. 5/6/27/50, Annex I/III, GPAI/FRIA. |
| **"We use multiple AI providers."** | Hold governs Anthropic, OpenAI, Azure OpenAI, Gemini, and Bedrock equally. And our governance intelligence is provider-agnostic — use any or all. |

---

## Competitive Positioning

| Competitor Category | Examples | Hold's Differentiation |
|---|---|---|
| **AI Governance Platforms** | Credo AI, Holistic AI, IBM watsonx.governance | Runtime enforcement, self-hosted, agent kill switch, MIT license |
| **GRC Platforms** | Vanta, Drata, OneTrust | AI-specific controls, proxy enforcement, shadow AI discovery, agent lifecycle |
| **Cloud Security** | Wiz, Orca, Prisma Cloud | AI-specific posture, EU AI Act wizard, MCP governance, policy-as-code |
| **API Gateways** | Kong, Envoy, Apigee | Governance semantics, compliance evidence, human-review queues, framework mapping |
| **Observability** | Datadog, New Relic | Normalized AI telemetry, cost attribution, per-surface dashboards, compliance reporting |

### Positioning Statement
> **Where Credo AI gives you assessment and Vanta gives you compliance checklists, Hold gives you enforcement. Where Kong gives you API management and Wiz gives you cloud posture, Hold gives you AI governance semantics — with a kill switch.**

---

## Enterprise Support

**Hold** is designed for organizations that need production-grade AI governance without vendor lock-in.

**Piyush Singhania** — Founder, Hold
📧 piyushsinghania66@gmail.com
https://www.linkedin.com/in/piyush65/
🌐 hold site - Live Soon

**Available for:**
- Platform implementation
- EU AI Act readiness
- NIST AI RMF operationalization
- Shadow AI remediation
- Developer AI oversight programs
- Custom integrations
- Compliance program alignment
- Strategic advisory

---

## Contributing

Issues and PRs welcome. Please read [CONTRIBUTING.md](./CONTRIBUTING.md) (to be added) for guidelines.

---

**Hold — Governance that holds.**
*Sovereign. Runtime-enforced. Audit-ready.*
*Built for the enterprise AI era.*
