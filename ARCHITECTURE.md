# Milliprime Co-op Technical Architecture

How Paul and Dan (and future members) collaborate, share infrastructure, and manage code/systems.

## 1. Co-op Structure

The Milliprime Co-op is a lightweight collaborative structure. Not a formal legal entity (yet). It's a shared commitment to:
- Build reusable infrastructure together
- Share modules across projects
- Maintain shared repositories and standards
- Split revenue on shared products

Future possibility: structure as a DAO with decentralized governance and dLLMs.

## 2. GitHub Organization

Propose a GitHub org structure. Paul already has:
- https://github.com/agent-intake-protocol/agent-intake-protocol (AIP spec)
- The AIP registry deploying to https://agentintake.io/

Suggest a GitHub org like `milliprime` or `milliprime-coop` with repos:
- `manifesto` — the public-facing manifesto and movement docs
- `shared-infra` — shared infrastructure modules (auth, monitoring, messaging, analytics, billing)
- `kh` — Thousand Hands framework (Paul's meta-framework, may stay in Paul's personal repos)
- `templates` — System Config templates, Journey Mapping templates, project scaffolding
- Individual product repos as needed

## 3. Shared Infrastructure (The Starter Kit)

Reusable modules every future project consumes:

| Module | Purpose | Status |
|--------|---------|--------|
| Auth (Cognito-based) | User registration, OTP/MFA, JWT | Designed (1KH Playbook) |
| Monitoring | Prometheus-style metrics, dashboard, alerting | Designed (KH_FUTURES) |
| Messaging | SMS/WhatsApp/Email via SES/Twilio/Meta Cloud API | Partially built |
| Analytics | Page views, conversions, funnel metrics | Not started |
| Billing | Stripe/Square integration patterns | Partially built (MVH) |
| Logging/Audit | Append-only event logs, action traces | Designed (1KH v2) |
| Escalation | Issue severity, routing, notification | Designed (MVH Phase 2) |
| Policy Rails | Agent permission boundaries, approval gates | Conceptual |
| Agent Intake | Agent onboarding protocol (AIP) | Live at agentintake.io |

## 4. Tech Stack (The Founder's Playbook)

The co-op's opinionated tech stack:

| Layer | Technology |
|-------|-----------|
| Local Dev | docker-compose (Postgres, Redis, Node app) |
| Database | Aurora Serverless v2 (PostgreSQL) |
| Data Access | Raw SQL via pg client (no ORM) |
| API + Functions | Lambda + API Gateway via SST v3 (Ion) |
| Auth | AWS Cognito |
| File Storage | S3 |
| Email | SES |
| Queues/Events | SQS + EventBridge |
| Secrets | SSM Parameter Store |
| Frontend | Vanilla HTML/CSS/JS |
| CDN/Hosting | CloudFront + S3 |
| Monitoring | CloudWatch + custom dashboard |
| Deployment | SST v3 (sst dev / sst deploy --stage prod) |

## 5. Development Workflow

How co-op members work:

### Solo Work
- Use Claude Code or OpenClaw for independent builds
- OpenClaw for parallelizable standalone tools (GTM platforms, utilities)
- Claude Code for codebase-aware iteration
- Cowork for planning, documentation, coordination

### Collaborative Work
- GitHub PRs for shared infrastructure changes
- 1KH Executor Standards for complex journey work
- System Configs for new business capabilities
- Shared monitoring dashboard for operational visibility

### Tool Allocation
| Tool | Best For |
|------|----------|
| OpenClaw | Standalone builds, parallelization, quick prototypes |
| Claude Code | Codebase-aware iteration, complex debugging, sequential work |
| Cowork | Planning, documentation, coordination, research |
| 1KH Executor | Journey-driven development, multi-step UAT, coherent systems |
| 1KH SC Builder | Generating new JMs from System Config specs |

## 6. Project Registry

Track all active projects/systems:

| Project | Owner | Status | Stack |
|---------|-------|--------|-------|
| Man vs Health | Paul | Phase 1 UAT → Go-Live | Supabase → Playbook (Phase 2) |
| Agent Intake Protocol | Paul | Live (agentintake.io) | GitHub Pages + Registry |
| Cold Email Platform | Paul | Built (GTM) | TBD |
| Social DM Platform | Paul | Built (GTM) | TBD |
| YouTube VideoGen | Paul | Built (GTM) | TBD |
| YOMO | Paul | Concept → First campaign | TBD |
| Jemini.io | Dan | Active consulting | Existing |
| [New Intake Project] | Paul | Upcoming — first SC candidate | Playbook |

## 7. Revenue Model

How money flows in the co-op:

1. **Consulting** (immediate revenue) — Client engagements through Jemini or direct
2. **Modules** (leverage) — Each engagement produces reusable modules
3. **Products** (recurring) — Modules packaged into SaaS products ($1-50/mo, affordable)
4. **Platform Skins** (scale) — Marketing suite, orchestration suite, business creation suite
5. **Spin-outs** (exit optionality) — Clean-room separation, due diligence packages, valuation snapshots

Flywheel: consulting → modules → products → distribution → more consulting → more modules

## 8. Communication & Coordination

- GitHub Issues/Discussions for async technical coordination
- Shared monitoring dashboard for operational awareness
- Jam Session (future) for mobile input into the system
- Regular sync meetings (weekly or bi-weekly)
- Manifesto as the philosophical north star

## 9. Onboarding New Members

When a new Milliprime joins:
1. Read the Manifesto
2. Get added to GitHub org
3. Get access to shared monitoring dashboard
4. Review the Founder's Playbook tech stack
5. Pick a first project or contribution
6. Pair with an existing member on first system build

Keep it clean, technical but accessible. This is a working document, not a manifesto (that's MANIFESTO.md).
