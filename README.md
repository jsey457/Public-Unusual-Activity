# Kalshi Flow — Unusual Activity Detector

Live Kalshi trade flow monitor. No API key needed — uses Kalshi's public API directly.

## Deploy to GitHub Pages (free, ~3 minutes)

### Step 1 — Create a GitHub repo

1. Go to [github.com](https://github.com) → click **+** → **New repository**
2. Name it `kalshi-flow`
3. Set to **Public** ← important, GitHub Pages requires this on free accounts
4. Click **Create repository**

### Step 2 — Upload the file

1. In your new repo, click **uploading an existing file**
2. Drag and drop `index.html`
3. Click **Commit changes**

### Step 3 — Enable GitHub Pages

1. In your repo, click **Settings**
2. Scroll down to **Pages** in the left sidebar
3. Under **Branch**, select `main` and folder `/root`
4. Click **Save**

### Step 4 — Get your URL

After ~60 seconds, your site is live at:
```
https://YOUR-GITHUB-USERNAME.github.io/kalshi-flow
```

Bookmark it. Done.

---

## How it works

- Calls `https://api.elections.kalshi.com/trade-api/v2/markets/trades` directly
- No API key, no proxy, no backend — 100% browser-side
- Polls every 15 seconds
- Detects 6 behavioral signals using only public trade fields

## Signals

| Signal | Trigger |
|--------|---------|
| ⚡ Burst | 3+ fills same market within 60s |
| 🎯 Round # | 100, 250, 500, 1000 contracts |
| 📊 Vol Spike | Trade is 3× that market's rolling average |
| 💥 Price Impact | Single trade moved price 3¢+ |
| ⚖️ Imbalance | 80%+ same side in last 10 trades |
| 🌙 Off-Hours | Large trade outside 9am–5pm ET |
