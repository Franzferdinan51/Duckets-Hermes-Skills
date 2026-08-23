---
name: follow-the-white-rabbit
description: Use when an error, anomaly, strange file, unexpected result, undocumented behavior, hidden dependency, or unusual clue may reveal the actual cause or a better path through a difficult task.
---

# Follow the White Rabbit

## Overview

Use anomaly-driven investigation to uncover hidden structure without getting distracted by irrelevant side quests.

**Core principle:** unusual evidence deserves attention when it can materially advance the mission.

## The Rabbit Test

Before following a clue, ask:

1. Is it real evidence rather than speculation?
2. Could it explain the failure, reveal ownership, expose hidden state, or unlock a better path?
3. Can it be investigated at reasonable cost?
4. Will the result reduce meaningful uncertainty?

If mostly yes, follow it. Otherwise, return to the task.

## Common White Rabbits

- an error that contradicts the current theory;
- a file or module referenced indirectly;
- an undocumented endpoint or configuration option;
- a helper function already solving part of the problem;
- a TODO, FIXME, dead branch, or abandoned implementation;
- a test failing differently than expected;
- a version or dependency mismatch;
- state appearing where it should not exist;
- behavior that changes between environments;
- a repeated naming or data-flow pattern;
- a log line that appears before every failure;
- a success path that differs from the assumed architecture.

## Investigation Loop

### Observe

Record what is actually unusual.

Avoid converting an observation into an explanation too early.

### Connect

Ask how the clue could connect to the user's objective or observed failure.

Trace callers, dependencies, state, configuration, data flow, and recent changes.

### Predict

Form a testable expectation.

Example: if this hidden configuration controls the behavior, changing or inspecting it should alter a specific observable result.

### Test

Run the smallest useful experiment.

### Decide

- If confirmed, follow the new path.
- If disproven, preserve the information and return to the main problem.
- If ambiguous, choose the next cheapest discriminating test.

## Rabbit Hole Guard

Every few investigative steps, ask:

> How does this connect to the original objective?

Stop when:

- the connection becomes weak;
- the clue has been disproven;
- additional detail no longer changes the next action;
- another path has clearly higher information value.

The goal is not to understand the entire system. It is to understand enough of the system to complete the task.

## Deja Vu

When something that previously worked suddenly fails, treat repetition or unexpected recurrence as evidence that something changed.

Check:

- configuration;
- dependencies and versions;
- environment;
- permissions;
- state and caches;
- API behavior;
- data format;
- recent commits;
- generated artifacts.

Do not assume yesterday's explanation still applies today.

## Completion Rule

A useful rabbit either:

- reveals a cause;
- reveals a path;
- eliminates a hypothesis;
- exposes a hidden dependency;
- or materially reduces uncertainty.

If it does none of those, stop chasing it.

**Follow the white rabbit — but keep the mission in sight.**
