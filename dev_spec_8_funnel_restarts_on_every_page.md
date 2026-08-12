# Funnel restarts on every page — dev spec
Site: nomadinternet.com · Priority 8 · High · Effort: Medium (2-5 days)

## Problem
The same qualification form appears on multiple pages, forcing users to re-enter the funnel regardless of landing point.

## Evidence (from the live site)
> The page's main headline reads “What Best Describes Your Time on the Road?”.
> The page's main headline reads “How Do You Use the Internet at Home?”.

## Current state
h1: What Best Describes Your Time on the Road?; cta: CONTINUE; notes: Form repeats on multiple pages.

## Required change
h1: What Best Describes Your Time on the Road?; cta: CONTINUE; notes: Persist progress across pages.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Persist progress across pages.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_funnel_restarts_on_every_page` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
