# Video Data Schemas

Each composition in bs-video/ accepts a JSON file. CC generates these JSONs. Windows box renders via `render.sh <composition> <json-path>`.

## RelayReel (15s)
```json
{ "week": "string", "stages": [{ "name": "Bonds", "arrow": "↑|↗|→|↓", "headline": "string", "detail": "string" }], "thesis": "string", "showCaptions": true, "captions": [{ "text": "string", "highlights": ["word"], "startTime": 0, "endTime": 1.5 }] }
```

## COTDataReveal (20s)
```json
{ "hook": "string", "subhook": "string", "rows": [{ "date": "string", "value": "string", "change": "string", "story": "string" }], "insight": "string", "columnHeaders": ["Date","Position","Change","Story"], "showCaptions": true, "captions": [...] }
```

## ExitLiquidityHook (15s)
```json
{ "hook": "string", "retailSide": { "label": "RETAIL", "action": "string", "emotion": "string" }, "institutionalSide": { "label": "INSTITUTIONS", "action": "string", "data": "string" }, "result": "string", "punchline": "string", "showCaptions": true, "captions": [...] }
```

## StructureEducation (25s)
```json
{ "concept": "string", "definition": "string", "steps": [{ "label": "string", "detail": "string" }], "cotConfirmation": "string", "takeaway": "string", "showCaptions": true, "captions": [...] }
```

## WeeklyNumbers (12s)
```json
{ "numbers": [{ "value": "string", "label": "string", "context": "string" }], "edition": "string" }
```

## FridayCOTStory (6s)
No props. Hardcoded 3-beat: "COT data drops today." → "Monday's Breaking Structure breaks it down." → "BREAKING STRUCTURE. Link attached."

## Brand Constants
- Resolution: 1080x1920 (vertical), FPS: 30
- Colors: bg #0A0A0F, primary #00D4AA, accent #8B5CF6, warning #F59E0B, danger #FF4757
- Fonts: Inter (headings), JetBrains Mono (data), Space Grotesk (brand)
