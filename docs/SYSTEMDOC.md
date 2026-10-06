# System Document

## Product Objective

Integrate A008 (`C:\code\A008`) into Visual Studio Code so it can act as a coding agent. The intended outcome is an A008-backed agent experience in VS Code; the implementation shape and currently supported capabilities are not yet established by this repository.

## Evidence Boundary

This document records durable behavior only after it exists and is verified. At the current baseline, this is a docs-only scaffold, and no integration architecture or runtime behavior is documented as implemented. Keep desired behavior, implementation facts, and open decisions clearly separate.

## Development Roadmap

The planned phases and exit criteria are maintained in `DEVELOPMENT_PLAN.md`. Treat them as future work: update this system document only when an architectural decision or behavior is supported by verified evidence.

## Design Constraints for Future Work

- Inspect the A008 source and its documented interfaces before choosing how to connect it to VS Code. Prefer existing supported APIs over a parallel agent implementation.
- Investigate the relevant VS Code extension/agent APIs and compatibility requirements from authoritative sources before depending on them.
- Define how agent context is scoped to the active workspace, how progress/results/errors/cancellation reach the user, and how settings and credentials are handled.
- Preserve explicit user control and least privilege for filesystem, terminal, network, and other side-effecting tools. Make approval, cancellation, and failure behavior understandable; do not silently widen access.
- Keep integration boundaries testable. Verify behavior with appropriate automated tests and document manual checks where automation is not available.
- Do not assert any of these as implemented until supported by code and verification.

## Open Questions

- What A008 runtime/API is supported for local integration, and what lifecycle does it require?
- Which VS Code extension or coding-agent integration surface best fits the supported A008 interface?
- What packaging, compatibility, security, and release requirements apply?
