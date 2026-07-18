# 02 — User Experience

## Design principle

The product should feel like a calm, credible market advisor—not a complicated research platform. Every optional field must earn its place.

## Primary journey

### Step 1: Choose what to review

The first screen asks: **What would you like to test?**

Options:

- Brand identity
- Website / landing page
- Product detail page
- Social media account or post
- Ad — single image
- Ad — carousel
- Ad — video
- Other / specific question

The selection changes helper text and recommended optional inputs. It does not create separate products.

### Step 2: Provide the asset

At least one of these is required:

- **URL**
- **Image upload**

Both may be provided. This supports brands that are pre-launch and do not have a live site.

For video review, accept a short uploaded video or a public URL. The prototype should enforce a practical duration and file-size limit and clearly state that only selected frames plus transcript/audio cues may be analyzed.

### Step 3: Add context — optional

Optional fields:

- Brand name
- Product category
- What the brand sells
- Intended customer
- Price range
- Current brand positioning
- Main concern or question
- Competitor names or URLs
- Additional screenshots or carousel slides
- Existing customer-review excerpts
- Brand origin positioning: proudly origin-led / global / origin-neutral / unsure

The interface should say: **“More context improves the report, but you can continue without it.”**

### Step 4: Select report settings

Required:

- Target market: United States available in the prototype, with other markets visibly described as future modules
- Report language: English or Simplified Chinese

The user interface remains in English for the Build Week demo. Only the generated report language changes.

The product architecture and wording should make clear that users will later be able to select other target markets; the U.S. is the first implemented module rather than the definition of the entire product.

### Step 5: Confirm analysis boundaries

Before running:

- explain that public URLs and uploaded assets will be sent for AI analysis;
- state that synthetic personas are fictional and illustrative;
- state that the result is directional, not legal advice or validated consumer research; and
- show an estimated processing time and, later, usage allowance.

### Step 6: Progress experience

Use meaningful stages rather than a generic spinner:

1. Capturing the submitted experience
2. Reviewing language and first impressions
3. Checking U.S. customer expectations
4. Looking for market evidence
5. Building your prioritized report

If external research fails, continue with the submitted material and label the missing section. A partial evidence source should not destroy the entire report.

### Step 7: Report

The report begins with:

- overall readiness score;
- one-sentence verdict;
- confidence/evidence coverage label;
- top three strengths; and
- top three actions.

The user can then expand detailed sections and evidence cards.

## Input validation

- One URL or image is mandatory; everything else is optional.
- Reject unsupported protocols and internal/private network URLs.
- Explain upload limits before the user waits for a failure.
- Permit the user to remove any uploaded asset before analysis.
- Never require an account for the Build Week judge path.

## Report actions

Prototype actions:

- copy the executive summary;
- print/save as PDF through the browser;
- start another review; and
- view the demo report instantly.

Post-prototype possibilities:

- compare two versions;
- export a branded client report;
- collaborate with a teammate; and
- track improvements over time.

## Demo mode

The landing page includes a prominent **View sample report** action. Judges should be able to experience the full output even if live crawling, video processing, or an external data source is temporarily unavailable.

The sample must be clearly labeled as a demo. It may use a fictional brand or an authorized real sample, but it must not publicly criticize an unrelated live business without permission.

## Accessibility and trust

- Use plain English and define “synthetic persona.”
- Do not rely on color alone for scores.
- Ensure readable contrast and keyboard navigation.
- Avoid national stereotypes in illustrations, icons, and persona descriptions.
- Show the evidence and reasoning behind important scores.
