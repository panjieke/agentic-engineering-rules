Rules for engineering teams where AI agents write, test, and ship code next to people.

AI coding agents are fast, but they are only as reliable as the guardrails around them. Most teams find this out the expensive way: an agent rewrites a module nobody asked it to touch, adds a dependency without telling anyone, or reports a feature as "done" when the tests pass but it doesn't work. This repository collects rules that prevent that. They are short, opinionated, and come from real delivery work. Agents can follow them and humans can enforce them.

Why this exists
Agents follow what's written down. Unwritten team habits never reach the model, so the rules need to live in the repo.
Speed without control creates rework. Clear boundaries cut down the review time agents create.
Regulated environments need traceability. Every change an agent makes should be explainable, reviewable, and reversible.
What's inside
rules/
└── core/
    └── test-driven-development.mdc

One Cursor rule, so far. It requires test-driven development in atomic steps: write one failing test and confirm it fails for the right reason, write the minimum code that passes, refactor only while the suite stays green, micro-commit, then repeat. No extra approval is required between those steps when that workflow is followed. The rule applies to every file.

The file is written for Cursor. Copy `rules/core/test-driven-development.mdc` into `.cursor/rules`. The content adapts equally to Claude Code and other agentic IDEs: copy the rule body into `CLAUDE.md`, `AGENTS.md`, or the instruction file that tool reads, and trim it to fit your team. A short set of rules that gets enforced is better than a long set that gets ignored.

More rule sets (workflow, quality, security) will be added over time.
Contributing

PRs are welcome. Each new rule should state the failure it prevents and, where possible, link to a real-world example. Rules without a reason behind them will be challenged.