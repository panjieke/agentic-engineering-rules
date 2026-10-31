Rules for engineering teams where AI agents write, test, and ship code next to people.

AI coding agents are fast, but they are only as reliable as the guardrails around them. Most teams find this out the expensive way: an agent rewrites a module nobody asked it to touch, adds a dependency without telling anyone, or reports a feature as "done" when the tests pass but it doesn't work. This repository collects rules that prevent that. They are short, opinionated, and come from real delivery work. Agents can follow them and humans can enforce them.

Why this exists
Agents follow what's written down. Unwritten team habits never reach the model, so the rules need to live in the repo.
Speed without control creates rework. Clear boundaries cut down the review time agents create.
Regulated environments need traceability. Every change an agent makes should be explainable, reviewable, and reversible.
What's inside
rules/
└── core/
    └── cursor/    # Cursor-native rules (.mdc): scope discipline, evidence before "done", small reversible changes

The files are written for Cursor and drop straight into `.cursor/rules`. The content adapts equally to Claude Code and other agentic IDEs: copy the rule body into `CLAUDE.md`, `AGENTS.md`, or the instruction file that tool reads, and trim it to fit your team.

More rule sets (workflow, quality, security) will be added over time.

Quick start
bash
git clone https://github.com/<org>/agentic-engineering-rules.git

For Cursor, copy the files from `rules/core/cursor/` into `.cursor/rules`. For Claude Code and other agentic IDEs, adapt the same content into the instruction file that tool reads. A short set of rules that gets enforced is better than a long set that gets ignored.

Principles
Scope is sacred. Change only what the task needs.
Evidence over assertion. "Done" means verified, not just written.
Ask before irreversible actions. That includes migrations, deletions, force-pushes, and anything in production.
Leave a trail. Every change should come with a reason a reviewer can follow.
Humans own the outcome. Agents speed up the work. Accountability stays with people.
Contributing

PRs are welcome. Each new rule should state the failure it prevents and, where possible, link to a real-world example. Rules without a reason behind them will be challenged.