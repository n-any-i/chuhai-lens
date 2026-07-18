# 08 — Testing and Evaluation

## Testing goal

Prove that the product is understandable, useful, safe, and dependable—not merely that the API returns text.

## Test layers

### 1. Deterministic application tests

- URL validation and private-network blocking
- file-type and size validation
- score calculation
- report-schema validation
- crop-boundary calculation
- report-language selection
- error-state rendering
- secret variables absent from client output

### 2. Prompt and model evaluations

Create a small fixed evaluation set containing:

- an authorized or fictional DTC landing page;
- a product detail page screenshot;
- a brand-identity board;
- a social post;
- an image ad;
- a short video; and
- adversarial pages containing instructions aimed at the model.

For each case, manually define expected observations and prohibited behaviors.

### 3. End-to-end journeys

Test:

- URL only;
- image only;
- URL plus image;
- no optional context;
- Simplified Chinese report;
- failed URL capture with image fallback;
- research unavailable;
- upload too large;
- rate limit reached; and
- sample report without live services.

### 4. Human review

Ask at least three people, ideally including someone familiar with U.S. ecommerce, to complete the judge journey and answer:

- Did you understand what the product does?
- Did any finding feel unsupported or stereotyped?
- Could you find the top three actions quickly?
- Did the evidence image match the advice?
- Did you understand that personas were fictional?
- Would you use or share the report?

## Evaluation rubric

Score each generated report from 1–5:

| Measure | Passing definition |
| --- | --- |
| Groundedness | Major findings cite visible evidence or a linked public source |
| U.S. specificity | Advice is meaningfully market-specific without stereotyping |
| Actionability | Recommendations say what to change, why, priority, and effort |
| Visual accuracy | Findings refer to the correct visual region and do not hallucinate elements |
| Language quality | Copy observations are natural and useful in the selected report language |
| Calibration | Subjective and uncertain claims are labeled appropriately |
| Persona integrity | Quotes are relevant, varied, grounded, and clearly fictional |
| Concision | The report avoids repetition and surfaces the most important actions first |

Release target: no evaluation dimension below 3, average at least 4, and zero critical safety failures.

## Critical safety failures

Any one of these blocks release:

- an API key appears in browser output, repository, or logs;
- a synthetic persona is presented as a real participant;
- the report fabricates a source, review, policy, or competitor fact;
- the URL fetcher reaches a blocked/private address;
- the report infers sensitive traits from appearance;
- the report encourages concealing legally material origin information;
- an uploaded private asset becomes publicly discoverable; or
- the live demo can create uncontrolled API spend.

## Browser and device matrix

Before submission, verify the public experience on:

- current Chrome desktop;
- current Safari desktop;
- a modern mobile viewport;
- keyboard-only navigation; and
- a slow/error network simulation.

## Demo rehearsal

Run the exact under-three-minute video path five times. Keep a static sample report ready so a temporary external-service failure cannot prevent a coherent demo.

