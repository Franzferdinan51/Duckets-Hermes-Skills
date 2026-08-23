---
name: oracle-protocol
description: Use when a fix, decision, experiment, deployment, migration, or uncertain technical action needs explicit prediction, evidence, comparison, and verification before the agent can trust the result.
---

# Oracle Protocol

## Overview

Turn trial-and-error into deliberate experimentation.

**Core principle:** predict before acting, observe afterward, and update beliefs from the difference.

## The Oracle Test

Before a meaningful action, answer internally:

1. What hypothesis am I testing?
2. What do I predict will happen if it is correct?
3. What result would weaken or disprove it?
4. What will I measure or inspect?

Then act.

Afterward compare reality with the prediction.

## Interpret the Result

### Prediction matched

Increase confidence, but do not automatically declare completion. Check whether the result actually proves the user's objective was achieved.

### Prediction failed

Do not hide the mismatch or force the old explanation to survive.

Ask:

- Which assumption was wrong?
- Did the action execute as intended?
- Did an unseen dependency intervene?
- Is the measurement itself reliable?

Update the model.

### Unexpected third result

Treat surprise as high-value evidence.

An unexpected result can expose hidden state, a different owner, stale assumptions, or another causal path.

Follow it if it can advance the mission.

## Confidence Ladder

Use evidence proportionally:

- **Speculation:** plausible explanation, not tested.
- **Indication:** one observation supports it.
- **Strong evidence:** multiple independent observations support it.
- **Verified for scope:** direct test demonstrates the claim under the relevant conditions.

Do not call speculation verified.

## Verification Patterns

Prefer verification that observes real behavior:

- reproduce the original failure after a fix;
- run targeted tests, then broader tests when appropriate;
- inspect actual output, state, logs, API response, or artifact;
- compare before and after;
- validate both success path and important failure path;
- confirm a deployment or write actually exists rather than assuming a command succeeded.

## Falsification First

When several explanations fit the evidence, prefer experiments that can eliminate whole classes of hypotheses quickly.

A failed hypothesis is progress when it narrows the search space.

## Completion Gate

Before claiming success, ask:

> What evidence would I show another engineer that this actually works?

If the answer is only "the change looks right," verification is incomplete.

## Reality Rule

Never fabricate tool output, tests, files, deployments, commits, logs, API behavior, or measurements.

**The Oracle does not tell you what you want to hear. It tells you what reality showed.**
