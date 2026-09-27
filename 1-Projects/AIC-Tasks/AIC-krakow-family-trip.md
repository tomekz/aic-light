# AIC-krakow-family-trip

## Task metadata

- **Status:** done
- **Owner:** Copilot session `Kraków family trip`
- **Created:** 2026-09-27
- **Last updated:** 2026-09-27

Allowed status values: `draft`, `ready`, `in-progress`, `blocked`, `done`.

## Objective

Deliver a practical, self-contained four-day family itinerary for Kraków whose
total planned cost does not exceed EUR 300.

## Background / context

The traveler needs a clear four-day plan that can be followed without context
from another session. It must combine family-friendly sightseeing with
realistic food and local transport allowances, state the assumptions behind
the budget, and preserve money for contingencies. The durable trip plan belongs
in the repository's reusable resources.

## Scope

- Plan four full sightseeing days in Kraków for a family.
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

- [x] A four-day itinerary gives practical times, family-friendly activities,
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
  can support four realistic sightseeing days.
- The itinerary uses mostly free sights, two paid attractions across four
  days, self-catered breakfasts, packed lunches, and inexpensive hot dinners.
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
- 2026-09-27 - Scope changed from two to four full sightseeing days; task
  reopened and set to `in-progress`.
- 2026-09-27 - Itinerary expanded with dedicated Wawel/Kazimierz, aviation
  museum, and Nowa Huta days while retaining the EUR 300 ceiling.
- 2026-09-27 - Verified four distinct day sections, reconciled daily and
  category totals, confirmed EUR 292.94 total, and set the task to `done`.

## Open questions

No open questions.

## Handoff / results

- **Outcome:** Delivered a practical, budget-capped four-day Kraków itinerary
  for two adults and two children.
- **Changes:** Expanded `3-Resources/Travel/Krakow-family-trip.md` from two to
  four full days and updated this AIC task record to reflect the revised scope.
- **Validation:** Confirmed exactly four day sections and all required
  itinerary sections are present; `git diff --check` passed; independently
  reconciled daily totals of PLN 337 + PLN 226 + PLN 326 + PLN 226 =
  PLN 1,115 with category totals of PLN 800 food + PLN 210 activities +
  PLN 105 transport; adding PLN 130 contingency produces PLN 1,245, or
  EUR 292.94 at PLN 4.25/EUR, leaving EUR 7.06 below the cap.
- **Remaining work:** None.
