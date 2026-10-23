# charly-kubernetes — retired

> **RETIRED — this repo publishes nothing.** All 3 `kubernetes`-family skills live in the
> repo that holds the code, plugin or config each one documents (the table below).
> Nothing is authored, built, deployed or consumed here: a change to a `kubernetes`-family
> skill is a change at its destination repo, in the same pull request as the entity it
> documents.

**This repo no longer authors a skill.** It was the `charly-kubernetes` concept candy: a `true`-no-op `plan:` and 3 `skill:` entities, with the prose in `.agents/skills/`.
Under `AGENTS.md` Part II #5 a skill lives in the repo whose code,
plugin or config it describes — and this repo holds none of them (measured before the
change: **0 `.go`, 0 `.cue`, no `candy/` directory**) — so all of them moved, byte-identically,
to the repos that do:

| Skill | Now authored in | The entity that owns it |
|---|---|---|
| `helm` | [`opencharly/plugin-helm`](https://github.com/opencharly/plugin-helm) | the `step:helm-release` / `verb:helm` providers |
| `check-k8s`, `kubernetes` | [`opencharly/plugin-kube`](https://github.com/opencharly/plugin-kube) | the `command:` providers that serve these verbs |

**The addresses did not change.** Every skill keeps its `kubernetes` family at its
destination node, so `/charly-kubernetes:<skill>` still resolve — they are simply authored
where the entity is implemented. The move is the rule `AGENTS.md` Part II #5 states, tracked
in [opencharly/opencharly#600](https://github.com/opencharly/opencharly/issues/600).

## What remains here

| Property | Value |
|---|---|
| Layer / candy | `charly-kubernetes` (drained concept candy) |
| Install content | none — a `true` no-op `plan:` |
| Owns | nothing — 0 `skill:` entities |
| Service / port | none |

Do not compose, reference or edit this repo: the skills, their routing nodes and their
prose all live at the destinations above, and this repo's retirement is tracked in
[opencharly/opencharly#600](https://github.com/opencharly/opencharly/issues/600).
