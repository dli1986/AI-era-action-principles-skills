# Platform Playbooks Reference

Use this file only when a platform-specific pattern helps the current task.

Keep the main response concise. Do not dump this whole file into the answer.

## Cloud Platforms: AWS / Azure / GCP

High-signal resources:

- official service docs
- getting started guides
- service quotas
- pricing pages and calculators
- identity and access-management docs
- audit logs
- application logs and metrics
- architecture frameworks
- reference architectures
- official samples
- official labs
- official support/community knowledge bases

Expert operating path:

1. Secure the account and set billing/cost controls first.
2. Identify the smallest real workload to deploy.
3. Use official docs and samples before random tutorials.
4. Deploy one tiny but real system.
5. Inspect logs, permissions, cost, quotas, and cleanup steps.
6. Record what each service did and what constraints appeared.

Wrong paths:

- Treating free tiers as unlimited free usage.
- Watching long courses without deploying anything.
- Learning every service by name.
- Skipping identity and permissions.
- Using only the web console forever.
- Ignoring logs, cost, quotas, and cleanup.

## Model / ML Platforms

High-signal resources:

- model card or official model page
- files and versions
- configuration files
- tokenizer or processor files
- official library docs
- fine-tuning docs
- source code
- community discussions
- official examples
- license

Expert operating path:

1. Read the model page for intended use, examples, limitations, and license.
2. Inspect configuration and tokenizer/processor files.
3. Confirm architecture and loading path.
4. Run the smallest real inference example.
5. Inspect module names or extension points if adapting/fine-tuning.
6. Design a tiny overfit or validation experiment before full training.
7. Record model-specific quirks.

Wrong paths:

- Starting from random tutorials.
- Copying AI-generated code without verifying official docs.
- Ignoring tokenizer or processor files.
- Ignoring license.
- Trying large-scale training before a tiny validation test.

## GitHub / Open Source

High-signal resources:

- README
- docs or wiki
- releases and changelog
- closed issues
- merged pull requests
- discussions
- source code
- tests
- CI configuration
- dependency files
- commit history
- contributing guide
- license

Expert operating path:

1. Read README for intent and quickstart.
2. Check releases/changelog for stability and breaking changes.
3. Search closed issues for real-world problems.
4. Read tests as executable documentation.
5. Inspect CI to learn how maintainers run the project.
6. Read merged PRs for design decisions.
7. Run one meaningful sample or test, not only install the repo.
8. Save project-specific notes and known pitfalls.

Wrong paths:

- Judging only by stars.
- Ignoring last release date.
- Ignoring closed issues.
- Ignoring tests.
- Relying only on blogs or Stack Overflow.
- Installing without running a meaningful path.

## Career / Professional Platforms

High-signal resources:

- job alerts
- saved jobs
- company career pages
- hiring manager posts
- recruiter posts
- employee posts
- mutual connections
- company pages
- engineering blogs
- profile/recruiter signals
- job description keyword patterns

Expert operating path:

1. Define target roles and constraints.
2. Create focused alerts.
3. Track hiring posts and company signals.
4. Extract recurring keywords from job descriptions.
5. Build a target-company list.
6. Identify people worth following or contacting.
7. Update profile/resume based on repeated market signals.
8. Persist opportunities in a local database or note system.

Wrong paths:

- Treating professional platforms only as job boards.
- Scrolling feeds without capturing signals.
- Applying to everything.
- Ignoring company career pages.
- Ignoring weak ties and hiring posts.
- Automating risky platform actions.

## Kaggle / Competitions

High-signal resources:

- competition overview
- evaluation metric
- data description
- rules
- discussion threads
- top notebooks
- winning solution writeups
- public/private leaderboard behavior
- exploratory notebooks
- baseline notebooks
- leakage warnings

Expert operating path:

1. Understand the metric before modeling.
2. Read data description and rules.
3. Run a baseline notebook.
4. Study discussions for leakage and pitfalls.
5. Compare top public notebooks with winning writeups.
6. Track validation strategy carefully.
7. Save reusable feature and validation patterns.

Wrong paths:

- Copying top notebooks blindly.
- Optimizing public leaderboard only.
- Ignoring the evaluation metric.
- Ignoring leakage discussions.
- Skipping a simple baseline.

## Social Feeds / Video Platforms

High-signal resources:

- creator credibility
- original source links
- transcripts
- chapters
- comments with technical corrections
- publication date
- repeated references across trusted creators
- bookmarks or saved posts
- lists or subscriptions

Expert operating path:

1. Use social platforms for discovery and first-hand signals.
2. Verify claims against official docs, repos, papers, or source material.
3. Save only actionable or high-signal items.
4. Export useful items into a personal system.
5. Periodically prune noisy sources.

Wrong paths:

- Confusing popularity with correctness.
- Letting recommendation feeds define priorities.
- Watching many tutorials without building.
- Saving links without extracting decisions or actions.
