# AIC-krakow-family-trip

## Task metadata

- **Status:** done
- **Owner:** Copilot session `Kraków family trip`
- **Created:** 2026-09-27
- **Last updated:** 2026-09-27

Allowed status values: `draft`, `ready`, `in-progress`, `blocked`, `done`.

## Objective

Deliver a practical, self-contained two-day family itinerary for Kraków whose
total planned cost does not exceed EUR 300.

## Background / context

The traveler needs a clear two-day plan that can be followed without context
from another session. It must combine family-friendly sightseeing with
realistic food and local transport allowances, state the assumptions behind
the budget, and preserve money for contingencies. The durable trip plan belongs
in the repository's reusable resources.

## Scope

- Plan two full sightseeing days in Kraków for a family.
- Provide a time-based itinerary with family-friendly sights and activities.
- Estimate meals, local public transport, and attraction costs by day.
- Summarize costs by category and show the conversion to euros.
- State family-size, lodging, exchange-rate, fare, and price assumptions.
- Include a contingency while keeping the total within EUR 300.
- Save the resulting plan as a reusable repository resource.

## Non-goals

- Booking tickets, accommodation, restaurants, or transport.
- Paying for any part of the trip.
- Including accommodation, travel to Kraków, airport transfers, alcohol, or
  souvenirs in the EUR 300 sightseeing budget.
- Coordinating with, depending on, or modifying work from another task
  session.

## Requirements / acceptance criteria

- [x] A two-day itinerary gives practical times, family-friendly activities,
  meal stops, and travel or rest guidance for both days.
- [x] Assumptions explicitly cover family size, children's ages, lodging,
  inbound travel, exchange rate, reduced fares, and changing prices.
- [x] Each day has estimated costs for food, activities, and local transport
  in PLN and EUR.
- [x] A category summary includes meals, sights/activities, local transport,
  and a separately identified contingency.
- [x] The arithmetic is verified and the total, including contingency, is no
  more than EUR 300.
- [x] The output is stored in
  `3-Resources/Travel/Krakow-family-trip.md` and includes practical booking and
  official-reference guidance.
- [x] The work is independent from all other sessions and includes no
  unrelated repository changes.

## Relevant files / links

- `README.md` - defines the repository's PARA organization.
- `1-Projects/AIC-Tasks/README.md` - defines the AIC task workflow.
- `1-Projects/AIC-Tasks/AIC-TEMPLATE.md` - required task-document structure.
- `3-Resources/Travel/Krakow-family-trip.md` - durable trip plan produced by
  this task.

## Constraints and decisions

- Total budget is capped at EUR 300.
- The planning date is 2026-09-27 and the working exchange rate is
  EUR 1 = PLN 4.25; prices are allowances and must be rechecked before travel.
- The representative family is two adults and two children aged 7-15.
- Accommodation and inbound/outbound travel are excluded so the limited budget
  can support two realistic sightseeing days.
- The itinerary uses mostly free central sights and one principal paid
  attraction per day.
- This task is executed wholly within its dedicated worktree and branch.

## Dependencies

None.

## Status / progress

- 2026-09-27 - Task created and set to `in-progress`.
- 2026-09-27 - Repository PARA and AIC workflow guidance reviewed.
- 2026-09-27 - Two-day trip plan drafted as an independent travel resource.
- 2026-09-27 - Budget set at PLN 1,245, including a PLN 190 contingency, using
  the stated PLN 4.25/EUR planning rate.
- 2026-09-27 - Verified required files and itinerary sections; reconciled day
  and category totals; confirmed EUR 292.94 total and EUR 7.06 headroom.
- 2026-09-27 - All acceptance criteria completed and task set to `done`.

## Open questions

No open questions.

## Handoff / results

- **Outcome:** Delivered a practical, budget-capped two-day Kraków itinerary
  for two adults and two children.
- **Changes:** Created
  `3-Resources/Travel/Krakow-family-trip.md` and this complete AIC task record.
- **Validation:** Confirmed both files and all required itinerary sections are
  present; `git diff --check` passed; independently recalculated PLN 680 food +
  PLN 270 activities + PLN 105 transport + PLN 190 contingency = PLN 1,245,
  which is EUR 292.94 at PLN 4.25/EUR and EUR 7.06 below the cap. Day totals
  also reconcile to the non-contingency category subtotal.
- **Remaining work:** None.
