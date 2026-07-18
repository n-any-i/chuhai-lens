# Chuhai Lens

**Tagline:** See your brand through local eyes.

Chuhai Lens helps founders and brands evaluate whether their customer-facing materials feel clear, credible, and culturally at home in a foreign market they may not know firsthand—without asking them to hide where they come from.

The product vision is global: any business should be able to select a target market and receive a market-specific review. The Build Week prototype proves that vision through one deliberately focused route—China-based and other international businesses entering the United States.

## Current status

Product definition is in progress. Application code has not started yet.

This repository will be the source of truth for the OpenAI Build Week prototype. Decisions should be recorded in the documents below instead of relying only on chat history.

## Document map

Read these in order:

1. [Product brief](docs/01-product-brief.md)
2. [User experience](docs/02-user-experience.md)
3. [Analysis framework](docs/03-analysis-framework.md)
4. [Report specification](docs/04-report-specification.md)
5. [AI system specification](docs/05-ai-system-specification.md)
6. [Technical plan](docs/06-technical-plan.md)
7. [Security and privacy](docs/07-security-and-privacy.md)
8. [Testing and evaluation](docs/08-testing-and-evaluation.md)
9. [Cost and operations](docs/09-cost-and-operations.md)
10. [Build Week plan](docs/10-build-week-submission.md)
11. [Decision log](docs/11-decision-log.md)
12. [Development workflow](docs/12-development-workflow.md)

Durable Codex instructions live in [AGENTS.md](AGENTS.md), and completed changes are summarized in [CHANGELOG.md](CHANGELOG.md).

## Prototype promise

A user selects a target market and what they want reviewed, provides at least one URL or image, and receives an evidence-led market-readiness report that combines:

- first-scan visual and language analysis;
- objective commerce and logistics expectations;
- competitor and public-conversation evidence when available;
- a lightweight AI-visibility check;
- transparent synthetic-persona reactions presented as illustrative research quotes; and
- prioritized, practical recommendations.

For Build Week, the only enabled target market is the United States. The scoring labels, market references, and report architecture are designed so additional country or regional modules can be added later.

## Safety rules

- Never commit API keys or other secrets.
- Never imply synthetic personas are real customers.
- Never encourage a brand to conceal its country of origin.
- Never describe subjective cultural judgments as universal facts.
- Never present the product as legal advice or a replacement for real market research.

## Build sequence

1. Approve the documents and remaining product decisions.
2. Create a minimal clickable interface with a deterministic demo report.
3. Add live multimodal analysis and evidence capture.
4. Test the complete judge journey.
5. Create the personal GitHub repository and push only after secret protections are in place.
6. Deploy a free public demo, record the video, and submit through Devpost.
