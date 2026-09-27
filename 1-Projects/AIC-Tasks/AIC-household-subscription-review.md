# AIC-household-subscription-review

## Task metadata

- **Status:** done
- **Owner:** Copilot session `Subscription review checklist`
- **Created:** 2026-09-27
- **Last updated:** 2026-09-27

Allowed status values: `draft`, `ready`, `in-progress`, `blocked`, `done`.

## Objective

Create a thorough, practical, reusable checklist that helps a household
discover, evaluate, secure, document, and regularly review all subscriptions
and recurring charges.

## Background / context

Household subscriptions can be spread across cards, bank accounts, app stores,
digital wallets, email accounts, devices, and different household members.
Monthly statement reviews can also miss annual renewals, free trials, bundled
benefits, duplicate accounts, and subscriptions billed under unfamiliar
merchant names.

The result must make a complete review easy to perform without relying on this
task's originating conversation. It should guide a user from discovery through
decisions and follow-up, provide a structured inventory, and explicitly avoid
storing credentials or sensitive payment data.

## Scope

- Create an action-oriented household subscription review checklist.
- Cover preparation and discovery across financial records, accounts,
  communications, devices, and household members.
- Provide a practical subscription inventory structure.
- Cover categorization, actual usage, value, pricing, billing frequency,
  renewal terms, and price changes.
- Identify duplicate, overlapping, bundled, and separately billed services.
- Support explicit keep, negotiate, switch, downgrade, pause, rotate, and
  cancel decisions.
- Include security, privacy, account-access, and payment hygiene.
- Include documentation, reminders, follow-up, and recurring review cadences.
- Include a clear definition of done.
- Store the checklist in the repository's ongoing household area.

## Non-goals

- Review or cancel any real household subscription.
- Access bank, card, email, password-manager, or provider accounts.
- Store passwords, multifactor recovery codes, full account numbers, full
  payment-card numbers, security answers, or identity documents.
- Recommend specific subscription providers or assume regional consumer laws.
- Create calendar reminders or modify a household budget on the user's behalf.
- Depend on or modify work in another Copilot session.

## Requirements / acceptance criteria

- [x] A standalone Markdown checklist exists under `2-Areas/Household/`.
- [x] The checklist covers discovery through statements, bank accounts,
      wallets, app stores, email, devices, bundles, trials, and household
      members.
- [x] The checklist includes a reusable inventory with ownership, pricing,
      billing, renewal, usage, decision, action, and confirmation fields.
- [x] It provides a consistent method for comparing monthly, annual,
      quarterly, weekly, and four-week billing.
- [x] It covers categorization and evidence-based actual usage and value.
- [x] It covers prices, price changes, promotions, auto-renewal, notice
      periods, termination fees, refunds, and data or benefit loss.
- [x] It checks for duplicate accounts, overlapping services, app-store versus
      direct billing, bundles, included benefits, and legitimate family plans.
- [x] It gives concrete workflows for keeping, negotiating, switching,
      downgrading, pausing, rotating, and cancelling.
- [x] It includes account security, multifactor authentication, recovery,
      device and integration review, payment hygiene, and unauthorized-charge
      handling.
- [x] It includes documentation, savings tracking, reminders, cancellation
      follow-up, and a summary table.
- [x] It defines monthly, quarterly, annual, and event-triggered review
      cadences.
- [x] It warns against recording secrets or sensitive payment details.
- [x] Markdown and repository whitespace validation complete without errors.
- [x] The checklist and this task record are committed together and proposed
      for review in a pull request.

## Relevant files / links

- [`2-Areas/Household/subscription-review-checklist.md`](../../2-Areas/Household/subscription-review-checklist.md)
  - The reusable household checklist delivered by this task.
- [`AIC-TEMPLATE.md`](AIC-TEMPLATE.md)
  - Required structure for this self-contained task record.
- [`README.md`](README.md)
  - Conventions for AIC task files.
- [`../../2-Areas/README.md`](../../2-Areas/README.md)
  - PARA guidance for ongoing responsibilities such as household management.

## Constraints and decisions

- The checklist is stored under `2-Areas/Household/` because subscription
  management is an ongoing responsibility without a fixed completion date.
- The checklist is provider-neutral and region-neutral so it remains reusable.
- Real household information is not required to use or verify this artifact.
- Sensitive credentials and complete financial identifiers must never be
  stored in the checklist or repository.
- The work is self-contained on its own branch and does not depend on changes
  from another session.
- The task record remains in `1-Projects/AIC-Tasks/` for review with the
  delivered checklist; archival can occur after the pull request is accepted.

## Dependencies

None.

## Status / progress

- 2026-09-27 - Task created and set to `in-progress`.
- 2026-09-27 - Reviewed the repository PARA and AIC task conventions.
- 2026-09-27 - Created the household subscription review checklist under the
  ongoing household area.
- 2026-09-27 - Added discovery, inventory, categorization, usage, pricing,
  renewal, duplication, decision, security, documentation, reminder, and
  recurring-review sections.
- 2026-09-27 - Verified every acceptance criterion against the completed
  checklist and ran repository whitespace validation successfully.
- 2026-09-27 - Completed the handoff and set the task status to `done`.

## Open questions

No open questions.

## Handoff / results

- **Outcome:** Delivered a standalone, action-oriented household subscription
  review checklist that can be reused for monthly checks, quarterly reviews,
  and comprehensive annual reviews.
- **Changes:** Added
  `2-Areas/Household/subscription-review-checklist.md` and this AIC task record.
- **Validation:** Manually traced all requested topics to explicit checklist
  sections, confirmed every acceptance criterion, and ran `git diff --check`
  successfully.
- **Remaining work:** Review and merge the pull request. After acceptance, the
  completed task record may be moved to `4-Archives/Projects/AIC-Tasks/`
  according to repository practice.
