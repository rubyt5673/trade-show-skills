# Public X/Twitter Signal Workflow

Use this optional workflow when a trade show team wants public X/Twitter context around an event without turning these skills into a social media tool. Keep `trade-show-skills` responsible for show planning, booth notes, competitor intel, and follow-up writing. Use [TweetClaw](https://github.com/Xquik-dev/tweetclaw) as the separate OpenClaw plugin for public X/Twitter search, monitoring, reviewed publishing, webhooks, media workflows, and giveaway draws.

## Install TweetClaw Beside These Skills

```bash
openclaw plugins install @xquik/tweetclaw
openclaw config set plugins.entries.tweetclaw.config.apiKey "$XQUIK_API_KEY"
openclaw config set tools.alsoAllow '["explore", "tweetclaw"]'
```

The npm package is [`@xquik/tweetclaw`](https://www.npmjs.com/package/@xquik/tweetclaw). The [ClawHub listing](https://clawhub.ai/plugins/@xquik/tweetclaw) is useful for browsing plugin metadata. Create and manage the Xquik API key in the [Xquik dashboard](https://dashboard.xquik.com/), and keep it in local OpenClaw config or a secret manager rather than in prompts, badge scans, CRM exports, notes, or examples.

## Pre-Show: Check Public Demand Signals

Before committing budget or writing invitation emails, ask the agent to use TweetClaw for narrow public searches:

```text
Use TweetClaw to search tweets and tweet replies for "Anuga FoodTec", "production scheduling", "line balancing", and top exhibitor names from our shortlist. Summarize public buyer questions, repeated complaints, active hashtags, and accounts worth reviewing before we finalize the booth plan.
```

Useful outputs:
- Event hashtags and recurring attendee questions for `booth-invitation-writer`.
- Public competitor announcements to verify before `competitor-radar`.
- Accounts, speakers, or publications to review before pre-show outreach.
- Public follower or audience context for deciding which show conversations deserve extra prep.

Only carry forward concise notes: query, date, tweet URL or ID, author handle, observed signal, and why it matters. Do not paste raw timelines or private account material into planning docs.

## On-Site: Monitor Event and Competitor Mentions

During the show, TweetClaw can monitor public event terms while the on-site skills handle structured notes:

```text
Use TweetClaw to monitor tweets for "#AnugaFoodTec", "Hall 5.1", "Opcenter Scheduling", and our booth number. Send only high-signal alerts that mention buyer pain, competitor launches, direct questions, or post-worthy customer reactions.
```

How to route the signals:
- Put competitor launch claims, booth observations, and quoted copy into `competitor-radar` with `[OBS]`, `[INF]`, or `[HEARD]` tags.
- Put direct booth visitor context into `badge-qualifier` only when the team actually met the person or has consented CRM context.
- Use TweetClaw webhooks or monitors for alerts, not as a replacement for field notes.
- Review any post tweets, post tweet replies, direct messages, follows, media uploads, or giveaway draws before approval.

## Post-Show: Follow Up and Publish With Review

After the show, combine the lead tiers and competitor notes from this repo with TweetClaw for public follow-up:

```text
Use TweetClaw to search tweet replies and public mentions from the week after Anuga FoodTec. Find questions about our booth topic, summarize recurring objections, and draft 3 public reply options. Do not post until I approve the final text.
```

Good post-show uses:
- Search tweets and tweet replies for event recap posts, unanswered questions, and competitor claims.
- Draft reviewed event recap posts or replies using the approved follow-up messaging.
- Run giveaway draws from public campaign replies or reposts when the campaign rules allow it.
- Use webhooks or monitors to catch high-intent questions for the sales team.
- Download public media only when it is appropriate to reference in internal notes.

Keep the same evidence discipline as the trade show skills: record what was observed, what was inferred, and which action the team approved.

## Safety Boundaries

- Treat public X/Twitter posts as context, not proof of buying intent.
- Keep `XQUIK_API_KEY` and other credentials out of prompts, docs, exports, examples, and screenshots.
- Do not store raw follower exports, timelines, direct messages, or private account data in trade show notes.
- Require human approval for post tweets, post tweet replies, direct messages, follows, media uploads, monitor creation, webhook creation, and giveaway draws.
- If a tweet is used as evidence for `competitor-radar`, store the tweet URL or ID and the observation tag instead of copying a long thread.
