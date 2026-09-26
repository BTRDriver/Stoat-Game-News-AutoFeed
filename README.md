# Stoat Game News AutoFeed

Free GitHub Action that posts official Steam news into a Stoat channel.

No RSS.app, no paid Zapier/Make, no third-party bot permissions. One workflow per game. Webhook URLs stay in GitHub secrets.

## Games included

| Game | Workflow | Steam App ID | Secret |
|---|---|---|---|
| Escape from Tarkov | `tarkov-news.yml` | `3932890` | `STOAT_WEBHOOK_EFT` |
| DayZ | `dayz_news.yml` | `221100` | `STOAT_WEBHOOK_DAYZ` |
| Nuclear Option | `nuclear_option_news.yml` | `2168680` | `STOAT_WEBHOOK_NUCLEAR` |
| ARC Raiders | `arc_raiders_news.yml` | `1808500` | `STOAT_WEBHOOK_ARC` |
| Halo: The Master Chief Collection | `halo_mcc_news.yml` | `976730` | `STOAT_WEBHOOK_MCC` |
| Valheim | `valheim_news.yml` | `892970` | `STOAT_WEBHOOK_VALHEIM` |
| WARDOGS | `wardogs_news.yml` | `1867240` | `STOAT_WEBHOOK_WARDOGS` |
| Active Matter | `active_matter_news.yml` | `2887580` | `STOAT_WEBHOOK_ACTIVEMATTER` |
| Project Zomboid | `project_zomboid_news.yml` | `108600` | `STOAT_WEBHOOK_PZ` |
| Helldivers 2 | `helldivers2_news.yml` | `553850` | `STOAT_WEBHOOK_HD2` |

## What you need
- A Stoat server and a channel per game (or one shared channel)
- A GitHub account
- The game’s Steam App ID from [steamdb.info](https://steamdb.info)

## Setup

### 1. Create a Stoat webhook
Channel settings → Webhooks → New → copy the full URL.

Name it something like `Tarkov News` / `WARDOGS News`. Enable **Masquerade** if you want the custom name and avatar from the workflow.

### 2. Fork or copy this repo
Public repos are fine. Keep the files under `.github/workflows/`.

### 3. Add secrets
Repo → **Settings → Secrets and variables → Actions → New repository secret**.

Use the secret names in the table above. Value = that game’s webhook URL.

Same channel for every game? Use one secret and point each workflow at:

```yaml
STOAT_WEBHOOK: ${{ secrets.STOAT_WEBHOOK }}
