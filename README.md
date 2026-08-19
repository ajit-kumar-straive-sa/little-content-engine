# The Little Content Engine

> Agentic publish prototype — LearningMate & Chegg  
> A single-file HTML dashboard that simulates an AI-assisted content operations pipeline for professional AI learning programmes.

---

## What it does

The Little Content Engine models a 5-stage editorial workflow where an AI Research Agent surfaces new AI industry signals, and human LD leads decide, blueprint, and route them into production.

### Stages

| # | Stage | Who | What |
|---|-------|-----|------|
| 1 | **Research Queue** | AI Agent | Daily headless scan of OpenAI, Anthropic, Google, Microsoft, GitHub, HuggingFace, ArXiv, TechCrunch, VentureBeat + emerging tools. Each signal is scored by relevance, depth, and professional applicability. |
| 2 | **Review & Decide** | LD Lead | Reviews topic summary, what changed, learner impact, and course delta gaps — then approves or rejects. |
| 3 | **Blueprint & Gap Analysis** | Course Lead + Claude | Gap analysis against catalogue, then Claude generates all production docs at once: briefs, lesson outlines, activity worksheets, video storyboards, knowledge checks. |
| 4 | **Production Board** | Human teams | Kanban board tracking each content item from brief through media production, QA, SCORM packaging, and LMS deploy. |
| 5 | **Published & Sync** | LD Lead | Catalogue rebuild, repo sync, catch-up module compilation. |

---

## Use cases

- **Content signal monitoring** — visualise how an AI agent monitors the full AI landscape and scores candidates for instructional relevance, without manual triage.
- **Layer routing decisions** — prototype how LD leads decide whether a signal warrants a bi-weekly L3 Drop, platform course update (L2), foundational core refresh (L1), catch-up module (L4), or a P2 domain track.
- **Blueprint generation demo** — show stakeholders how Claude can generate a full production document package (brief + outline + worksheets + storyboard + KCs) in a single pass from a topic signal.
- **Editorial calendar planning** — demonstrate rolling bi-weekly L3 drop scheduling, platform-triggered L2 sprints, and quarterly L1 review cadences.
- **Stakeholder walkthrough** — single self-contained HTML file with no build step; share as an attachment or host as a static page for stakeholder demos.

---

## Content layers

| Layer | Name | Cadence | Trigger |
|-------|------|---------|---------|
| L1 | Foundational Core | Quarterly | Quarterly review + major conceptual shifts |
| L2 | Platform Courses | On major release | Auto-alert on major platform releases |
| L3 | Bi-weekly Update Drops | Every 2 weeks | Bi-weekly sprint — any AI development |
| L4 | Catch-up Modules | Every 6–8 weeks | Automated: 4+ L3 drops accumulated |
| P2 | Program 2 Tracks | ~3 month build | Stackable certification tracks |

---

## Deployment

The entire application is a single `index.html` file with no dependencies, no build step, and no server required.

### Run locally

```bash
# Clone the repo
git clone https://github.com/ajitkumar-lmsa/little-content-engine.git
cd little-content-engine

# Open directly in browser
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

### Host as a static site

Drop `index.html` into any static hosting service:

- **GitHub Pages** — push to `main`, enable Pages in repo Settings → Pages → Deploy from branch.
- **Netlify / Vercel** — drag and drop the file or connect the repo; no build command needed.
- **Azure Static Web Apps** — deploy via the included `.github/workflows/jekyll-docker.yml` or configure a direct static deploy.

### GitHub Actions (included)

The repo includes `.github/workflows/jekyll-docker.yml` for automated deployment via GitHub Actions.

---

## Updating canned data

All seed data lives in the `makeSeed()` function and `TOPIC_DETAILS` / `BLUEPRINT_DOCS` objects inside `index.html`. To refresh:

1. Update `const NOW = new Date(...)` to the current date.
2. Edit research signal `detected` dates and topics in the `research` array.
3. Update `schedule` dates and labels to reflect the current sprint calendar.
4. Adjust `kanban` due dates accordingly.
5. Update `TOPIC_DETAILS` narrative text for any topics that have evolved.

---

## Git workflow

```bash
# Pull latest from GitHub
git pull origin main

# Make changes to index.html (data, topics, dates)
git add index.html

# Commit with a descriptive message
git commit -m "data: refresh seed data to Aug 2026 sprint cycle"

# Push to main (triggers GitHub Actions deploy if configured)
git push origin main
```

---

## Tech stack

- **Vanilla HTML/CSS/JS** — zero dependencies, zero build tooling
- **~3 500 lines** — single file, fully self-contained
- All state lives in a plain JS object (`state`); `hardReset()` (click the Chegg logo) restores seed data at any time

---

*Last data refresh: Aug 19, 2026*

