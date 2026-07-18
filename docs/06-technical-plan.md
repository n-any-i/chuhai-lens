# 06 — Technical Plan

## Build goal

Deliver a public, mobile-friendly web prototype that a non-technical user or judge can open without an account, run with a URL or image, and receive a coherent evidence-led report.

## Recommended baseline

- **Application:** Next.js with TypeScript
- **Interface:** React with a small, accessible component system
- **Styling:** CSS variables plus a lightweight utility or component layer
- **AI:** OpenAI Responses API using the required GPT-5.6 model
- **Hosting default:** Vercel free tier for the prototype
- **Source control:** personal GitHub repository under `n-any-i`
- **Accounts:** none for the Build Week version
- **Payments:** none

This stack is conventional, judge-friendly, and easy for future developers to understand. The design remains portable to Netlify, Cloudflare, or another Node-compatible host.

## Architecture

```text
User browser
  ├─ submits URL/images/video and optional context
  └─ renders progress and report
          │
          ▼
Next.js server endpoints
  ├─ validate URL and files
  ├─ capture permitted public content
  ├─ prepare screenshots, crops, text, and video frames
  ├─ call public research adapter
  ├─ call OpenAI with structured schemas
  ├─ validate and prioritize findings
  └─ return report data
          │
          ├─ OpenAI API (server-side key only)
          ├─ page-capture adapter
          └─ public research/search adapter
```

## Portability rules

- Read secrets through environment variables, especially `OPENAI_API_KEY`.
- Do not import a host-specific SDK into core analysis logic.
- Wrap page capture, storage, and research behind small adapters.
- Keep report data in a documented JSON schema.
- Use standard Node/HTTP interfaces where possible.
- Treat a custom domain as a DNS setting, not an application dependency.

Changing hosting later should require replacing deployment configuration and re-entering secrets—not rewriting the product.

## Prototype implementation slices

### Slice 1: Judgeable shell

- landing page;
- review-type selection;
- URL/image inputs;
- optional context;
- sample report;
- responsive report layout; and
- all disclosures.

Use deterministic fixture data so the complete experience can be tested before the live model connection.

### Slice 2: Live image analysis

- secure image upload;
- multimodal observation;
- structured finding generation;
- dimension scores; and
- evidence references.

This is the most reliable live path and should work before URL or video capture.

### Slice 3: URL analysis

- URL safety validation;
- public page capture;
- screenshot and readable-text extraction;
- relevant crops; and
- graceful image-upload fallback.

### Slice 4: Research and AI visibility

- targeted competitor/category search;
- public Reddit/review evidence when permitted;
- source links and access dates; and
- a lightweight entity/AI-visibility snapshot.

### Slice 5: Short video

- strict file and duration limits;
- selected key frames;
- transcript or audio cues where supported;
- clear sampling disclosure; and
- cost/timeout safeguards.

If time becomes constrained, video remains visible as an honest limited beta rather than compromising the image and URL journeys.

## Data strategy

The simplest safe prototype does not require a database:

- process one analysis request;
- return the report to the browser;
- allow print/save as PDF;
- maintain a static fictional demo report; and
- discard uploaded content after the request or short operational window.

A database or object store is added only if persistent share links become essential. If added, use unguessable IDs, expiration, deletion, and explicit user notice.

## Evidence images

Store each source screenshot or frame with dimensions. Findings reference:

- source asset ID;
- optional crop rectangle `(x, y, width, height)`;
- optional numbered marker; and
- alt text.

The server produces crops or the browser renders overlays. The report never relies on the model to redraw the source.

## API boundaries

Suggested server endpoints:

- `POST /api/analyze` — validate and start one analysis
- `GET /api/demo-report` — return static demo data
- `GET /api/health` — minimal deployment check

Persistent asynchronous jobs may be added only if processing cannot complete within hosting limits. Avoid queues for the first working slice.

## Error handling

- Never show raw stack traces or model responses to users.
- Assign a non-sensitive request ID to failures.
- Preserve successful partial stages.
- Provide an image-upload fallback when URL capture fails.
- Show retry guidance without charging repeatedly for identical cached work.

## Definition of done

- A judge can open the public URL without an account.
- The sample report always works.
- At least the image-analysis path is live and uses GPT-5.6.
- URL analysis works for the controlled demo and common public pages.
- The report includes visual references and synthetic-persona disclosures.
- No key or private test data appears in the browser bundle or repository.
- The deployed version matches the submitted video.

