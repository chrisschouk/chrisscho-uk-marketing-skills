# Marketing Skills for chrisscho.uk, Total Audio Promo, NewsJack, SpotCheck

Public marketing skills pack for Chris Schofield's brands. **Memory lives in the private [growth-os](https://github.com/chrisschouk/growth-os) repo; this repo is public recipes only.**

## What's here

Marketing skills for:

- **chrisscho.uk** — £750 AI workflow audit for owner-run businesses (2–20 people)
- **Total Audio Promo** — £59 radio/playlist/blog pack for indie artists
- **NewsJack** — reactive PR scoring powered by newsjack.cc
- **SpotCheck** — botted playlist auditor

## Installation

Primary installation using Agent Skills CLI:

```bash
npx skills add chrisschouk/chrisscho-uk-marketing-skills
```

This installs to `~/.agents/skills` and automatically creates symlinks for Claude Code, Cursor, Codex, and Gemini when those directories exist.

**Optional**: Clone directly into your harness's skills directory:

| Harness | Common Skills Directory |
|---------|------------------------|
| Claude Code | `~/.claude/skills` |
| Cursor | `~/.cursor/skills` or `~/.agents/skills` |
| Codex | `~/.codex/skills` |
| Gemini / Antigravity | `~/.gemini/antigravity/skills` |

## Skills structure

```
skills/
├── shared/               # Cross-brand skills
│   ├── growth-os-read/   # How to read/update marketing memory
│   ├── commodity-gate/   # Quality check before publishing
│   └── eval-loop/        # Document failures so agents don't repeat them
├── chrisschouk/          # chrisscho.uk brand
│   ├── chrisscho-outreach/   # Cold outreach (cafe voice, 15-min ask)
│   └── local-seo/            # Brighton local SEO (no city-clone factories)
├── tap/                  # Total Audio Promo brand
│   ├── tap-outreach/         # Pack outreach (£59, artists who paid 4 figs)
│   └── indie-artist-pack/    # Release strategy for pack
├── newsjack/             # NewsJack brand
│   └── newsjack-scoring/     # Reactive PR scoring (4 signals)
├── spotcheck/            # SpotCheck brand
│   └── botted-playlist-auditor/  # Fake stream detection
└── _parked/              # Generic skills not in active use
```

## Brand rules

| Brand | Voice | ICP | Excludes |
|-------|-------|-----|----------|
| **chrisscho.uk** | Cafe (conversational, Brighton-specific) | Owner-run, 2–20 people, B2B services | James Groom / JustAir, Southpoint, Brighton Electric (on hold) |
| **Total Audio Promo** | Indie artist insider (music scene, no corporate fluff) | Artists who paid 4 figs for PR/radio | Holy Basil, LAMIA, Kag Katumba |
| **NewsJack** | Reactive PR (score > 60 = post now) | Tech/music industry news consumers | n/a |
| **SpotCheck** | Auditor (terse, technical) | Artists/labels checking playlist authenticity | n/a |

## Global rules (all brands)

- **UK spelling** (optimise not optimize, favour not favor)
- **No em dashes** (commas or full stops only)
- **Agents draft, Chris hits send** (never auto-send)
- **Metric = qualified replies + pipeline** (not messages sent)
- **Never invent emails, quotes, or customer data**
- **Every claim needs a source path** (in growth-os)

## Memory vs recipes

- **This public repo (recipes)**: How to do the task, frameworks, templates
- **growth-os (memory)**: Customer intel, excludes, pricing, eval corrections, what the market is telling us

Before writing copy or outreach, read `growth-os/brands/{brand}/` for excludes and context.

## Author

**Chris Schofield**  
[chrisscho.uk](https://chrisscho.uk) — £750 AI Workflow Audit for owner-run businesses (2–20 people)  
[Total Audio Promo](https://totalaudiopromo.com) — £59 radio/playlist/blog pack for indie artists

Not "AI developer tools". Not "Digital Employee Infrastructure".
