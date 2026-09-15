# Daily Briefing

A simple static display page for a daily briefing (date & weather for Kashiwa/Chiba, top news, AI/tech industry watch).

Paired with a Claude Code scheduled routine that searches the web and generates the briefing content every day at 6:00 AM JST, writing it to `data/briefings.json` and pushing straight to `main`. The page shows today's briefing plus a rolling 3-day history.

Live page: https://simonwillker.github.io/daily-briefing/

## Content data

`data/briefings.json` holds the briefing history, newest entry first:

```json
{
  "entries": [
    {
      "date": "2026-09-15",
      "weather": { "high": 28, "low": 21, "condition": "晴れ時々曇り", "note": "湿度やや高め" },
      "news": ["headline 1", "headline 2", "headline 3"],
      "ai": ["AI/tech item 1", "AI/tech item 2"]
    }
  ]
}
```

`index.html` fetches this file at load time, renders `entries[0]` as today's briefing, and `entries[1..3]` as the "過去3日間" history section. The file keeps roughly the last 14 days; only the most recent 3 prior days are shown on the page.

## Deploying on Render

This repo includes a `render.yaml` Blueprint that deploys the site as a static
site on Render, auto-deploying on every push to the connected branch.

1. In the Render Dashboard, go to **New > Blueprint**.
2. Connect this GitHub repository and select the branch to deploy.
3. Render detects `render.yaml` and creates a `daily-briefing` static site.
4. Click **Apply** to deploy. Future pushes will redeploy automatically.
