# opencode Agents

Personal collection of custom [opencode](https://opencode.ai) subagent definitions, version-controlled with git.

Each `.md` file in this directory defines an agent: YAML frontmatter (description, mode, permissions) followed by the agent's system prompt.

## Agents

| Agent | Mode | Description |
|-------|------|-------------|
| [docs-writer](docs-writer.md) | all | Writes and maintains project documentation |
| [ideogram-json-gen](ideogram-json-gen.md) | all | Generates Ideogram JSON configs for the Ideogen CLI (image generation prompts, batch configs) |
| [maintainability-auditor](maintainability-auditor.md) | all | Deep, forward-looking maintainability assessment (cohesion, complexity, coupling, architectural evolution) |
| [pair-programmer](pair-programmer.md) | all | Real-time collaborative coding in XP style; acts as driver or passenger |
| [project-kickoff](project-kickoff.md) | all | Translates planning discussions into foundational project files (PLAN.md, AGILE.md, AGENTS.md) |
| [repo-analyst](repo-analyst.md) | all | Explores and answers questions about a specific codebase (read-only) |
| [secure-code-auditor](secure-code-auditor.md) | all | Comprehensive security audits following OWASP best practices |
| [security-audit](security-audit.md) | subagent | Performs security audits and identifies vulnerabilities |
| [tech-strategist](tech-strategist.md) | all | Discusses technology choices, architecture trade-offs, and open-source vs corporate perspectives |

## Usage

Agents live in `~/.config/opencode/agents/` and are available automatically to opencode. Invoke them by name when delegating a task, e.g. "run a maintainability analysis on this repo" or "pair with me as passenger on this function".

Frontmatter fields:
- `description` — when opencode should launch the agent (include examples for reliable triggering)
- `mode` — `all` (primary or subagent), `subagent`, or `primary`
- `permission` — per-tool allow/deny overrides (e.g. `edit: deny` for read-only auditors)
