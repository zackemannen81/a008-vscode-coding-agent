# Development Plan

## Objective

Deliver an A008-backed coding-agent experience in Visual Studio Code. The integration mechanism is deliberately undecided until the supported A008 runtime boundary and applicable VS Code APIs are verified. This plan describes work and decision gates, not implemented capabilities.

## Guiding Constraints

- Recheck both this repository and `C:\\code\\A008` before relying on the initial baseline; follow A008's own instructions when work touches that checkout.
- Prefer supported A008 interfaces and current, authoritative VS Code APIs. Do not choose an extension host, protocol, process model, or agent API by assumption.
- Keep workspace context and tool access scoped, understandable, and least-privileged. Define approval, cancellation, secrets, and failure behavior before enabling side effects.
- Build a small end-to-end slice before expanding features. Keep the integration boundary testable and distinguish automated from manual verification.
- At each phase, update the active task, status, system document, and journal as appropriate. Record decisions with evidence and keep this plan aligned with verified reality.

## Phases and Exit Criteria

### 0. Establish the verified baseline

- Reinspect the project tree and current A008 checkout; read applicable task/system docs and identify relevant runtime entry points, tests, and existing integration surfaces.
- Inspect authoritative VS Code documentation for candidate agent/extension APIs, lifecycle, compatibility, and packaging requirements.
- Record source paths, API support status, constraints, and unknowns in `CURRENT_STATUS.md` and the active task.
- **Exit:** evidence is sufficient to compare viable integration boundaries, or a concrete blocker and the information needed to resolve it are recorded. No architecture is selected merely from package description or product intent.

### 1. Select and document the integration design

- Compare supported options against runtime compatibility, lifecycle, user experience, cancellation, workspace access, security, testability, and distribution.
- Define the minimum user-visible workflow and explicit non-goals for the first release.
- Record the chosen boundary, rejected alternatives, evidence, compatibility assumptions, threat/approval model, and open risks in `SYSTEMDOC.md` and an ADR if a durable architectural decision warrants one.
- **Exit:** the design is grounded in verified A008 and VS Code contracts, and scope plus acceptance checks are agreed. If no supported route exists, stop implementation and document the blocker/options.

### 2. Create the integration foundation

- Establish only the package/project configuration required by the chosen design, with a reproducible development and test workflow.
- Implement the minimal lifecycle boundary: startup, connection/initialization, user-visible errors, cancellation/disposal, and configuration/secret handling as applicable.
- Add focused tests for boundary behavior and failure paths; avoid broad tool permissions or unrelated capabilities.
- **Exit:** the integration can initialize and shut down reliably under automated checks, and any runtime requirements are documented. This phase does not imply a complete coding-agent workflow.

### 3. Deliver a minimal end-to-end agent workflow

- Connect one user-initiated VS Code interaction to A008 using the selected supported interface.
- Pass only the necessary active-workspace context; present progress, result, errors, and cancellation in the chosen VS Code surface.
- Keep side-effecting actions disabled or explicitly mediated until approval and scope behavior is implemented and verified.
- Add automated tests for request/result/error/cancel paths and appropriate manual checks inside VS Code.
- **Exit:** a user can complete the agreed minimal workflow without hidden access or unreported failures, with test evidence recorded.

### 4. Harden, validate, and prepare distribution

- Verify permission boundaries, workspace isolation, secret handling, cancellation, malformed/unavailable runtime behavior, and compatibility against the declared support matrix.
- Add only user-facing capabilities justified by the product scope and verified A008 support; test each permission and failure boundary.
- Document installation, configuration, limitations, troubleshooting, and supported versions; run build, automated, and manual validation appropriate to the selected packaging route.
- **Exit:** release checks pass, known limitations are disclosed, and distribution/release steps are reproducible. Do not claim publication unless it actually occurs.

## Immediate Next Action

Begin Phase 0: inspect A008's applicable docs and actual runtime/API interfaces, then research current VS Code integration options. Update the findings before proposing architecture. The original baseline only confirms a docs scaffold here and a Node 24 private ESM A008 package; it does not settle integration suitability.

## Cross-Phase Definition of Done

- Decisions and implementation claims are backed by current source, tests, or authoritative documentation.
- Security and user-control behavior is tested, not only described.
- Relevant project docs and task records reflect the delivered state and unresolved limitations.
- Verification reports state exactly which automated and manual checks ran and their outcomes.
