# project-kickoff

A [Claude skill](https://support.claude.com/en/articles/12512180-use-skills-in-claude) that solves a familiar problem: **Claude forgets everything between sessions.** You make decisions, build things, change direction — and the next conversation starts from zero.

`project-kickoff` fixes this at the start of a project. It runs a short interview to clarify your goal and scope, then creates three tracking files that act as the project's persistent memory:

| File | What it holds |
|------|---------------|
| `PROJECT.md` | What you're building, for whom, V1 scope, what's out |
| `DECISIONS.md` | Chronological log of every meaningful decision, with rationale |
| `PROGRESS.md` | Chronological log of completed units of work |

The skill also writes a convention block into your project's `CLAUDE.md`, so **every future session keeps the files up to date automatically** — decisions and completed work get recorded as they happen, without you asking. When a decision reverses a previous direction, it's logged in a richer narrative format (*what we thought / why we turned / what changed*), so the reasoning isn't lost.

The interview and all generated files are written in **whatever language you're speaking** — the skill itself is in English, but it adapts.

## Installation

**Claude Code** (recommended — this is where the skill works fully, since it relies on a project folder and `CLAUDE.md`):

Copy the `project-kickoff` folder into your skills directory:

```bash
cp -r project-kickoff ~/.claude/skills/
```

Or download the packaged `project-kickoff.skill` file from [Releases](../../releases) and double-click it to install.

**Claude apps (claude.ai)**: zip the `project-kickoff` folder and upload it under *Settings → Capabilities → Skills*. Note that the auto-tracking convention assumes a filesystem project with a `CLAUDE.md`, so this works best in Claude Code or with the code execution environment enabled.

## Usage

Just start talking about a new project:

> "I'm starting a new project — a habit tracker app."

The skill triggers, asks only what your opening line didn't cover, proposes a `PROJECT.md` for approval, then creates the three files and wires up the convention. From then on, it stays out of your way.

## Philosophy

Minimal on purpose. Three files, one convention block, no process overhead. Decisions get recorded when they're made (thinking out loud doesn't count); progress gets recorded when something substantial ships (tweaks don't count). Everything else lives in the code.

## License

MIT
