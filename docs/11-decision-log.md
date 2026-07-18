# 11 — Decision Log

This file records product decisions so revisions are deliberate and reversible.

## Approved decisions

| ID | Decision | Reason |
| --- | --- | --- |
| D-01 | Product name: Chuhai Lens | Memorable and directly tied to seeing market fit more clearly |
| D-02 | Working tagline: “See your brand through local eyes.” | Expresses the value without encouraging origin concealment |
| D-03 | Global product vision with the United States as the first implemented market module and China-to-U.S. as the initial wedge | Keeps the prototype specific while ensuring the product serves businesses entering unfamiliar markets worldwide |
| D-04 | Primary users include solo founders, new brands, and factory-to-DTC operators | Avoids designing only for large established brands |
| D-05 | A URL or an image is required; either one is sufficient | Enables pre-launch testing and minimizes friction |
| D-06 | Start with a review-type selector | Makes one product adaptable to brand, page, social, ad, and video contexts |
| D-07 | Keep most contextual fields optional | Encourages first use while still rewarding richer context |
| D-08 | Interface in English; report in English or Simplified Chinese | Judge-friendly interface with practical client output |
| D-09 | Include subjective visual, font, image, casting, and layout analysis | The “something feels off” problem is not limited to language |
| D-10 | Include lightweight competitor, Reddit/review, and AI-visibility evidence | Grounds the report beyond the submitted asset |
| D-11 | Synthetic personas appear only as final-report quotes | Preserves the insight while avoiding a costly interview product overlap |
| D-12 | Persona quotes are explicitly fictional and non-statistical | Prevents misrepresentation as real research |
| D-13 | Include visual references/crops in evidence cards | Makes recommendations faster to understand and verify |
| D-14 | Do not build an editor, campaign generator, or legal-advice feature | Protects prototype focus |
| D-15 | Build a no-login public web prototype | Gives judges and prospective clients a low-friction test path |
| D-16 | Keep the architecture host- and domain-portable | Allows later migration without rewriting the product |
| D-17 | Continue in the current task and current folder | Preserves this task as the main Build Week Codex session |
| D-18 | Create the personal GitHub repository only after secret protections and initial files are ready | Prevents accidental key exposure and overbroad repository authorization |
| D-19 | Keep unrelated side-project concepts entirely outside the Chuhai Lens repository and Build Week submission | Separate future products should not dilute judging or public positioning |

## Default technical decisions — reversible

| ID | Default | Change impact |
| --- | --- | --- |
| T-01 | Next.js + TypeScript | Moderate change if altered after implementation; low impact before coding |
| T-02 | Vercel free-tier deployment | Low impact because core services use standard environment variables and adapters |
| T-03 | No database for the first prototype | A database can be added later for report history/share links |
| T-04 | No custom domain for submission | A domain can be connected later without changing code or GitHub |
| T-05 | Static fictional or explicitly authorized demo | Can be replaced later if asset rights and public criticism risks are addressed |

## Decisions still requiring owner approval

| ID | Question | Recommended default | Decision deadline |
| --- | --- | --- | --- |
| P-01 | Which exact demo brand/assets will be public? | Use a fictional brand unless the owner supplies a site with permission | Before visual fixture creation |
| P-02 | Should live video be complete or limited beta for submission? | Build after image and URL paths; keep strict limits | After first live image analysis |
| P-03 | Should reports persist/share by link? | No persistence for Build Week; browser print/PDF only | Before backend implementation |
| P-04 | What daily public usage allowance is affordable? | Start very small with sample-mode fallback | After measured test costs |
| P-05 | Public or private judging repository? | Public after license and secret review | Immediately before repo creation |

## Change procedure

When changing an approved decision:

1. record the new decision and date;
2. identify affected documents, interface, code, tests, and demo materials;
3. update the source documents first;
4. implement the change; and
5. verify the live experience and submission materials remain consistent.
