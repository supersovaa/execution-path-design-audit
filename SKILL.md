---
name: execution-path-design-audit
description: Audit design completion by tracing actual execution paths across interacting decisions, automatic processing, state changes, and external boundaries instead of relying on isolated capability checks.
---

# Execution Path Design Audit

Use this skill when deciding whether a design is complete for behavior whose execution depends on multiple interacting mechanisms, decisions, or transitions.

## Core rule

Judge design completion by tracing the actual execution path, not by checking only that the required capabilities are described individually.

For each behavior in scope, start where it first affects externally meaningful state, eligibility, observation, output, or another established contract.
Trace the behavior through the decisions, automatic processing, state changes, and follow-up processing that actually occur until the next external stop or the behavior completes.

Trace only boundaries that exist for that behavior.
Do not require a decision, branch, or interaction that the behavior does not have.

## Audit the path

At each relevant point in the path, confirm that the settled requirements and design determine what happens next.

Check, as applicable:

- who makes each decision, what information is available at that point, and what that decision determines;
- whether candidate sets, admissibility, or other gating decisions can be determined from information already established at that point;
- whether a result depends on a future state change, an unresolved decision, or hypothetical optional processing, and if so, whether the design already defines how that dependency is handled;
- whether automatic processing has determined inputs and externally meaningful results;
- whether combining individually designed mechanisms introduces an unresolved dependency between them; and
- after a decision or automatic step, how far processing continues and where the next external stop or completion boundary occurs.

## Use capability checks as supporting evidence

Capability lists, design matrices, and other per-feature checks can support the audit.
They do not replace execution-path tracing when completion depends on how those capabilities interact.

A design can contain every required capability individually and still be incomplete if their execution order or information dependencies require another design decision.

## Determine completion

Treat the audited behavior as design-complete only when its relevant execution path can be followed to the next external stop or completion boundary without introducing a new design decision.

When the path exposes an unresolved dependency, identify the point where the path becomes underdetermined and return that gap to the workflow that owns the design.
Do not invent a resolution as part of this audit.

## Responsibility boundary

This skill audits design completion across execution paths.

Requirement definition, design decisions, implementation planning, implementation mechanics, test definition, and exhaustive completion across a finite target set remain with their owning workflows.
