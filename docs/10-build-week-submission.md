# 10 — OpenAI Build Week Submission Plan

## Source of truth

Always re-check the official pages immediately before submitting:

- <https://openai.com/build-week/>
- <https://openai.devpost.com/rules>

This checklist was verified on July 18, 2026. If this document conflicts with the official rules, the official rules win.

## Deadline

**Submission deadline:** July 21, 2026 at 5:00 p.m. Pacific Time / 8:00 p.m. Eastern Time.

Target an internal submission deadline at least six hours earlier. Do not depend on a final-minute deployment, video upload, or Devpost save.

## Required product use

- Build a functional project with Codex and GPT-5.6.
- The project must run consistently on its intended platform.
- It must work as shown in the video and description.
- This project is newly created during the submission period; preserve dated Codex work and Git commit history.

## Recommended category

**Work & Productivity**

Reason: Chuhai Lens helps founders and ecommerce teams make better market-entry and marketing decisions. It is a business workflow product, not primarily a developer tool or consumer-lifestyle app.

## Required submission materials

- [ ] Join/register for the challenge on Devpost.
- [ ] Complete every required Devpost project field.
- [ ] Choose Work & Productivity.
- [ ] English project description explaining features and functionality.
- [ ] Publicly visible YouTube demo video with audio, shorter than three minutes.
- [ ] Video clearly shows what was built and how Codex and GPT-5.6 were used.
- [ ] Video avoids unauthorized trademarks, copyrighted music, or third-party material.
- [ ] Code-repository URL.
- [ ] Repository is public with a relevant license, or private and shared with both required judging addresses.
- [ ] README explains collaboration with Codex, key human decisions, and how GPT-5.6 and Codex contributed.
- [ ] `/feedback` Codex Session ID for the task where most core functionality was built.
- [ ] Free working website/demo or test build available to judges.
- [ ] English testing instructions and credentials if any private access exists.
- [ ] Demo remains free and unrestricted until the judging period ends.

## Repository choice

Recommended for this prototype: a public repository after secret scanning and license review.

Before creating it:

1. confirm `.gitignore` protects local secrets;
2. verify `.env.example` contains placeholders only;
3. search the entire folder for key-like strings;
4. choose a license deliberately;
5. initialize Git and create the first dated commit; and
6. then prompt the owner to create `n-any-i/chuhai-lens` and authorize only that repository.

Do not create or connect the personal repository without the owner's confirmation at that stage.

## Live demo requirement

Submit the hosted web prototype, not a Codex project file. Codex is the tool used to build it; Devpost receives:

- the live demo URL;
- the code repository;
- the public YouTube video;
- the description and images; and
- the Codex Session ID.

A custom domain is not required.

## Judge-first demo path

The public site should offer:

1. a clear promise on the landing page;
2. a one-click sample report;
3. a live URL/image analysis path;
4. visible evidence-linked advice;
5. synthetic-persona disclosures; and
6. a concise explanation of GPT-5.6 and Codex use.

No sign-up, payment, browser extension, or local installation should be required.

## Video outline — maximum 2:40 target

### 0:00–0:20 — Problem

Businesses entering unfamiliar foreign markets can launch polished brands that still feel subtly wrong to local customers, and early-stage teams cannot always hire local agencies. Chuhai Lens demonstrates the global idea through its first focused China-to-U.S. use case.

### 0:20–0:35 — Product

Introduce Chuhai Lens and show the low-friction URL/image input.

### 0:35–1:35 — Live journey

- choose an asset type;
- submit the demo asset;
- show progress;
- reveal score, first-scan verdict, and annotated evidence;
- show commerce expectations and prioritized fixes; and
- show clearly labeled synthetic-persona quotes.

### 1:35–2:05 — Technical substance

Explain GPT-5.6 multimodal reasoning, structured evidence objects, secure server-side API calls, source research, and visual crop references.

### 2:05–2:30 — Codex collaboration

Show dated project documents, key decisions, code/test work, and where Codex accelerated implementation while the founder set product and ethical direction.

### 2:30–2:40 — Impact

End with the target user and the decision the product helps them make.

## Judging alignment

### Technological implementation

- working multimodal GPT-5.6 analysis;
- structured evidence and report schema;
- URL/image/video handling;
- public research integration;
- safety, cost, and failure controls; and
- documented Codex collaboration.

### Design

- complete no-login journey;
- coherent input, progress, and report experience;
- visual evidence embedded in findings; and
- clear disclosures and graceful errors.

### Potential impact

- specific underserved users;
- costly real-world market-entry mistakes;
- actionable output before agency-level spending; and
- a path from prototype to consultant/team workflow.

### Quality of idea

- focuses on the subtle gap between translation and market fit;
- combines visual, operational, evidence, AI-visibility, and synthetic perspectives; and
- frames origin ethically rather than teaching brands to impersonate local companies.

## Final 12-hour checklist

- [ ] Freeze non-essential features.
- [ ] Run the full test matrix.
- [ ] Confirm the deployed model is GPT-5.6.
- [ ] Confirm the public URL works in a signed-out browser.
- [ ] Confirm sample mode works if live analysis is unavailable.
- [ ] Check mobile layout.
- [ ] Check no API key appears in source, browser network responses, logs, Git history, or video.
- [ ] Record and upload the video early.
- [ ] Verify YouTube is public.
- [ ] Verify repository access and README.
- [ ] Obtain and save the `/feedback` Session ID.
- [ ] Submit a Devpost draft, reopen it, and verify every link.
- [ ] Submit before the internal deadline and save confirmation evidence.
