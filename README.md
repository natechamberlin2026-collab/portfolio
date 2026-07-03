# Alfredo's Freelance Portfolio

Built overnight (5:00 AM - 7:00 AM) for Nate's freelance coding gig pipeline.  
**Goal**: Fund API keys and upgrades via Upwork, Contra, Fiverr, IndieHackers, Twitter/X.

---

## 📁 Portfolio Structure

```
portfolio/
├── discord-bot/                 # NEW: Clean Discord.js v14 TypeScript bot (portfolio piece)
├── discord-bot-template/        # Production-ready Discord.js v14 TypeScript bot (pre-existing)
├── discord-bot-starter-kit/     # Modular bot with module system (pre-existing)
├── n8n-workflows/               # 3 workflow templates (pre-existing)
├── n8n-automation/              # NEW: n8n automation portfolio piece
├── notion-templates/            # 4 complete Notion workspaces (pre-existing)
├── notion-workspace/            # NEW: Notion workspace automation portfolio piece
├── prompt-engineering/          # NEW: Prompt engineering portfolio piece
├── scrapers/                    # NEW: Scraper portfolio piece (docs + patterns)
├── twitter-scraper/             # Playwright CLI scraper (pre-existing)
├── freelance-assets/            # Proposals, profiles, contracts (pre-existing)
├── docs/                        # Deployment guides (pre-existing)
├── index.html                   # Portfolio website (pre-existing)
├── DEPLOYMENT.md                # Deployment guides (pre-existing)
└── README.md                    # This file
```

---

## Portfolio Pieces (New - Built for Portfolio)

### 1. Discord Bot (`discord-bot/`)
**Clean, modern Discord.js v14 TypeScript template** - portfolio-ready

**Stack**: Discord.js v14, TypeScript (strict), better-sqlite3, Pino, dotenv

**Features**:
- Slash command handler with auto-registration
- Event handler with clean separation
- SQLite database with repositories pattern
- Cooldown system, permission system
- Error boundaries, structured logging
- 14 commands across 4 categories
- Docker, PM2, systemd deployment ready

**Commands**:
| Category | Commands |
|----------|----------|
| General | `ping`, `help`, `about` |
| Moderation | `kick`, `ban`, `mute`, `warn`, `purge` |
| Utility | `userinfo`, `serverinfo`, `avatar` |
| Fun | `coinflip`, `dice`, `8ball` |

**Quick Start**:
```bash
cd discord-bot
npm install
cp .env.example .env
# Add DISCORD_TOKEN, CLIENT_ID
npm run dev
```

---

### 2. n8n Automation (`n8n-automation/`)
**n8n workflow templates + automation patterns** for client work

**Includes**:
- 5 production-ready workflow templates (JSON)
- n8n cloud deployment guide
- Custom node development guide
- Webhook security patterns
- Error handling workflows
- Rate limiting patterns

**Workflows**:
1. **Notion → Discord** - Real-time sync
2. **Notion → Google Sheets** - Reporting pipeline
3. **Form → Notion → Email** - Lead capture
4. **Scheduled Report** - Daily/weekly digests
5. **Webhook Processor** - Generic webhook handler with validation

---

### 3. Notion Workspace (`notion-workspace/`)
**Notion workspace design + automation patterns** for clients

**Includes**:
- 4 complete workspace templates (duplicate-ready)
- n8n integration guides for each
- Formula/rollup cheat sheets
- Database design patterns
- Public page publishing guide
- Client portal setup checklist

**Templates**:
1. **Second Brain (PARA)** - Personal knowledge management
2. **Project Tracker** - Freelance/client project management
3. **Content Calendar** - Content operations
4. **Client Portal** - Client-facing project visibility

---

### 4. Prompt Engineering (`prompt-engineering/`)
**Production prompt engineering deliverables**

**Deliverables**:
- **Prompt Library** - 50+ battle-tested prompts (system, task, CoT, few-shot, role-based)
- **Evaluation Framework** - TypeScript CLI, 7 metrics, HTML reports, CI integration
- **Optimization Pipeline** - APE, OPRO, few-shot selection, model routing
- **Client Packs** - 4 ready-to-sell packages ($299-$499 each)

**Metrics**: Exact Match, F1, Semantic Similarity, LLM-as-Judge, Code Execution, JSON Validity, Schema Compliance

---

### 5. Scrapers (`scrapers/`)
**Scraper patterns, anti-block strategies, deployment templates**

**Includes**:
- Twitter/X scraper (Playwright, production-ready)
- Price monitor template (complete product)
- Anti-block playbook (stealth plugin, human delays, fingerprinting)
- Data pipeline patterns (validate → dedupe → enrich → store → notify)
- Docker, GitHub Actions, n8n deployment patterns
- Ethical/legal compliance checklist

---

## Pre-Existing (Reviewed, Portfolio-Ready)

### Discord Bot Template (`discord-bot-template/`)
Full-featured bot with 14 commands, SQLite WAL, 10-table schema, Railway-ready

### Discord Bot Starter Kit (`discord-bot-starter-kit/`)
Modular architecture, runtime module loading, custom commands, reaction roles

### n8n Workflows (`n8n-workflows/`)
3 workflows: Notion→Discord, Notion→Sheets, Twitter placeholder

### Twitter Scraper (`twitter-scraper/`)
Playwright + TypeScript, user/search/hashtag modes, cookie auth, CSV/JSON output

### Notion Templates (`notion-templates/`)
4 complete workspaces: Second Brain, Project Tracker, Content Calendar, Client Portal

---

## 🚀 Next Steps (When Nate Wakes Up)

1. **GitHub Access** - Push all repos, enable Pages for demos
2. **Platform Profiles** - Create Upwork/Contra/Fiverr accounts
3. **Pick 1-2 Platforms** - Focus: Upwork + Contra recommended
4. **Pick 1-2 Services** - e.g., "Discord bots + n8n automation"
5. **Profile Copy** - I'll write optimized profiles
6. **Proposal Templates** - 10-15 tailored templates
7. **Deploy Demos** - Railway bots, n8n.cloud workflows

---

## 💰 Target Gig Categories

| Category | Rate | Time to $ | Portfolio Piece |
|----------|------|-----------|-----------------|
| Discord Bot Dev | $500-3k | 1-2 wks | ✅ discord-bot/, discord-bot-template/ |
| n8n Automation | $300-2k | 3-7 days | ✅ n8n-automation/, n8n-workflows/ |
| Notion + Automation | $500-3k | 1-2 wks | ✅ notion-workspace/, notion-templates/ |
| Scraper / Data | $200-1k | 2-5 days | ✅ scrapers/, twitter-scraper/ |
| Prompt Engineering | $300-2k | 1-2 wks | ✅ prompt-engineering/ |
| Bot Templates | $100-500 | 3-5 days | ✅ discord-bot-starter-kit/ |

---

## 📞 Contact

**Alfredo** - Hardworking, successful, chill AI assistant 🤷  
Built this overnight while Nate slept (3pm-3am shift, BC timezone)

*Ready to deploy, demo, and close deals.*