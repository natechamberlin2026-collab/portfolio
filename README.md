# Alfredo's Freelance Portfolio

Built overnight (5:00 AM - 7:00 AM) for Nate's freelance coding gig pipeline.  
**Goal**: Fund API keys and upgrades via Upwork, Contra, Fiverr, IndieHackers, Twitter/X.

---

## 📁 Portfolio Structure

```
portfolio/
├── discord-bot-template/        # Production-ready Discord.js v14 TypeScript bot
├── discord-bot-starter-kit/     # Modular bot with module system (pre-existing)
├── n8n-workflows/               # 3 workflow templates
├── twitter-scraper/             # Playwright CLI scraper
└── notion-templates/            # 4 complete Notion workspaces
```

---

## 1. Discord Bot Template (`discord-bot-template/`)

**Stack**: Discord.js v14, TypeScript, SQLite (WAL), Winston, Railway-ready

### Commands (14 total)

| Category | Commands |
|----------|----------|
| **Moderation** | `ban`, `kick`, `mute`, `unmute`, `timeout`, `warn`, `purge` |
| **Utility** | `ping`, `serverinfo`, `userinfo`, `avatar` |
| **Fun** | `roll` (dice), `8ball`, `coinflip` |

### Database Schema
- `users` - Discord user tracking
- `guilds` - Server tracking
- `guild_members` - Member/role tracking
- `mod_logs` - Moderation audit trail
- `warnings` - Warning system
- `custom_commands` - User-defined commands
- `reaction_roles` - Reaction role assignments
- `automod_settings` - Auto-moderation config
- `guild_settings` - Per-guild config
- `command_cooldowns` - Rate limiting

### Quick Start
```bash
cp .env.example .env
# Add DISCORD_TOKEN, CLIENT_ID, GUILD_ID (optional)
npm install
npm run build
npm start
```

### Deploy to Railway
```bash
railway login
railway init
railway up
```

---

## 2. Discord Bot Starter Kit (`discord-bot-starter-kit/`)

**Pre-existing, reviewed** - Modular architecture with:
- Event handler, command handler with cooldowns
- Module system (load/unload at runtime)
- Custom commands, reaction roles, guild settings
- SQLite database with full moderation schema

---

## 3. n8n Workflows (`n8n-workflows/`)

| Workflow | Trigger | Actions |
|----------|---------|---------|
| **Notion → Discord** | Minute poll on Notion DB | Send Discord message, update Notion "Notified" checkbox |
| **Notion → Google Sheets** | Hourly poll | Transform data, append to Sheets |
| **Twitter Scraper** | Manual/Scheduled | Placeholder - use Playwright scraper instead |

### Import
In n8n: Workflows → Import → Select `.json` file

---

## 4. Twitter/X Scraper (`twitter-scraper/`)

**Stack**: Playwright, TypeScript, Commander.js, CSV-Writer

### Commands
```bash
npm run scrape:user -- elonmusk
npm run scrape:search -- "ai automation"
npm run scrape:hashtag -- "#buildinpublic"
```

### Auth (Required for most scraping)
Export cookies from browser:
- `auth_token` → `TWITTER_AUTH_TOKEN`
- `ct0` → `TWITTER_CT0`

### Output
- JSON or CSV in `./output/`
- Fields: id, url, text, author, metrics, media, timestamps

---

## 5. Notion Templates (`notion-templates/`)

### A. Second Brain (PARA Method)
**7 Databases**: Inbox, Projects, Areas, Resources, Tasks, Notes, Daily Notes  
**4 Pages**: Dashboard, Weekly Review, Monthly Review, Project Template  
**n8n Setup Guide**: `n8n-setup.md` with 6 automations

### B. Project Tracker (Freelance)
**6 Databases**: Clients, Projects, Milestones, Invoices, Tasks, Time Entries  
**4 Pages**: Dashboard, New Project Wizard, Invoice Tracker, Time Log

### C. Content Calendar
**5 Databases**: Content Ideas, Calendar, Metrics, Pillars, Repurposing Map  
**4 Pages**: Dashboard, Idea Inbox, Analytics, Repurposing

### D. Client Portal
**5 Databases**: Projects (Client View), Milestones, Deliverables, Communications, Invoices  
**4 Public Pages**: Welcome, Status Dashboard, Resources, Meeting Notes

---

## 🚀 Next Steps (Tomorrow)

1. **GitHub Access** - Push all repos, enable Pages for demos
2. **Platform Profiles** - Nate creates Upwork/Contra/Fiverr accounts
3. **Pick 1-2 Platforms** - Focus efforts (recommend: Upwork + Contra)
4. **Pick 1-2 Services** - e.g., "Discord bots + n8n automation"
4. **Profile Copy** - I'll write optimized profiles
5. **Proposal Templates** - 10-15 tailored templates
6. **Deploy Demos** - Railway bots, n8n.cloud workflows

---

## 💰 Target Gig Categories

| Category | Rate | Time to $ | Portfolio Piece |
|----------|------|-----------|-----------------|
| Discord Bot Dev | $500-3k | 1-2 wks | ✅ Bot Template |
| n8n Automation | $300-2k | 3-7 days | ✅ Workflows |
| Notion + Automation | $500-3k | 1-2 wks | ✅ 4 Templates |
| Scraper / Data | $200-1k | 2-5 days | ✅ Twitter Scraper |
| Bot Templates | $100-500 | 3-5 days | ✅ Starter Kit |

---

## 📞 Contact

**Alfredo** - Hardworking, successful, chill AI assistant 🤷  
Built this overnight while Nate slept (3pm-3am shift, BC timezone)

*Ready to deploy, demo, and close deals.*