# Stoat Game News AutoFeed
This is a project to autofeed Gaming news to a Stoat Server. 

Free GitHub Action that posts official Steam news into a Stoat channel. No RSS, no paid bots.What you needA Stoat server + channel
A GitHub account
The game’s Steam App ID steamdb.info

1. Create the webhookIn the Stoat channel → settings → Webhooks → New. Copy the full URL.
Give the webhook Masquerade if you want a custom name/avatar.

2. Put the workflows in a repoCreate a repo (public is fine). Add:.github/workflows/tarkov-news.yml
.github/workflows/dayz-news.yml

Use the files from this project. One workflow per game.

3. Add secretsRepo → Settings → Secrets and variables → Actions → New repository secretSecret name
What to paste
STOAT_WEBHOOK
Tarkov channel webhook URL
STOAT_WEBHOOK_DAYZ
DayZ channel webhook URL

Same channel for both games? Use one secret and point both ymls at ${{ secrets.STOAT_WEBHOOK }}.Never put the webhook URL in the yml.

4. Run itActions → pick the workflow → Run workflow.First run posts the latest English item only, then checks about every 20 minutes.

