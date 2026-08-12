# Dead-end pricing page error — dev spec
Site: nomadinternet.com · Priority 7 · Urgent · Effort: Medium (2-5 days)

## Problem
The /pricing page returns an error, causing a dead end for users seeking pricing information.

## Evidence (from the live site)
> (see report)

## Current state
notes: Page returns error.

## Required change
notes: Fix or redirect to /plans.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Fix or redirect to /plans.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_dead_end_pricing_page_error` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
