# HOW TO ADD A NEW MATCH — Simple Steps

## The error you saw: "Match not found"
This happens when the file name in your `matches/` folder does NOT exactly match
the matchId in `index.json`. They must be identical.

---

## Step 1 — Create the match JSON file

1. Open `matches/NEW-MATCH-TEMPLATE.json` (included in this folder)
2. Click the pencil icon on GitHub to edit it
3. Change ALL the values (team names, date, venue, result, overs, commentary)
4. At the top, set the matchId like this:
   - Format: `team1-vs-team2-YYYY-MM-DD`
   - Example: `rcb-vs-csk-2026-03-28`
   - Rules: ALL LOWERCASE, hyphens only, no spaces, no capitals
5. Click "Commit changes"
6. Then go to the file → click the 3 dots menu → "Download" or just copy all content
7. In GitHub, click "Add file" → "Create new file"
8. Name the file EXACTLY: `matches/rcb-vs-csk-2026-03-28.json`
   (same as matchId + .json)
9. Paste the content → Commit

---

## Step 2 — Add to index.json

Open `matches/index.json` and add ONE entry inside the `"matches": [...]` array:

```json
{
  "matchId": "rcb-vs-csk-2026-03-28",
  "status": "completed",
  "team1": "RCB",
  "team2": "CSK",
  "date": "2026-03-28",
  "result": "RCB WON BY 10 RUNS",
  "file": "rcb-vs-csk-2026-03-28.json"
}
```

⚠️ IMPORTANT: The `matchId` here must be EXACTLY the same as:
- The `matchId` inside your JSON file
- The filename (without .json)

---

## CHECKLIST before adding a new match

✅ matchId in JSON file = filename (without .json) = matchId in index.json
✅ All lowercase
✅ Hyphens only, no spaces
✅ File is inside the `matches/` folder
✅ JSON is valid — check at https://jsonlint.com
✅ Committed to GitHub (wait 30 seconds for Vercel to redeploy)

---

## Common mistakes

❌ File named `RCB-vs-CSK-2026-03-28.json` (capitals) but matchId is `rcb-vs-csk-2026-03-28`
❌ File is in root folder instead of `matches/` subfolder
❌ Comma missing or extra comma in JSON — use jsonlint.com to check
❌ Forgot to add entry to `index.json`
❌ matchId in JSON doesn't match filename

---

## JSON number rules

CORRECT:   `"runs": 12`      (no quotes around numbers)
WRONG:     `"runs": "12"`    (don't put quotes around numbers)

CORRECT last item:   `{ "over": 20, "runs": 8, "wickets": 0, "bowler": "Name" }`
WRONG last item:     `{ "over": 20, "runs": 8, "wickets": 0, "bowler": "Name" },`  ← extra comma!
