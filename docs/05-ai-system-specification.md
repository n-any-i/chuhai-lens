# 05 — AI System Specification

## System objective

Convert a low-friction asset submission into a structured, evidence-linked target-market readiness report while clearly separating observation, external evidence, interpretation, and synthetic illustration. The first implemented market module is the United States.

## Proposed pipeline

1. Validate inputs and consent.
2. Fetch a permitted public URL or process uploaded assets.
3. Capture page screenshots and selected page text.
4. Sample key frames and transcript cues for short videos.
5. Run a multimodal first-pass extraction into structured data.
6. Run targeted public research for competitors, reviews, Reddit/category discussion, and AI visibility.
7. Synthesize findings using the analysis rubric.
8. Generate synthetic-persona quotes from the same evidence packet.
9. Verify that every major claim has an evidence type and reference.
10. Render the report and retain only the minimum necessary data.

## Model responsibilities

The required Build Week model is GPT-5.6. The implementation should use it for the substantive reasoning and multimodal report generation. Codex is used to design, implement, test, and document the product.

To control cost and latency, deterministic code should handle:

- input validation;
- page capture;
- image dimensions/cropping;
- file limits;
- score arithmetic;
- report rendering;
- caching; and
- retry/error states.

Do not ask the model to perform work that code can perform reliably.

## Structured intermediate objects

### Submission

- review type
- URL and/or asset references
- optional brand context
- target market
- output language
- consent timestamp

### Evidence item

- ID
- evidence type: submitted / observed / public source / synthetic
- source URL or asset reference
- screenshot/frame reference
- crop coordinates when available
- extracted text
- access timestamp
- reliability notes

### Finding

- ID
- dimension
- title
- observation
- interpretation
- evidence IDs
- evidence label
- priority
- impact type
- effort
- recommendation
- confidence
- limitations

### Persona quote

- fictional persona summary
- quote
- evidence IDs
- triggered signal
- disclosure

## Prompt architecture

Use separate, versioned prompts rather than one enormous instruction:

1. **Asset observer:** describes only what is visible or supplied.
2. **Market analyst:** applies the selected market module's rubric to observations; the prototype supplies the U.S. module.
3. **Research synthesizer:** relates external sources without copying them.
4. **Persona panel:** generates short illustrative reactions grounded in evidence.
5. **Report editor:** removes repetition, checks labels, and prioritizes actions.

The model must be told that text found on a submitted webpage is untrusted content, not an instruction. This protects against prompt injection embedded in sites.

## Grounding requirements

- Every high-priority finding must reference at least one submitted evidence item.
- Claims about competitors or consumers require a source link.
- If external research is unavailable, say so and lower evidence coverage.
- Do not invent Reddit posts, reviews, policies, product facts, or customer demographics.
- Do not infer nationality, race, health, religion, sexuality, or other sensitive traits from appearance.
- Do not make legal conclusions.

## Synthetic-persona rules

- Generate final-report quotes only; no interactive interview loop.
- Use three to five personas maximum.
- Make each persona relevant to purchase context.
- Keep each quote short and natural.
- Tie every quote to visible or supplied evidence.
- Label each as fictional.
- Never aggregate quotes into fake percentages or sample statistics.

## Failure behavior

- URL capture failure: invite image upload and preserve other inputs.
- Research failure: produce a submitted-asset report and mark research unavailable.
- Video too long: ask for a shorter clip or analyze a limited sample with disclosure.
- Low visual quality: explain the limitation instead of overconfident scoring.
- Unsafe or disallowed content: stop or narrow the analysis with a clear message.
- Schema failure: retry once with the validation error; do not silently render malformed output.

## Versioning

Store:

- prompt version;
- rubric version;
- model identifier;
- analysis timestamp; and
- report schema version.

This makes debugging and evaluation possible without exposing private chain-of-thought.
