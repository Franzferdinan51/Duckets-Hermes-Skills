# Neo Agent Skills

A Matrix-inspired suite of reusable Agent Skills for persistent problem solving, debugging, assumption breaking, anomaly investigation, and verification.

Neo is built around one rule:

> Keep working the problem.

The Matrix language is not just flavor. Each phrase maps to a concrete reasoning behavior that helps an agent stay focused, recover from failed approaches, question false constraints, investigate promising anomalies, and verify reality before claiming success.

## Skills

| Skill | Use it when |
|---|---|
| [`neo`](skills/neo/SKILL.md) | A difficult task needs persistent, adaptive problem solving across multiple approaches |
| [`follow-the-white-rabbit`](skills/follow-the-white-rabbit/SKILL.md) | An anomaly, clue, undocumented behavior, strange file, error, or unexpected result may reveal the real path |
| [`there-is-no-spoon`](skills/there-is-no-spoon/SKILL.md) | A task appears blocked by assumptions, architecture, dependencies, tooling, or supposed constraints |
| [`bullet-time-debugging`](skills/bullet-time-debugging/SKILL.md) | A bug or failure has too many symptoms and needs controlled isolation |
| [`wake-up-neo`](skills/wake-up-neo/SKILL.md) | The agent is looping, repeating failed fixes, over-planning, or losing the task objective |
| [`oracle-protocol`](skills/oracle-protocol/SKILL.md) | A decision or fix needs prediction, experiment, evidence, and verification |

## Recommended setup

Install the whole repository into an Agent Skills-compatible runtime, or copy only the skills you want.

```bash
git clone https://github.com/Franzferdinan51/Duckets-Hermes-Skills.git
```

Cross-runtime Agent Skills commonly live under:

```text
~/.agents/skills/
```

For runtimes that use another skills directory, copy the folders under `skills/` into that runtime's skill directory.

## Neo mode

For the broadest behavior, start with `skills/neo/SKILL.md`. It acts as the main Matrix-mode reasoning skill and incorporates the ideas behind the companion skills.

The focused skills are useful when you want the same techniques to trigger automatically from more specific situations such as debugging loops, mysterious errors, or hidden constraints.

## Design principles

- Persistence toward the objective, not stubbornness toward one implementation.
- Hard constraints are respected; imaginary constraints are discarded.
- Failed attempts become evidence.
- Anomalies are investigated only when they can advance the mission.
- Tools are used to either advance the task or reduce uncertainty.
- Claims of success require verification.
- The agent should change strategies before giving up.

## Evaluation scenarios

See [`evals/neo-pressure-tests.md`](evals/neo-pressure-tests.md) for pressure scenarios designed to test whether an agent actually follows the Neo behaviors rather than merely repeating Matrix-themed language.

## License

MIT. See [`LICENSE`](LICENSE).
