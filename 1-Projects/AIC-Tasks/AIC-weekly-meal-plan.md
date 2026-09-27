# AIC-weekly-meal-plan

## Task metadata

- **Status:** done
- **Owner:** Copilot session `Weekly meal plan`
- **Created:** 2026-09-27
- **Last updated:** 2026-09-27

Allowed status values: `draft`, `ready`, `in-progress`, `blocked`, `done`.

## Objective

Create a practical, reusable weekly meal-planning template for a household of
four that coordinates meals, shopping, preparation, leftovers, and food-safety
checks without assuming specific diets or prices.

## Background / context

The repository's beginner guide uses a weekly meal-planning template for a
family of four as an example AIC task. The repository does not contain an
application or an existing meal-planning implementation; its established
product pattern is a self-contained Markdown resource paired with an AIC task
record. Meal planning is an ongoing household responsibility, so the durable
template belongs under `2-Areas/Household/`.

No dietary needs, cuisine preferences, budget, location, pantry contents, or
schedule were provided. The template must therefore prompt for these inputs
rather than invent them, and remain usable for different households and weeks.

## Scope

- Create a seven-day planning table for breakfast, lunch, dinner, snacks, and
  preparation or leftover notes.
- Include a short weekly setup workflow that captures household needs,
  schedules, budget, pantry stock, and planned use of leftovers.
- Include reusable meal, shopping, preparation, and leftover trackers.
- Group the shopping list into practical store categories.
- Include food-safety and accessibility guardrails.
- Provide an optional illustrative example for a family of four that is
  clearly separated from the blank reusable template.
- Store the result as an ongoing household resource.

## Non-goals

- Prescribing a medical, allergy, weight-loss, or therapeutic diet.
- Creating a personalized nutrition plan without household requirements.
- Guaranteeing prices, nutrition totals, portion sizes, or ingredient
  availability.
- Purchasing groceries, ordering food, or creating external reminders.
- Building software, automation, a database, or a meal-planning application.
- Modifying unrelated repository content.

## Requirements / acceptance criteria

- [x] A standalone reusable Markdown meal-planning resource exists under
      `2-Areas/Household/`.
- [x] The resource includes a complete seven-day table covering breakfast,
      lunch, dinner, snacks, and preparation or leftover notes.
- [x] The setup workflow captures household size, dietary and allergy needs,
      schedule constraints, budget, pantry stock, and meals away from home.
- [x] The template includes a meal-detail structure with servings,
      ingredients, source or recipe, preparation time, and planned leftovers.
- [x] The shopping list is grouped into practical categories and supports
      quantities, pantry checks, and purchased status.
- [x] The preparation plan identifies advance tasks, timing, storage, and
      intended meal use.
- [x] Leftovers are deliberately assigned, labeled, and checked rather than
      assumed to remain safe.
- [x] The resource includes concise food-safety, substitution, and
      accessibility guidance without making medical claims.
- [x] An optional family-of-four example demonstrates how the template works
      and is labeled as adaptable rather than prescriptive.
- [x] Markdown structure and repository whitespace validation complete without
      errors.
- [x] This task record is updated with verified criteria, dated progress,
      final status, and handoff details.
- [x] All scoped changes are committed, published, and proposed in a pull
      request.

## Relevant files / links

- `README.md` - defines the PARA organization and names this use case.
- `1-Projects/AIC-Tasks/README.md` - defines the required AIC lifecycle.
- `1-Projects/AIC-Tasks/AIC-TEMPLATE.md` - defines this task record's
  structure.
- `2-Areas/README.md` - identifies household meal planning as an ongoing
  responsibility.
- `2-Areas/Household/weekly-meal-plan.md` - reusable resource delivered by
  this task.

## Constraints and decisions

- Use the repository's existing Markdown-first second-brain architecture
  instead of introducing software or another framework.
- Treat four people as the example household size, not a fixed serving rule;
  ages and appetites are unknown.
- Keep the resource cuisine-, region-, budget-, and diet-neutral.
- Do not invent allergies, medical requirements, prices, calorie targets, or
  pantry contents.
- Keep food-safety advice general and direct users to product labels and local
  official guidance where requirements differ.
- Store the resource under `2-Areas/Household/` because meal planning recurs
  without a fixed end date.

## Dependencies

None.

## Status / progress

- 2026-09-27 - Task created and set to `in-progress`.
- 2026-09-27 - Reviewed repository PARA guidance, the AIC lifecycle, existing
  completed task patterns, and the README's family-of-four meal-plan example.
- 2026-09-27 - Confirmed there is no application or existing meal-planning
  feature; selected a reusable household Markdown resource as the matching
  integration point.
- 2026-09-27 - Created the weekly setup, seven-day plan, meal-detail tracker,
  categorized shopping list, preparation plan, leftover tracker, adaptable
  family-of-four example, and end-of-week review.
- 2026-09-27 - Verified all content criteria with an automated structure check
  and confirmed repository whitespace with `git diff --check`.
- 2026-09-27 - Committed and published the scoped changes, opened pull request
  #12, completed the handoff, and set the task status to `done`.

## Open questions

- Household dietary needs, allergies, budget, location, pantry inventory, and
  weekly schedule are unknown. These do not block a reusable blank template;
  the template captures them before a personalized plan is filled in.

## Handoff / results

Complete this section before closing the task:

- **Outcome:** Delivered a reusable weekly meal-planning template for a
  household of four.
- **Changes:** Created `2-Areas/Household/weekly-meal-plan.md` and maintained
  this AIC task record; published the work for review in pull request #12.
- **Validation:** An automated content check confirmed all required sections,
  both seven-day tables, and every weekday row. `git diff --check` passed.
- **Remaining work:** Review and merge pull request #12. After acceptance, this
  completed task record may be moved to `4-Archives/Projects/AIC-Tasks/`
  according to repository practice.
