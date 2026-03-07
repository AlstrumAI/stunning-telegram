# Alstrum Marketing OS

> The marketing operating system for [Breaking Structure](https://breakingstructure.substack.com) and [Alstrum AI](https://alstrum.ai). Clone on any machine, open Claude Code, generate a full week of distribution from the current newsletter edition.

## What This Is

A git-backed marketing brain for a solo founder running a weekly financial newsletter and trading platform. Any Claude Code session on any machine reads `CLAUDE.md`, understands the product, the voice, the audience, and the workflow — then generates platform-ready social content, video data files, and deployment checklists without re-explaining anything.

Built for [Breaking Structure](https://breakingstructure.substack.com) — a weekly institutional positioning newsletter using CFTC/COT data — and [Stryk by Alstrum](https://app.alstrum.ai) — an AI-powered trading platform with the Relay, a live cross-asset institutional flow visualization.

## How It Works

```
Friday    → COT data drops → Relay updates on alstrum.ai → screenshot story + teaser tweet
Saturday  → Write newsletter → schedule on Substack → paste into published/current-edition.md → push
Sunday    → CC batch generates all social + video data JSONs → review → push staged content
Mon-Fri   → Deploy staged content → 15-20min daily engagement
Friday    → Loop restarts
```

One newsletter in. A full week of cross-platform distribution out. Every piece grounded in the actual edition, the actual voice, and the actual data.

## Repo Structure

```
CLAUDE.md               ← The brain. CC reads this first. Non-negotiable.
context/
  product.md            ← Stryk, the Relay, four trading modes, AlphaNet ML
  company.md            ← Alstrum AI, Delaware C-Corp, State Street origin story
  voice-style.md        ← Extracted from 6 published editions. The canonical voice.
  icp.md                ← Ideal customer + competitive positioning
  genesis-pass.md       ← Lifetime access offer, launch sequence, naming rules
published/
  current-edition.md    ← This week's edition only. Replaced every Saturday.
strategy/
  engagement-targets.md ← 20-30 accounts for daily 15-20min engagement
  growth-accelerators.md← Podcasts, guest posts, big account features
skills/                 ← Curated marketing skills (from coreyhaines31/marketingskills)
templates/
  newsletter-to-social.md  ← Angle selection → platform assignment → generation
  video-data-schemas.md    ← JSON schemas for each Remotion video composition
  deploy-checklist.md      ← Step-by-step Friday→Saturday→Sunday→Mon-Fri workflow
data/
  accounts.md           ← Handles, follower counts, tools, canonical URLs
  metrics.md            ← Weekly subscriber count, open rates, best posts
  audience-signals.md   ← What readers ask, what resonates, content ideas
output/staged/
  week-YYYY-MM-DD/      ← Generated content ready to deploy
    angles.md           ← Which hooks were selected and why
    monday-twitter.md
    monday-linkedin.md
    monday-insta-carousel.md
    twitter-tue-wed-fri.md
    wednesday-insta-carousel.md
    thursday-story.md
    video-data/         ← JSONs for Remotion rendering
```

## Video Pipeline

Social video is rendered programmatically via [Remotion](https://remotion.dev). CC generates JSON data files. The Remotion project (`bs-video/`) renders 1080×1920 vertical MP4s.

**Compositions available:** RelayReel, COTDataReveal, ExitLiquidityHook, StructureEducation, WeeklyNumbers, FridayCOTStory, WhatIsBS, WhatIsAlstrum, RelayEducation

```bash
cd bs-video
./render.sh RelayReel ../output/staged/week-2026-03-10/video-data/relay-reel-006.json
./render.sh COTDataReveal ../output/staged/week-2026-03-10/video-data/cot-data-reveal-006.json
./render.sh StructureEducation ../output/staged/week-2026-03-10/video-data/structure-education-006.json
./render.sh WeeklyNumbers ../output/staged/week-2026-03-10/video-data/weekly-numbers-006.json
```

## Five Content Pillars

| Pillar | Name | What It Covers |
|--------|------|---------------|
| P1 | Institutional Positioning Data | COT numbers, contract counts, the Relay |
| P2 | Market Structure Education | SMC concepts confirmed by COT data |
| P3 | Macro Narrative | Cross-asset thesis, connecting markets |
| P4 | Build in Public | Alstrum development, founder journey |
| P5 | Exit Liquidity Education | "You are exit liquidity and here's proof" |

## The Closed Loop

```
Friday COT drops
  → Relay updates (Bonds → Currencies → Commodities → Equities → Crypto)
  → Watchlist generated from positioning shifts
  → Trade entry zones identified from structure + COT alignment
  → Monday newsletter published with full analysis
  → Social content atomized across platforms
  → Social drives subscribers back into the loop
```

## Quick Start

1. Clone this repo
2. Open Claude Code (any machine)
3. CC reads `CLAUDE.md` automatically — no setup needed
4. Say: *"Generate this week's distribution from the current edition"*
5. Review output in `output/staged/week-YYYY-MM-DD/`
6. Deploy across platforms using `templates/deploy-checklist.md`

## Minimum Viable Week

When deep in product work, hit three touchpoints:
- Newsletter publishes (already scheduled Saturday)
- Friday Relay screenshot story on Instagram
- One tweet with the strongest data point

The machine stays alive.

## Built With

- [Claude Code](https://claude.ai) — content generation engine (Kairo)
- [Remotion](https://remotion.dev) — programmatic video rendering
- [Substack](https://substack.com) — newsletter platform
- [Typefully](https://typefully.com) — Twitter/X scheduling
- [OpenAI TTS](https://platform.openai.com) — video voiceover generation

---

*Breaking Structure — the newsletter for people tired of being exit liquidity.*

*Alstrum AI — the operating system of modern trading.*
