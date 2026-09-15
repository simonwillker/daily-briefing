# Daily Briefing

A simple static display page for a daily briefing (date & weather for Kashiwa/Chiba, top news, AI/tech industry watch).

Paired with a Claude Code scheduled routine that generates the briefing content every day at 8:00 AM JST.

Live page: https://simonwillker.github.io/daily-briefing/

## Deploying on Render

This repo includes a `render.yaml` Blueprint that deploys the site as a static
site on Render, auto-deploying on every push to the connected branch.

1. In the Render Dashboard, go to **New > Blueprint**.
2. Connect this GitHub repository and select the branch to deploy.
3. Render detects `render.yaml` and creates a `daily-briefing` static site.
4. Click **Apply** to deploy. Future pushes will redeploy automatically.
