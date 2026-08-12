# Review count and recency missing — dev spec
Site: nomadinternet.com · Priority 6 · Medium · Effort: Medium (2-5 days)

## Problem
Social proof lacks review count and recency, weakening credibility.

## Evidence (from the live site)
> A section heading reads “Real Stories from Real Users”.
> A section heading reads “As Featured In:”.

## Current state
notes: Trustpilot rating shown but no count or recency.

## Required change
notes: Display review count and date range.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Display review count and date range.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_review_count_and_recency_missing` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
