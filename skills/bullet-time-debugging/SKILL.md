---
name: bullet-time-debugging
description: Use when a bug, failure, regression, or complex system has many competing symptoms, unclear causality, noisy logs, or too many possible causes to debug effectively in one pass.
---

# Bullet Time Debugging

## Overview

Slow a chaotic failure down into a sequence of observable state transitions.

**Core principle:** reduce uncertainty one variable at a time.

## Freeze the Scene

Before changing code, identify:

1. **Objective** — what behavior is required?
2. **Current state** — what is happening now?
3. **Known-good state** — when or where did it work?
4. **First divergence** — where does reality first differ from expectation?
5. **Competing explanations** — what plausible causes remain?
6. **Discriminating test** — what smallest experiment separates those explanations?

Then run the discriminating test before making a broad fix.

## Trace the Matrix

Map the relevant flow:

`INPUT -> STATE -> TRANSFORMATION -> DEPENDENCY -> OUTPUT`

For each boundary, ask:

- What enters?
- What should leave?
- What actually leaves?
- Which component owns the transformation?
- What state can leak across calls?
- What dependency can mutate the result?

The first incorrect transition is usually more valuable than the final visible symptom.

## Last Known Good

For regressions, compare the failing state with the closest known-good state.

Check differences in:

- code;
- dependency versions;
- configuration;
- environment variables;
- runtime versions;
- API responses;
- schemas and data shape;
- permissions;
- persisted state;
- cache;
- network behavior.

Prefer concrete diffs over memory.

## Smallest Useful Experiment

A good debugging experiment changes or observes one meaningful variable and has a predicted result.

Before running it, state internally:

> If hypothesis H is correct, I expect observation O.

Afterward:

- O occurs -> confidence in H increases.
- O does not occur -> H weakens or dies.
- a new observation occurs -> update the model before continuing.

## Do Not Spray Fixes

Avoid:

- changing several unrelated files at once;
- adding retries before identifying the failure mode;
- suppressing errors to make output look clean;
- rewriting a subsystem before isolating the cause;
- assuming the stack trace's final line is the root cause;
- repeatedly applying patches without testing a hypothesis.

## Agent Smith Check

If several symptoms share the same shape, search for one replicating source:

- shared helper;
- common schema;
- global state;
- generated code;
- dependency;
- serializer;
- event handler;
- inherited configuration.

Fix the source when possible rather than every copy.

## Bullet Time Exit

Leave diagnostic mode when the evidence identifies a cause strongly enough to justify a targeted fix.

After the fix, reproduce the original scenario and verify the failure is gone without introducing a new one.

**Slow the scene down. See the first divergence. Then move.**
