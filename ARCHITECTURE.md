# MilliPrime Co-Op — Technical Architecture

How MilliPrime members collaborate, share infrastructure, and manage systems.

## 1. Co-op Structure

The MilliPrime Co-op is a lightweight collaborative structure — a shared commitment to:
- Build reusable infrastructure together
- Share modules across projects
- Maintain shared repositories and standards
- Split revenue on shared products

Future possibility: structure as a DAO with decentralized governance.

## 2. GitHub Organization

The co-op operates through a shared GitHub org with repos:
- `manifesto` — the public-facing manifesto and movement docs
- `shared-infra` — shared infrastructure modules (auth, monitoring, messaging, analytics, billing)
- `kh` — standards engine (protocols, templates, patterns)
- `templates` — System Config templates, Journey Mapping templates, project scaffolding
- Individual product repos as needed

## 3. Shared Infrastructure (The Starter Kit)

Reusable modules every future project consumes:

| Module | Purpose | Status |
|--------|---------|--------|
| Auth (OTP-based) | User registration, OTP/MFA, JWT | Designed |
| Monitoring | Prometheus-style metrics, dashboard, alerting | Designed |
| Messaging | SMS/WhatsApp/Email dispatch | Partially built |
| Analytics | Page views, conversions, funnel metrics | Not started |
| Billing | Stripe/Square integration patterns | Partially built |
| Logging/Audit | Append-only event logs, action traces | Designed |
| Escalation | Issue severity, routing, notification | Designed |
| Policy Rails | Agent permission boundaries, approval gates | Conceptual |

## 4. Tech Stack (The Founder's Playbook)

The co-op's opinionated tech stack:

| Layer | Technology |
|-------|-----------|
| Local Dev | docker-compose or vanilla Node.js |
| Database | PostgreSQL (Aurora Serverless or Supabase) / SQLite for local |
| Data Access | Raw SQL (no ORM) |
| API + Functions | Lambda + API Gateway via SST v3 |
| Auth | Cognito or custom OTP |
| File Storage | S3 |
| Email | SES |
| Queues/Events | SQS + EventBridge |
| Secrets | SSM Parameter Store |
| Frontend | Vanilla HTML/CSS/JS |
| CDN/Hosting | CloudFront + S3 |
| Monitoring | CloudWatch + custom dashboard |
| Deployment | SST v3 |

## 5. Development Workflow

### Solo Work
- Use AI coding agents for independent builds
- Parallelize standalone tools and utilities
- Sequential codebase-aware iteration for complex systems

### Collaborative Work
- GitHub PRs for shared infrastructure changes
- 1KH Executor Standards for complex journey work
- Shared monitoring dashboard for operational visibility

## 6. Revenue Model

How money flows in the co-op:

1. **Consulting** (immediate revenue) — Client engagements
2. **Modules** (leverage) — Each engagement produces reusable modules
3. **Products** (recurring) — Modules packaged into affordable SaaS ($1-50/mo)
4. **Platform Suites** (scale) — Marketing suite, orchestration suite, business creation suite
5. **Spin-outs** (exit optionality) — Clean-room separation, due diligence packages

Flywheel: **consulting → modules → products → distribution → more consulting → more modules**

## 7. Onboarding New Members

When a new MilliPrime joins:
1. Read the Manifesto
2. Get added to GitHub org
3. Get access to shared monitoring dashboard
4. Review the Founder's Playbook tech stack
5. Pick a first project or contribution
6. Pair with an existing member on first system build

This is a working document, not a manifesto (that's MANIFESTO.md).
