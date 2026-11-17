# TripOps AI — Project Plan

## Problem statement
Travel teams often process enquiries, supplier information, quotations, and post-booking tasks across disconnected documents and manual workflows. TripOps AI will explore a traceable agent-assisted workflow for these tasks.

## MVP user journey
1. A traveller submits a natural-language request.
2. The system extracts destination, dates, travellers, budget, and preferences; missing fields are requested.
3. Retrieval searches approved sample supplier documents and returns supporting source references.
4. Deterministic pricing tools prepare a draft quotation and itinerary.
5. A staff member reviews and approves the draft.
6. The system records follow-up tasks and status changes.

## Engineering requirements
- Typed request/response schemas and clear API boundaries.
- Persisted workflow state and useful execution logs.
- Bounded tool permissions and human approval for consequential actions.
- Reproducible evaluation data and metrics.
- Tests for malformed inputs, missing evidence, tool errors, retries, and pricing edge cases.

## Out of scope for the initial demo
- Real airline check-in or live booking modifications.
- Real payment processing.
- Use of real traveller personal information.
- Autonomous external communication without human review.

## Milestones
See the milestone list in the root README. Record implementation evidence and evaluation results before describing a feature as completed on a resume.
