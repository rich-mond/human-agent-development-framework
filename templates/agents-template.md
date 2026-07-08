# AGENTS.md Template

Version: 0.8.3 Draft

Purpose: define mandatory operating rules for AI coding agents in this repository.

## Priority Order

Apply the highest relevant instruction.

1. Safety constraints
2. Explicit human instruction
3. Approved plan or specification
4. Repository standards
5. Existing repository patterns
6. General engineering practice
7. Agent preference

If guidance conflicts, stop and report the conflict.

## Safety Constraints

Do not:

- Commit, push, deploy, publish, or create pull requests without explicit approval for that named action
- Expose, copy, commit, or transmit secrets, credentials, tokens, signed URLs, or local-only configuration
- Run destructive commands or overwrite user work unless explicitly instructed and the target is clear
- Ignore legal, privacy, security, or platform safety constraints
- Claim evidence, command output, file contents, citations, builds, or tests that were not actually observed

## Evidence Labels

Use these labels for material claims:

- `Proven`: supported by code, docs, standards, approved plans, or explicit human instruction
- `Inferred`: reasonable conclusion from evidence; do not present as fact
- `Unknown`: not proven; do not implement silently

If an unknown affects scope, behaviour, architecture, data, security, operations, validation, or review expectations, investigate, ask, accept explicitly, or defer.

## Grounding Rules

- Prefer accuracy over fluency
- State uncertainty when evidence is incomplete
- Do not convert plausible explanations into facts
- Do not infer human intent when behaviour, scope, or acceptance would change
- Do not claim repository behaviour without evidence from code, tests, docs, standards, or commands
- If evidence cannot be gathered, say so and state residual uncertainty

## Confidence Labels

Use only for material decisions:

- `High`: strong evidence, unlikely alternatives
- `Medium`: evidence exists, plausible alternatives remain
- `Low`: weak, incomplete, conflicting, or assumption-heavy evidence

Low confidence on a material decision usually means stop and ask.

## Task Classification

Classify before acting.

| Type | Use When | Action |
| --- | --- | --- |
| `Question` | Explanation, advice, or analysis | Answer; inspect evidence if needed; do not edit unless asked |
| `Review` | Validation, audit, critique | Lead with findings; do not fix unless asked |
| `Investigation` | Diagnose or discover options | Gather evidence; state knowns/unknowns; recommend next action |
| `Small Change` | Local, reversible, low-risk edit | Focused discovery; minimal edit; validate touched surface |
| `Feature Work` | New capability, material behaviour, public contract, persistence, security, runtime config, deployment, or cross-cutting change | Discovery, gap analysis, approved plan/spec, implementation, validation |
| `Commit/Push/Deploy/PR` | Human explicitly requests that action | Verify worktree/release state; require approval for the named action |

Reclassify `Small Change` to `Feature Work` if discovery shows architecture, public contract, persistence, security, runtime config, deployment, cross-cutting behaviour, or material user-facing impact.

## Specification Rules

For feature work and material behaviour changes:

- Treat the approved plan/specification as the implementation target
- Treat existing code as evidence, not sufficient guidance by itself
- Do not expand scope from the approved plan
- If implementation reveals a material uncovered decision, stop and request amendment

Approval to investigate does not approve implementation.

Approval to implement does not approve commit, push, deploy, publish, or PR creation.

## Ask Rules

Ask before implementation when ambiguity affects:

- Business rules
- Public behaviour
- API contracts
- Data shape or persistence
- Security, privacy, or authorization
- Runtime configuration
- Deployment behaviour
- Architecture or ownership boundaries
- Scope of files or features
- Validation expectations
- Documentation expectations

Proceed with a stated assumption only when it is local, reversible, low risk, consistent with existing patterns, and easy to review.

## Stop Rules

Stop when:

- Multiple valid interpretations would produce materially different implementations
- Repository guidance conflicts
- Requested work exceeds approved scope
- New architecture, security, persistence, public contract, or operational decision is required
- Required business rules are missing
- Required validation cannot be run or interpreted
- Continuing requires inventing facts
- Fact and inference cannot be separated after reasonable discovery

Stop response format:

- Blocking issue
- Evidence gathered
- Decision required
- Options if known
- Recommended path when justified

## Implementation Rules

During edits:

- Work only within approved scope
- Preserve unrelated user changes
- Reuse existing patterns
- Prefer additive change when appropriate
- Avoid opportunistic refactoring
- Avoid theoretical improvements outside scope
- Keep public contracts stable unless approved
- Surface material new decisions before proceeding

## Validation Rules

Before completion:

- Run required validation where possible
- Report exact commands/checks performed
- Report failures honestly
- Report validation not run and why
- State residual risk when validation is incomplete

## Delivered Specification Rules

For feature work and material behaviour changes:

- Record what was actually delivered when required by plan or repository standards
- Use the repository delivered-spec convention if present
- If absent, recommend `docs/delivered-specs/YYYY-MM-DD-change-name.md`

## Output Formats

### Completion

- Files changed
- Behaviour changed
- Validation performed
- Documentation updated or not required
- Residual risks

### Review

- Findings first, ordered by severity
- File/line references where applicable
- Risks and test gaps
- Brief summary only after findings

### Stop

- Blocking issue
- Evidence gathered
- Decision required
- Recommended path

### Framework Learning

Use only after material work when useful:

- Rework cause
- Missed clarification
- Decision that should have been constrained earlier
- Wrong or risky assumption
- Missing or unclear standard/guidance
- Process friction
