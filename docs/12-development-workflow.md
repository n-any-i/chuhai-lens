# 12 — Development Workflow

## Purpose

This workflow lets a non-technical owner see what changed, why it changed, how it was tested, and how to recover when something breaks.

## Where project knowledge lives

- `README.md` — project entry point and document map
- `AGENTS.md` — durable rules Codex must follow in this folder
- `docs/01–10` — product, system, and submission specifications
- `docs/11-decision-log.md` — approved choices and pending owner decisions
- `CHANGELOG.md` — completed material changes by date
- Git commit history — exact file-level history after repository initialization
- Codex task — discussion, reasoning, approvals, and live debugging

No single chat message is the only record of an important product decision.

## Build loop

For each implementation slice:

1. **Define:** identify the user outcome and source specification.
2. **Plan:** list the smallest files and behaviors that must change.
3. **Build:** implement one coherent slice.
4. **Verify:** run automated tests and the affected browser journey.
5. **Review:** show the owner the working result and material tradeoffs.
6. **Record:** update decision log or changelog when appropriate.
7. **Commit:** save a clear Git checkpoint once Git is connected.

## Recommended implementation order

### Phase A — Product shell

- landing page and visual direction;
- review-type selection;
- URL/image inputs and optional context;
- report-language control;
- consent/disclosures;
- static fictional demo report; and
- responsive report layout.

### Phase B — Live image path

- server-only OpenAI connection;
- upload validation;
- GPT-5.6 structured observation and findings;
- scoring; and
- live report rendering.

### Phase C — Visual evidence

- source image references;
- markers/crops;
- evidence cards; and
- visual accuracy tests.

### Phase D — URL and research

- secure public-URL capture;
- screenshot/text extraction;
- competitor and public-conversation evidence;
- lightweight AI visibility; and
- partial-failure behavior.

### Phase E — Video beta

- short-video limits;
- key-frame sampling;
- transcript/audio cues where supported;
- cost controls; and
- explicit sampling limitations.

### Phase F — Submission hardening

- cross-browser checks;
- rate limits and kill switch;
- deployment;
- README collaboration narrative;
- GitHub repository;
- demo video; and
- Devpost submission.

## Bug report template

When something fails, record:

```text
Title:
Date/time:
Environment: local / preview / production
What I was trying to do:
Exact steps to reproduce:
Expected result:
Actual result:
Screenshot or request ID:
Does it happen every time?:
Last known working version:
```

Never paste API keys, authorization headers, private uploaded content, or full sensitive logs into a bug report.

## Debugging loop

1. Reproduce the smallest failing case.
2. Check the last working checkpoint and recent changes.
3. Inspect sanitized browser/server evidence.
4. Form one concrete cause hypothesis.
5. Make the smallest safe fix.
6. Add a test that would have caught the bug.
7. Re-run the original journey and nearby regression tests.
8. Record the fix in the changelog if users or architecture are affected.

## Git checkpoints

After the repository is created, commit at meaningful milestones such as:

- `docs: define Chuhai Lens product and safety boundaries`
- `feat: add no-login analysis intake flow`
- `feat: generate structured image analysis report`
- `feat: link findings to visual evidence`
- `test: cover URL and upload security boundaries`
- `chore: prepare Build Week submission`

Do not bundle unrelated changes into one large final commit.

## Moving the folder later

After submission, the entire folder may be moved. First:

1. commit and push all intended changes;
2. stop the development server;
3. move the whole folder, including hidden `.git` and `.env.local` files;
4. open the new folder location in a new Codex task; and
5. verify Git status, local secrets, and the development command.

The GitHub repository, deployment, and domain do not depend on the laptop folder path.

