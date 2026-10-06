# Task Workflow

Draft -> Ready -> In Progress -> Complete

`docs/CURRENT_TASK.md` is the active task and defines the bounded objective, scope, and done conditions.

## For Every Task

1. Read `AGENTS.md`, the active task, and the relevant project docs.
2. Confirm the current repository and implementation state before making assumptions. For A008 work, verify the intended checkout at `C:\code\A008` and record when it is unavailable.
3. Make the smallest in-scope change consistent with verified architecture. Add or update tests where behavior changes.
4. Run relevant checks and record exactly what ran and its result; distinguish unverified work and blockers.
5. Update `CURRENT_STATUS.md` when verified project state changes, `SYSTEMDOC.md` when durable behavior/architecture changes, `FILESTRUCTURE.md` when the layout changes, and append a dated or clearly ordered entry to `JOURNAL.md` for meaningful work.
6. Mark the task Complete only when all its done conditions are met; otherwise leave it In Progress and state the remaining work.

## Documentation Rules

- Separate implemented behavior from product intent, plans, and open questions.
- Prefer evidence from the current checkout, tests, and authoritative upstream documentation; cite relevant paths or sources where useful.
- Do not use this control plane to prescribe an unverified architecture. Resolve open questions before implementation or record the decision and its evidence.
