# execution-path-design-audit

`execution-path-design-audit` is a lightweight design-audit skill for detecting gaps that appear only when individually designed mechanisms are connected into an actual execution path.

## Core idea

A design is not complete merely because every required capability is described somewhere.

For behavior that crosses multiple decisions, automatic steps, state changes, or external boundaries, trace the actual path from the point where the behavior first becomes externally meaningful to the next external stop or completion boundary.
The path should be determined by settled requirements and design without requiring a new design decision along the way.

## What the audit checks

The audit focuses on interaction points such as:

- what information is available when a decision is made;
- whether candidates or gating conditions can be determined at the point they are needed;
- whether current behavior incorrectly depends on unresolved future decisions or state changes;
- whether automatic processing has a determined input and result;
- whether individually designed mechanisms create a new unresolved dependency when combined; and
- where automatic continuation ends and control returns to an external actor.

Capability matrices and per-feature checklists remain useful supporting evidence, but they do not replace tracing the path itself.

## Responsibility

This skill audits whether an existing design is complete across an execution path.
It does not define requirements, choose the missing design decision, prescribe implementation, define tests, or prove exhaustive completion across a finite target set.

## Installation

Place `SKILL.md` where the target skill system loads skills from, or use the repository/package according to that system's installation method.
