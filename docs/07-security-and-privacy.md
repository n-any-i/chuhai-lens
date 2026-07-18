# 07 — Security and Privacy

## Security promise

Users may submit unreleased brand materials. The prototype must minimize collection, keep secrets server-side, and explain its limitations plainly.

## API-key protection

### Local development

- Real keys belong only in `.env.local`.
- `.env.local`, `.env`, and environment-specific secret files are ignored by Git.
- `.env.example` contains blank variable names only.
- Keys must never appear in Markdown, screenshots, issue text, prompts, test fixtures, browser code, or logs.

### Hosting

- Store `OPENAI_API_KEY` in the host's encrypted environment-variable dashboard.
- Read it only inside server code.
- Never prefix it with a public/client environment marker.
- Never send it to the browser or include it in API responses.

### Migration

When changing hosts:

1. deploy the same code to the new host;
2. enter the key in the new host's secret dashboard;
3. test the new deployment;
4. remove the secret from the old host; and
5. rotate the key if the old host or access history is uncertain.

The repository remains unchanged.

### If a key is exposed

1. Revoke it immediately in the OpenAI platform.
2. Create a replacement project-scoped key.
3. Remove the secret from Git history, logs, screenshots, and deployment variables.
4. Review usage for unexpected activity.
5. Redeploy and test.

Deleting the visible line from the latest commit is not sufficient because Git history retains it.

## Public-trial cost controls

The product owner pays API usage for public analyses. Users do not supply or “burn” their own OpenAI credits in the prototype.

Required controls:

- per-IP and per-session rate limits;
- daily global request budget;
- file and video limits;
- model token/output ceilings;
- request timeout;
- duplicate-input caching where privacy permits;
- disabled or sample-only mode when the daily budget is reached; and
- spending alerts and project budget in the OpenAI platform.

## URL-fetch protection

User-provided URLs can attack a server. Before fetching:

- allow only `http` and `https`;
- block localhost, private, link-local, metadata, and reserved network ranges;
- resolve and re-check DNS targets;
- limit redirects and revalidate every redirect;
- impose response-size and time limits;
- reject authenticated/internal pages;
- do not execute downloaded files; and
- treat page content as untrusted data, never as instructions.

Respect access restrictions and do not bypass paywalls, logins, CAPTCHAs, or robots controls.

## Upload protection

- Permit only documented image/video types.
- Verify actual file signatures rather than trusting filenames.
- Rename files with generated IDs.
- Apply strict size, pixel, duration, and frame-count limits.
- Never make uploads publicly listable.
- Delete temporary files after processing or a clearly stated short retention period.
- Do not use submitted assets for unrelated model improvement.

## Privacy behavior

The upload notice must explain:

- what is sent to AI services;
- why it is processed;
- whether it is retained and for how long;
- that users should not upload secrets, personal data, or assets they lack permission to use; and
- how to request deletion if persistence is later introduced.

The Build Week version should avoid user accounts, analytics profiles, and long-term report storage.

## Logging

Log only what is needed to debug:

- request ID;
- timestamps and stage durations;
- model/prompt/schema versions;
- token/usage totals;
- success/failure category; and
- sanitized error code.

Do not log:

- API keys;
- full prompts containing user assets;
- uploaded file contents;
- full report content by default;
- authorization headers; or
- unnecessary URLs with sensitive query parameters.

## Public-source and IP safety

- Link to sources and use short excerpts or paraphrases.
- Do not republish full reviews, articles, or competitor creative.
- Use an authorized or fictional brand for the public demo.
- Remove unrelated personal information from screenshots.
- Do not make defamatory claims about the submitted or competitor brand.

## Product disclaimers

- Directional AI-assisted analysis, not representative consumer research.
- Synthetic personas are fictional.
- Not legal, customs, tax, accessibility-compliance, or regulatory advice.
- Users remain responsible for verifying recommendations before acting.

