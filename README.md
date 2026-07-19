# Calorie-Cal

A calorie & macro calculator built for personal training and nutrition coaching clients. Pick a BMR formula, enter a client's stats, and get an instant daily calorie target with a full protein/carb/fat breakdown — no install, no build step, runs entirely in the browser.

**Live demo:** _add your GitHub Pages link here once it's deployed, e.g. `https://<your-username>.github.io/Calorie-Cal/`_

![Calorie-Cal screenshot](screenshot.png)
_(add a screenshot here — see "Adding a screenshot" below)_

---

## Features

- **Three BMR formulas, your choice:**
  - **Mifflin-St Jeor** — the modern default, accurate for most clients
  - **Katch-McArdle** — more accurate for lean/athletic clients, requires body fat %
  - **Harris-Benedict** — the revised (1984) equation, still widely used and requested by some clients/coaches
- Activity-level multipliers (sedentary → extremely active) to get from BMR to TDEE
- Optional extra training calories on top of activity level
- Goal-based adjustment: fat loss / maintenance / muscle gain, with adjustable intensity
- Adjustable protein (g/kg bodyweight) and fat (% of calories) targets — carbs fill the remainder
- Compares a client's current intake against their calculated target
- Save/load multiple client profiles, stored locally in your browser
- Clean, print-friendly "client facts" style output you can screenshot or read straight off screen in a session

## Formulas used

**Mifflin-St Jeor**
```
Men:   BMR = 10×weight(kg) + 6.25×height(cm) − 5×age + 5
Women: BMR = 10×weight(kg) + 6.25×height(cm) − 5×age − 161
```

**Katch-McArdle** (requires body fat %)
```
Lean body mass = weight(kg) × (1 − bodyFat%/100)
BMR = 370 + 21.6 × lean body mass
```

**Harris-Benedict** (revised, 1984)
```
Men:   BMR = 88.362 + 13.397×weight(kg) + 4.799×height(cm) − 5.677×age
Women: BMR = 447.593 + 9.247×weight(kg) + 3.098×height(cm) − 4.33×age
```

If Katch-McArdle is selected but no body fat % is entered, the calculator temporarily falls back to Mifflin-St Jeor and flags this on screen, so you're never looking at a silently wrong number.

## Using it

### Option 1 — just open it
Download `index.html` and double-click it. It opens in your default browser and works immediately, fully offline capable (aside from loading fonts/styling from a CDN on first load).

### Option 2 — host it on GitHub Pages (recommended)
1. Upload `index.html` to this repo (already done if you're reading this on GitHub).
2. Go to **Settings → Pages**.
3. Under "Build and deployment," set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`. Save.
4. Wait a minute or two — your live link will appear at the top of that Pages settings screen, in the form:
   `https://<your-username>.github.io/Calorie-Cal/`
5. Share that link with anyone. It works on any device with a browser, no login, no install.

### Option 3 — command line
```bash
git init
git add index.html README.md
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<your-username>/Calorie-Cal.git
git push -u origin main
```
Then follow steps 2–4 above to enable Pages.

## Adding a screenshot

Take a screenshot of the calculator with a sample client filled in, save it as `screenshot.png` in this repo's root, and it'll automatically render at the top of this README on GitHub.

## Data & privacy

Client data entered into the calculator is saved only in **that visitor's own browser** (localStorage) — it is never sent to a server, never shared between devices, and not visible to anyone but the person using that browser. If you fill it in on your laptop, it stays on your laptop; if a client fills it in on their phone, it stays on their phone.

If you eventually want one shared client list visible only to you (e.g. logging in and seeing every client's data from any device), that requires an actual backend/database — a bigger step beyond this static tool.

## Notes for coaches

Macro presets (protein g/kg, fat %) are sensible defaults, not clinical prescriptions — apply your own professional judgment per client. This is a calculation tool, not a substitute for individualized coaching assessment. Re-assess targets every 2–4 weeks against real-world client progress.

## License

MIT
