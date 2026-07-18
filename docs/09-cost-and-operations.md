# 09 — Cost and Operations

## Who pays

For the public prototype, the project owner's OpenAI API project pays for analyses. Test users do not use their ChatGPT subscription or personal credits merely by visiting the site.

The promotional Build Week credits are for building and testing the project and expire according to the challenge terms. They are not a permanent pool for future public users.

## Cost objective

Design for useful bounded analysis rather than maximum context. Initial operating targets:

- image or single-page analysis: comfortably below $1 per successful report;
- URL plus limited research: approximately $1 or less where possible;
- short video: explicitly capped and allowed to cost more;
- sample report: no live-model cost; and
- daily public-demo maximum: set by a hard request budget.

These are product budgets, not price guarantees. Before launch, calculate estimates using the then-current GPT-5.6 pricing and observed token/image usage from test runs.

## Cost components

Track each separately:

- input text tokens;
- image or video-frame inputs;
- model reasoning/output tokens;
- retries and failed schema calls;
- page capture;
- search/research service;
- temporary storage; and
- hosting bandwidth/function time.

## Cost-control design

- Resize images while preserving readable detail.
- Use a limited number of page screenshots and video frames.
- Extract only relevant page text.
- Run narrow research queries instead of broad repeated searches.
- Produce structured findings once, then render them without another model call where possible.
- Cap output length and persona count.
- Retry only validation failures and at most once by default.
- Cache the fictional demo and approved repeat test fixtures.
- Prevent duplicate button submissions.

## Prototype public limits

Initial recommendation:

- one active analysis per browser session;
- a small per-IP daily allowance;
- maximum five images or carousel slides;
- short video only, with a visibly stated duration limit;
- one target market; and
- no background batch processing.

When the daily global budget is reached, switch to sample-report mode with an honest message.

## Measurement

For every test analysis, record sanitized metrics:

- review type;
- asset count and dimensions/duration;
- stage latency;
- model input/output usage;
- estimated API cost;
- external-service cost;
- success or failure; and
- cache status.

Use the median and 90th percentile—not one best-case run—to set public limits.

## Hosting and domain costs

- A custom domain is optional for Build Week.
- A reputable provider subdomain is acceptable for judging.
- Start with a free hosting tier, but confirm function duration and bandwidth limits.
- A domain can be connected later without changing the GitHub repository or application architecture.
- Hosting secrets are re-entered in the provider dashboard when migrating.

## Operational checklist

- project-scoped OpenAI API key;
- platform spending limit and alerts;
- application rate limit;
- daily global kill switch;
- health check;
- sanitized error logging;
- sample-report fallback;
- documented rollback to last working deployment; and
- keep the public demo free and available through the judging period.

