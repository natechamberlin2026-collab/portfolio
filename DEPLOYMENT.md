# DEPLOYMENT GUIDE — Portfolio Demos

---

## 1. Discord Bot → Railway (5 min)

### Prerequisites
- GitHub repo pushed: `discord-bot-template`
- Discord App created: https://discord.com/developers/applications
- Bot token + Client ID copied

### Steps

1. **Railway Login**
   - railway.app → Login with GitHub

2. **New Project**
   - "Deploy from GitHub repo" → Select `discord-bot-template`
   - Railway auto-detects Node.js

3. **Environment Variables** (Settings → Variables)
   ```
   DISCORD_TOKEN=your_bot_token_here
   CLIENT_ID=your_application_id_here
   GUILD_ID=your_test_guild_id_optional
   DB_PATH=/data/bot.sqlite
   NODE_ENV=production
   LOG_LEVEL=info
   ```

4. **Add Volume** (Critical for SQLite)
   - Settings → Volumes → Add Volume
   - Name: `bot-data`
   - Mount Path: `/data`
   - Size: 1 GB

5. **Deploy**
   - Railway builds: `npm install` → `npm run build` → `npm start`
   - Watch logs for "Logged in as [bot name]"

6. **Verify**
   - Invite bot to test server: `https://discord.com/oauth2/authorize?client_id=YOUR_CLIENT_ID&permissions=8&scope=bot%20applications.commands`
   - Run `/ping` in Discord

### Custom Domain (Optional)
- Settings → Networking → Custom Domain
- Add CNAME: `bot.yourdomain.com` → `up.railway.app`

---

## 2. n8n Workflows → n8n.cloud (10 min)

### Option A: n8n.cloud (Easiest)
1. n8n.cloud → Start Free (1 workflow, 100 executions/month)
2. Import each workflow:
   - Workflows → Import → Select `.json` file
   - `notion-discord/workflow.json`
   - `notion-sheets/workflow.json`
   - `twitter-scraper/workflow.json`
3. Add Credentials:
   - Notion API: Integration token + database IDs
   - Discord: Webhook URL or Bot token
   - Google Sheets: OAuth2
4. Activate each workflow
5. Test: Add item to Notion DB → Check Discord/Sheets

### Option B: Self-Hosted (More Control)
```bash
# Docker
docker run -it --rm \
  --name n8n \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  docker.n8n.io/n8nio/n8n
```
- Access: http://localhost:5678
- Same import process

---

## 3. Notion Templates — Publish & Share (5 min each)

### For Each Template (`portfolio/notion-templates/*/`)
1. Open Notion → Import → JSON (or recreate from `template.json`)
2. Duplicate to your workspace
3. **Share → Publish → Allow duplicate as template**
4. Copy public link
5. Add to:
   - GitHub README
   - Profile bios
   - Proposal attachments

### Template Links to Update
| Template | Your Public Link |
|----------|------------------|
| Second Brain | `https://your-notion.site/second-brain-xxx` |
| Project Tracker | `https://your-notion.site/project-tracker-xxx` |
| Content Calendar | `https://your-notion.site/content-calendar-xxx` |
| Client Portal | `https://your-notion.site/client-portal-xxx` |

---

## 4. Twitter Scraper → GitHub Actions (Optional Demo)

### For Live Demo (Not Required)
1. Add secrets to GitHub repo (`twitter-scraper`):
   - `TWITTER_AUTH_TOKEN`
   - `TWITTER_CT0`
2. Workflow runs on schedule or manual trigger
3. Artifacts: JSON/CSV downloads

### `.github/workflows/scraper.yml`
```yaml
name: Scraper Demo
on:
  workflow_dispatch:
    inputs:
      type:
        type: choice
        options: [user, search, hashtag]
      target:
        type: string
      max:
        type: string
        default: '50'
jobs:
  scrape:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: '20' }
      - run: npm ci && npx playwright install chromium
      - run: npm run build
      - run: node dist/index.js ${{ github.event.inputs.type }} "${{ github.event.inputs.target }}" --max ${{ github.event.inputs.max }} --headless
        env:
          TWITTER_AUTH_TOKEN: ${{ secrets.TWITTER_AUTH_TOKEN }}
          TWITTER_CT0: ${{ secrets.TWITTER_CT0 }}
      - uses: actions/upload-artifact@v4
        with:
          name: scraped-data
          path: output/
```

---

## 5. GitHub Pages — Portfolio Site (5 min)

### Each Repo
1. Settings → Pages
2. Source: "Deploy from branch"
3. Branch: `main` / `root`
4. Save → URL: `https://yourusername.github.io/repo-name/`

### Main Portfolio (`portfolio/`)
- Already has `README.md` → becomes index
- Customize: Add your name, links, demo URLs

---

## 6. Environment Variable Templates

### Discord Bot (`.env`)
```bash
DISCORD_TOKEN=
CLIENT_ID=
GUILD_ID=
DB_PATH=./data/bot.sqlite
LOG_LEVEL=info
NODE_ENV=production
```

### n8n (`.env` for self-hosted)
```bash
N8N_BASIC_AUTH_ACTIVE=true
N8N_BASIC_AUTH_USER=admin
N8N_BASIC_AUTH_PASSWORD=
N8N_HOST=0.0.0.0
N8N_PORT=5678
N8N_PROTOCOL=http
WEBHOOK_URL=https://yourdomain.com/
GENERIC_TIMEZONE=America/Vancouver
```

### Twitter Scraper (`.env`)
```bash
TWITTER_AUTH_TOKEN=
TWITTER_CT0=
HEADLESS=true
SCROLL_DELAY_MS=2000
MAX_TWEETS=100
OUTPUT_DIR=./output
OUTPUT_FORMAT=json
```

---

## 7. Quick Verification Checklist

| Demo | URL | Test |
|------|-----|------|
| Discord Bot | Railway URL | `/ping` works |
| n8n Notion→Discord | n8n.cloud | Notion item → Discord msg |
| n8n Notion→Sheets | n8n.cloud | Notion item → Sheets row |
| Notion Second Brain | Notion link | Duplicate works |
| Notion Project Tracker | Notion link | Duplicate works |
| GitHub Portfolio | `github.io/portfolio` | Loads correctly |

---

## 8. Troubleshooting

### Railway: "Database locked"
- Volume not mounted → Check Settings → Volumes
- Multiple instances → Scale to 1 replica

### n8n: "Credential test failed"
- Notion: Check integration shared with database
- Discord: Webhook URL valid? Bot has perms?
- Google Sheets: OAuth consent screen published?

### Discord: Commands not showing
- Run deploy: `npm run deploy:commands` (or bot auto-deploys on start)
- Wait 1hr for global, instant for guild commands
- Check bot has `applications.commands` scope

### GitHub Pages: 404
- Check repo has `index.html` or `README.md`
- Settings → Pages → Branch = main
- Wait 5-10 min for first deploy

---

## 9. Costs (Monthly)

| Service | Free Tier | Paid If Needed |
|---------|-----------|----------------|
| Railway | $5 credit/mo | $5/mo after |
| n8n.cloud | 1 workflow | $20/mo (unlimited) |
| Notion | Personal free | $8/mo (Plus) |
| GitHub Pages | Free | Free |
| Discord | Free | Free |

**Total to start: $0**

---

*All configs in `/portfolio/` repos. Copy `.env.example` → `.env` and fill.*