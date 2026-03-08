# Video Data Schemas

CC generates these JSONs from the current edition. Windows box renders via `render.sh <composition> <json-path>`.

**Read `strategy/video-growth.md` first.** Every video follows the 5-beat structure: Pattern Interrupt → Curiosity Gap → Reveal → Reframe → CTA. The captions must follow this rhythm.

## Series Branding (All Compositions)
Every video gets a `series` field — the brand name shown as an overlay. No episode numbers.
- COTDataReveal → `"THE NUMBERS"`
- StructureEducation → `"HOW THE MACHINE WORKS"`
- RelayReel → `"THE RELAY"`
- WeeklyNumbers → `"THE NUMBERS"`
- ExitLiquidityHook → `"EXIT LIQUIDITY"`

## Caption Rhythm (All Compositions)
```json
"captions": [
  { "text": "[PATTERN INTERRUPT — big number or provocation]", "highlights": ["key number"], "startTime": 0, "endTime": 2.0 },
  { "text": "[CURIOSITY GAP — what people think vs what data shows]", "highlights": ["contrasting word"], "startTime": 2.5, "endTime": 5.0 },
  { "text": "[REVEAL — data points, one per 3-4s]", ... },
  { "text": "[REFRAME — That's not X. That's Y.]", "highlights": ["Y"], ... },
  { "text": "[CTA — like and subscribe + link in bio]", "highlights": [], ... }
]
```

## Voiceover Schema (All Compositions)
All compositions include a `voiceover` array and `audioPrefix` field for TTS narration. Each entry maps to one beat of the 5-beat structure. The `generate-tts.mjs` script reads these to produce per-beat WAV files.
```json
"voiceover": [
  { "beat": "interrupt", "text": "Spoken text for this beat.", "startFrame": 0, "endFrame": 90 },
  { "beat": "gap", "text": "...", "startFrame": 90, "endFrame": 180 },
  { "beat": "reveal", "text": "...", "startFrame": 180, "endFrame": 450 },
  { "beat": "reframe", "text": "...", "startFrame": 450, "endFrame": 540 },
  { "beat": "cta", "text": "...", "startFrame": 540, "endFrame": 600 }
],
"audioPrefix": "composition_name"
```
- `startFrame`/`endFrame`: Frame range at 30fps where this beat's audio plays
- `audioPrefix`: Used by TTS script to name output files (e.g., `cot_data_reveal_interrupt.wav`)
- Voiceover text should be relaxed, trader-adjacent, accessible — not reading captions verbatim

## RelayReel (15s at 30fps = 450 frames)
Use when: the Relay changed significantly this week (nodes flipped, new status). Includes TTS voiceover.
```json
{
  "week": "Week of [date]",
  "series": "THE RELAY",
  "stages": [
    { "name": "Bonds", "arrow": "↑|↗|→|↓", "headline": "short data point", "detail": "one line" }
  ],
  "thesis": "One sentence connecting the chain.",
  "showCaptions": true,
  "captions": [...],
  "voiceover": [...],
  "audioPrefix": "relay_reel"
}
```

## COTDataReveal (20s = 600 frames)
Use when: a dramatic data trend built over multiple weeks (numbers building then stopping, acceleration, reversal). Includes TTS voiceover.
```json
{
  "hook": "Single dramatic number.",
  "subhook": "Why that number matters — the curiosity gap.",
  "series": "THE NUMBERS",
  "rows": [
    { "date": "string", "value": "string", "change": "string", "story": "1-3 word narrative" }
  ],
  "insight": "The reframe. 'That's not X. That's Y.'",
  "columnHeaders": ["Date", "Position", "Change", "Story"],
  "showCaptions": true,
  "captions": [...],
  "voiceover": [...],
  "audioPrefix": "cot_data_reveal"
}
```

## ExitLiquidityHook (15s = 450 frames)
Use when: a clear retail-vs-institutional split happened (sweep, liquidation, positioning divergence).
```json
{
  "hook": "What happened on the surface.",
  "retailSide": { "label": "RETAIL", "action": "what they did", "emotion": "what they felt" },
  "institutionalSide": { "label": "INSTITUTIONS", "action": "what they did", "data": "the number" },
  "result": "price A → price B",
  "punchline": "The reframe.",
  "showCaptions": true,
  "captions": [...]
}
```

## StructureEducation (25s = 750 frames)
Use when: the "Off the Books" section explains a mechanism (dark pools, collateral chains, margin mechanics, sweeps). Includes TTS voiceover.
```json
{
  "concept": "Name",
  "definition": "One sentence. Surprising or contrarian.",
  "series": "HOW THE MACHINE WORKS",
  "steps": [
    { "label": "Step name", "detail": "Simple, one idea per step" }
  ],
  "cotConfirmation": "How this week's COT confirms it. Specific numbers from current edition.",
  "takeaway": "The reframe. One sentence. Shareable.",
  "showCaptions": true,
  "captions": [...],
  "voiceover": [...],
  "audioPrefix": "structure_education"
}
```

## WeeklyNumbers (12s = 360 frames)
Use when: the edition has 5-6 standout numbers worth rapid-fire display. Includes TTS voiceover.
```json
{
  "numbers": [
    { "value": "+465K", "label": "Treasury Contracts", "context": "Short punchy context" }
  ],
  "edition": "Series branding — e.g. THE NUMBERS — Change of Character",
  "series": "THE NUMBERS",
  "showCaptions": true,
  "captions": [...],
  "voiceover": [...],
  "audioPrefix": "weekly_numbers"
}
```

## FridayCOTStory (6s = 180 frames)
No props. Hardcoded 3-beat: "COT data just dropped." → "Breaking it down Monday." → "BREAKING STRUCTURE. Link attached."

## Brand Constants
- 1080x1920 vertical, 30fps
- bg #0A0A0F, primary #00D4AA, accent #8B5CF6, warning #F59E0B, danger #FF4757
- Inter (headings), JetBrains Mono (data), Space Grotesk (brand)
