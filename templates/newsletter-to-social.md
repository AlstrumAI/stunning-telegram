# Newsletter → Social Atomization Template

## Step 1: Angle Selection
Read the current edition. Identify the 3-4 strongest hooks. A hook is a single data point or concept that can stand alone without context.

For each hook, rate: surprise factor (1-5), data specificity (1-5), shareability (1-5).

Select top 4 hooks. Assign each to the platform where it performs best:
- **Dramatic single number** → Twitter (punchy, quotable)
- **Visual comparison / multi-week trend** → Instagram carousel (data-visual)
- **Professional analysis / macro thesis** → LinkedIn (credibility, longer form)
- **Mechanical explanation (how something works)** → Video short (educational)
- **Product moment (Relay update, new feature)** → Instagram story (screenshot + link)

## Step 2: Platform-Specific Generation

### Twitter (Mon, Tue, Wed, Fri)
- Monday: The edition's single strongest data point as a standalone tweet. No link in tweet — put link in reply.
- Tuesday: A contrarian take or engagement question derived from the thesis. Must contain a number.
- Wednesday: Watchlist or plays update. "Last edition flagged X. Here's where it is now."
- Friday: COT quick-take after data drops. Screenshot of the Relay + one-sentence thesis.

### Instagram (Mon, Wed, Thu)
- Monday: Relay carousel (5-7 slides). Slide 1 = hook. Slides 2-5 = one asset class each. Slide 6 = thesis. Slide 7 = CTA.
- Wednesday: Educational carousel or reel from "Off the Books" section (4-5 slides).
- Thursday: Story — Relay screenshot or poll based on current positioning.

### LinkedIn (Mon, Wed)
- Monday: 300-500 word newsletter companion. Professional tone, same data, link in first comment.
- Wednesday: 200-400 word macro analysis connecting institutional positioning to broader economics.

### Video Shorts (Wed, Fri)
- Wednesday: 30-60s COT explainer. Generate JSON for COTDataReveal or StructureEducation composition.
- Friday: 45-90s Relay breakdown. Generate JSON for RelayReel composition.

## Step 3: Cross-Reference
Check git history for prior week's edition to ensure no repeated angles.

## Step 4: Output
Write all content to `output/staged/week-YYYY-MM-DD/`. Video JSONs go in `video-data/` subdirectory. Create `angles.md` documenting which hooks were selected and why.
