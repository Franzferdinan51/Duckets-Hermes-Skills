---
name: wake-up-neo
description: Use when an agent is looping, repeating similar fixes, rereading the same evidence, over-planning, asking avoidable questions, or losing connection to the user's original objective.
---

# Wake Up, Neo

## Overview

This skill breaks unproductive agent loops and restores forward motion.

**Core principle:** persist toward the goal, not toward a failing approach.

## Loop Indicators

Trigger a reset when one or more of these appears:

- nearly identical fixes are attempted repeatedly;
- the same files or logs are reread without a new question;
- planning continues but no test or implementation occurs;
- code changes happen without a hypothesis;
- symptoms are patched individually without searching for a shared cause;
- the agent keeps asking for information available through tools or evidence;
- the task drifts into interesting but irrelevant research;
- the current approach has failed multiple times without changing materially.

## WAKE Protocol

### WAKE

Restate the user's objective internally in one sentence.

If the current activity does not advance that objective, stop it.

### TRACE

Summarize only concrete attempts:

- what was tried;
- what happened;
- what each attempt established.

Do not retell the entire conversation.

### BREAK

Identify the repeating assumption or strategy.

Ask:

> What am I continuing to believe despite evidence that this path is not working?

### SHIFT

Choose a materially different next path.

Examples:

- inspect instead of patch;
- reproduce instead of theorize;
- use the API instead of the UI;
- replace a dependency instead of fixing compatibility around it;
- trace backward from desired output;
- test a smaller component;
- compare known-good and failing states;
- search for a shared root cause.

A cosmetic variation of the failed path does not count as a shift.

### EXECUTE

Take the next useful action immediately.

Do not restart with another large plan unless planning itself is necessary to execute safely.

## Progress Test

After each new action, ask:

- Did this advance the task?
- Did this reduce uncertainty?
- Did it reveal a new path?

If none are true, change strategy again.

## Rabbit Hole Interrupt

If investigation becomes detached from the objective, say internally:

> The task remains.

Return to the nearest unresolved step that directly affects completion.

## External Blockers

Do not loop forever against a hard external constraint.

If progress requires missing credentials, permissions, hardware, inaccessible data, or an unsupported external action, establish that with evidence and report the smallest unblocker needed.

## Exit Condition

Wake Up mode ends when the agent has a materially different strategy and has resumed evidence-producing work.

**Wake up, Neo. The failed path is not the mission.**
