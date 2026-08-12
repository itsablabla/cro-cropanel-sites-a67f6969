# Value claims lack specifics — dev spec
Site: nomadinternet.com · Priority 10 · Medium · Effort: Medium (2-5 days)

## Problem
The claim of being fastest lacks concrete speed or comparison figures, leaving the value proposition unsupported.

## Evidence (from the live site)
> A section heading reads “The Fastest Rural & On-the-Go Internet in the USA”.
> A section heading reads “Nomad Internet: The Go-To For Rural Internet”.

## Current state
notes: No specific speed or comparison.

## Required change
notes: Add measurable speed or comparison.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add measurable speed or comparison.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_value_claims_lack_specifics` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
