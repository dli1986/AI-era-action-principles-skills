# Safety and Platform Boundaries Reference

Use this file when a task involves third-party platforms, accounts, automation, scraping, social interactions, or financial/account risk.

## General Principle

Prefer:

- official platform features
- official APIs
- exports
- alerts
- saved items
- email notifications
- user-controlled notes
- local databases
- human-in-the-loop actions
- AI-generated recommendations with manual final execution

Avoid recommending:

- account-risky automation
- automated mass engagement
- automated messaging
- automated profile visits
- scraping behind authentication
- platform manipulation
- behavior intended to impersonate human attention or interaction
- bypassing access controls or anti-abuse systems

## Professional / Social Platforms

Prefer:

- official alerts
- manual saved posts
- manual follows/connections
- local opportunity databases
- summarization of user-provided content
- action queues that the user reviews manually

Avoid:

- automated likes
- automated comments
- automated follows/unfollows
- automated connection requests
- automated DMs
- automated profile scraping
- automated feed manipulation

## Cloud / Paid Platforms

Always consider:

- billing alerts
- cost estimates
- free-tier limits
- quotas
- cleanup steps
- least-privilege permissions
- audit logs
- credential hygiene

Do not recommend:

- hardcoding credentials
- using root/admin privileges by default
- leaving paid resources running unintentionally
- skipping cleanup instructions

## Data / ML Platforms

Always consider:

- license
- model/data usage restrictions
- privacy
- personally identifiable information
- dataset provenance
- evaluation leakage
- reproducibility

## Output Pattern

When safety boundaries matter, include a short section:

```markdown
## Risks and Boundaries
- Safe:
- Risky:
- Avoid:
- Human judgment required:
```
