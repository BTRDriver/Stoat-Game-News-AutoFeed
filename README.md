# Stoat Game News AutoFeed

Free GitHub Action that posts official Steam news into a Stoat channel.

No RSS.app, no paid Zapier/Make, no third-party bot permissions. One workflow per game. Webhook URLs stay in GitHub secrets.

**Games included**
- Escape from Tarkov (`tarkov-news.yml`, app `3932890`)
- DayZ (`dayz_news.yml`, app `221100`)
- Nuclear Option (`nuclear_option_news.yml`, app `2168680`)

## What you need
- A Stoat server and a channel per game (or one shared channel)
- A GitHub account
- The game’s Steam App ID from [steamdb.info](https://steamdb.info)

## Setup

### 1. Create a Stoat webhook
Channel settings → Webhooks → New → copy the full URL.

Enable **Masquerade** on that webhook if you want a custom name and avatar.

### 2. Fork or copy this repo
Public repos are fine. Keep the files under `.github/workflows/`.

### 3. Add secrets
Repo → **Settings → Secrets and variables → Actions → New repository secret**.

| Secret name | Value |
|---|---|
| `STOAT_WEBHOOK` | Tarkov channel webhook URL |
| `STOAT_WEBHOOK_DAYZ` | DayZ channel webhook URL |
| `STOAT_WEBHOOK_NUCLEAR` | Nuclear Option channel webhook URL |

Same channel for every game? Use one secret and change each workflow’s env line to:

```yaml
STOAT_WEBHOOK: ${{ secrets.STOAT_WEBHOOK }}
