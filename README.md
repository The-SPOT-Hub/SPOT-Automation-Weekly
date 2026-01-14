*Note: The following was written in part by Claude.*

# SPOT Weekly Automation

## What This Is

This repository contains automation that posts when2meet links to the #the-spot Slack channel every Thursday morning. It replaces the manual process of creating when2meet links and posting them to Slack.

**What it does:**
- Generates when2meet links for the agreed upon Launch School courses (see config.py for full list)
- Posts them to #the-spot every Thursday morning at the scheduled time
- Runs automatically via GitHub Actions
- Prevents duplicate posts if the automation runs multiple times

**Who owns this:**
- Repository: SPOT GitHub account
- Slack app: Launch School workspace
- Maintainers: Current SPOT moderators

---

## How It Works

### The Automation Flow

1. **Thursday morning**: GitHub Actions triggers the automation
2. **Script runs**: Python script generates when2meet links and Slack post content
3. **Posts to Slack**: Bot posts to #the-spot channel with threaded replies
4. **Duplicate prevention**: Checks if bot already posted today before running

### Components

```
Automation System
├── GitHub Actions (scheduler)
│   └── Runs Python script every Thursday
├── Python Script
│   ├── Generates when2meet links
│   └── Posts to Slack via API
└── Slack Bot
    └── Has permission to post to #the-spot
```

### File Structure

```
spot-weekly-automation/
├── README.md (this file)
├── .gitignore (keeps secrets out of Git)
├── requirements.txt (Python dependencies)
├── scripts/
│   ├── slack.py (main automation script)
│   ├── w2m.py (w2m automation script)
│   └── config.py (list of courses)
└── .github/
    └── workflows/
        └── weekly_posts.yml (GitHub Actions config)
```

## Version History

- **v1.0** (January 2026): Initial automation system
  - Created by: Karishma Tank
  - GitHub: SPOT account owns repo
  - Slack: LS workspace owns app
