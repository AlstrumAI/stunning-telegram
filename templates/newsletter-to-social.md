# Newsletter → Social Atomization Template

## What This Does
CC reads the current edition from `published/current-edition.md` and generates a full week of social content + video data JSONs. Everything comes from the edition. Nothing is made up.

## Read First
1. `context/voice-style.md`
2. `strategy/video-growth.md` (video is a growth channel, not a summary format)
3. `published/current-edition.md` (this week's source)

## Step 1: Pick the Hooks
Read the edition. Find 4-5 data points or concepts that can stand alone. Score each:

| Criteria | What It Means |
|----------|--------------|
| Surprise (1-5) | Would this stop someone scrolling? |
| Specificity (1-5) | Does it have a concrete number? |
| Shareability (1-5) | Would someone send this to a friend? |
| Video potential (1-5) | Can it be a 15-25s video with visuals? |

Assign each hook to the platform where it hits hardest:
- **Dramatic single number** → Twitter
- **Visual trend / multi-week data** → Instagram carousel
- **Professional macro analysis** → LinkedIn
- **Surprising mechanism or "how it works"** → Video short
- **Product moment (Relay update)** → Instagram story

## Step 2: Generate Video (Do This First — Highest Reach)
Pick 2-3 hooks with highest video potential. Generate JSONs per `templates/video-data-schemas.md`. Follow the 5-beat structure from `strategy/video-growth.md`. One concept per video.

## Step 3: Generate Twitter (Mon, Tue, Wed, Fri)
- **Monday**: Strongest data point from the edition. Link in reply, not in tweet.
- **Tuesday**: Contrarian take or divergence. Must contain a number.
- **Wednesday**: Watchlist follow-up or COMEX/delivery tracking update.
- **Friday**: COT quick-take after 3:30pm drop. Relay screenshot + one sentence. (Placeholder until Friday.)

## Step 4: Generate Instagram (Mon, Wed, Thu)
- **Monday**: Carousel from the Relay or strongest positioning shift. 5-7 slides. Hook → data → thesis → CTA.
- **Wednesday**: Educational carousel from "Off the Books" section. Or post the Wednesday video as a Reel.
- **Thursday**: Story — poll or Relay screenshot with link sticker.

## Step 5: Generate LinkedIn (Mon)
- **Monday**: 300-500 word newsletter companion. Professional tone. Link in first comment.

## Step 6: Cross-Reference
Check git history for prior week's `published/current-edition.md`. Don't lead with the same angle two weeks running.

## Step 7: Output
Write everything to `output/staged/week-YYYY-MM-DD/`:
- `angles.md` — which hooks were selected and why
- Social posts as markdown files
- `video-data/` — JSONs for Remotion
