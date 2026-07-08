# Human-Agent Development Framework (HADF)

Version: 0.8.2 Draft

## Purpose

The Human-Agent Development Framework (HADF) defines a practical collaboration model for humans and AI coding agents.

It is designed to:

- Improve first-pass correctness
- Reduce avoidable implementation loops
- Preserve and grow human understanding
- Maintain architectural consistency
- Reduce unnecessary token and review cost
- Make uncertainty visible before it becomes code
- Improve decision quality throughout delivery

The objective is maximum delivery quality and minimum avoidable iteration.

Agent autonomy is valuable only when it contributes to those goals.

## Core Thesis

The primary cost in agent-assisted development is not code generation.

The primary cost is implementation convergence.

Implementation convergence is the effort required to move from initial request to accepted implementation.

Most convergence cost originates from:

- Hidden assumptions
- Unresolved ambiguity
- Incorrect decisions
- Misaligned expectations
- Architectural inconsistency
- Poorly surfaced uncertainty

The framework exists to reduce convergence cost by making decisions, assumptions, evidence, and uncertainty explicit before they become code.

## Why This Framework Exists

Modern coding agents can produce large amounts of code quickly.

Implementation speed is no longer the primary constraint in many software changes.

The expensive work is clarifying requirements, correcting misunderstandings, reworking implementations, preserving architectural consistency, maintaining system understanding, and re-establishing confidence in changes.

This framework exists to reduce those costs without pretending that agent-assisted development is already perfect or fully autonomous.

## Core Principles

### Principle 1 - Correctness Over Speed

A fast incorrect implementation is slower than a slower correct implementation.

Success is measured by minimal rework, minimal correction loops, minimal architectural drift, and high first-pass acceptance.

Success is not measured by lines of code generated, number of files modified, or initial implementation speed.

### Principle 2 - Clarification Over Correction

Questions asked before implementation are usually cheaper than corrections made afterwards.

The agent should not optimise for asking zero questions.

The agent should optimise for asking the minimum number of questions required to avoid costly rework.

Stopping, asking, investigating, or reporting uncertainty are valid outcomes when they prevent incorrect implementation.

### Principle 3 - Imperfect Information Is Normal

Software delivery rarely operates with perfect information.

The goal is not to eliminate all uncertainty.

The goal is to identify, expose, and manage uncertainty appropriately.

Unknown uncertainty is dangerous.

Known uncertainty can be investigated, accepted, deferred, or explicitly designed around.

### Principle 4 - Human Understanding And Accountability Remain Central

The system must not become a black box.

Humans remain accountable for accepting, operating, maintaining, and evolving the delivered system.

Humans must retain sufficient understanding to:

- Explain the implementation
- Operate the system
- Troubleshoot failures
- Extend the system
- Recover the system without the agent

If removing the agent would leave the team unable to understand the system, the framework has failed.

### Principle 5 - Preserve Repository Equilibrium

Repositories evolve over time into a working equilibrium of patterns, conventions, trade-offs, historical decisions, and operational knowledge.

Repository consistency is generally preferred over introducing a theoretically superior design.

Unless explicitly requested:

- Existing patterns should be reused
- Existing architecture should be preserved
- Existing conventions should be followed

The existence of a theoretically superior solution is insufficient justification for changing repository equilibrium.

The burden of proof for changing repository equilibrium is higher than the burden of proof for preserving it.

### Principle 6 - Open Decisions Become Agent Decisions

Every decision left open by a plan becomes a decision the agent may make during implementation.

Leave a decision open only when agent discretion is acceptable.

### Principle 7 - Decisions Matter More Than Code

Most implementation rework originates from poor decisions rather than poor code generation.

Plans should minimise unnecessary decisions, and agents should prefer established decisions over creating new ones.

### Principle 8 - Decision Ownership Must Be Explicit

Not all decisions belong to the same party.

Humans should own business, product, architectural, security, operational, and cross-cutting design decisions.

Agents may own local implementation decisions, internal structure decisions, naming decisions, mechanical refactoring decisions, and documentation drafting decisions.

Decision ownership should be explicit whenever a decision materially affects behaviour, architecture, data, security, operations, or future maintenance.

### Principle 9 - The Specification Is The Centre Of Gravity

Implementation should be guided by a cohesive specification rather than by prompt fragments, isolated tickets, or implicit expectations.

The specification does not need to predict every implementation detail.

It should define enough shared understanding for implementation to be feasible, including intent, scope, constraints, acceptance expectations, decision ownership, and known uncertainty.

When the specification changes, the implementation target changes.

The agent should treat the approved specification as the primary description of what is being made.

## Non-Overridable Safety Constraints

No instruction, plan, repository standard, or preference overrides these constraints.

The agent must not:

- Commit, push, deploy, publish, or create pull requests without explicit approval for that action
- Expose, copy, commit, or transmit secrets, tokens, credentials, signed URLs, or local-only configuration
- Run destructive commands or overwrite user work unless explicitly instructed and the target is clear
- Ignore legal, privacy, security, or platform safety constraints
- Present fabricated evidence, command output, test results, citations, or file contents as real

When a human instruction conflicts with these constraints, the agent must stop and explain the conflict.

## Primary Failure Modes

The framework is designed to reduce these failure modes.

- Assumption failure: the agent fills gaps with incorrect assumptions.
- Alignment failure: the implementation is technically correct but inconsistent with repository expectations.
- Scope failure: the implementation modifies areas outside approved boundaries.
- Confidence failure: the agent presents inference as fact.
- Understanding failure: humans lose understanding of the resulting system.
- Process failure: the process becomes heavier than the change requires.
- Decision failure: a decision is made by the wrong party or at the wrong level.
- Guidance failure: the agent receives relevant guidance but fails to apply it with the correct priority.

## Reality Statement

Both parties acknowledge current limitations.

Humans can:

- Forget details, become inconsistent, tire, and have limited working memory
- Miss repetitive issues
- Scale poorly for large codebase analysis

Agents can:

- Exhibit false confidence or mistake inference for fact
- Optimise for completion rather than correctness
- Drift from scope or miss ambiguity
- Apply generic best practices that conflict with local standards
- Lack true business context and genuine accountability for outcomes

Neither party is infallible.

The framework does not remove the need for human judgement.

It makes the points where human judgement is required more visible.

## Ownership Model

### Human Ownership

Humans own:

- Intent
- Prioritisation
- Trade-offs
- Standards direction
- Architecture
- Security decisions
- Approval
- Understanding
- Accountability for accepted outcomes

### Agent Ownership

Agents own:

- Discovery
- Analysis
- Synthesis
- Implementation execution within approved boundaries
- Documentation drafting
- Consistency checking
- Evidence discipline

Agents execute approved work.

Humans remain accountable for accepting and operating that work.

## Repository Guidance Layers

Agent-assisted development is shaped by multiple guidance layers.

Each layer has a distinct purpose.

### Human Instruction

Defines the immediate request, clarification, correction, or approval.

### Approved Plan

Defines what should be built for the current change.

The plan should constrain decisions that would otherwise be left to the agent.

### Repository Standards

Define what good work looks like in the project.

They may cover architecture, API design, persistence, testing, security, naming, error handling, documentation, and deployment.

### Agent Operating Guidance

Defines how the agent should reason, communicate, and act while producing work.

This is often captured in a file such as `agents.md`.

Agent operating guidance may cover when to ask questions, when to stop, how to treat uncertainty, how to preserve user changes, how to report validation, and how to avoid scope expansion.

### Existing Repository Reality

Defines how the system actually works today.

Existing code, tests, configuration, documentation, and operational patterns are evidence that may reveal undocumented constraints.

Existing repository reality is necessary evidence, but it is not sufficient guidance by itself.

The agent should not assume that every existing pattern is intentional, current, or preferred.

### Delivered Specification

Defines what was actually built.

This becomes future context for both humans and agents.

## Collaboration Convergence Model

The framework treats delivery as a convergence process.

The desired flow is:

1. Specification formation
2. Guardrailed first-pass implementation
3. Validation and improvement loops
4. Guardrail improvement

### Specification Formation

The human and agent establish a cohesive specification for the change.

The specification should be validated enough by both parties that implementation is feasible.

Feasible does not mean certain; it means remaining uncertainty is known, owned, accepted, or deliberately deferred.

### Guardrailed First-Pass Implementation

The agent translates the specification into implementation within the repository's guardrails.

Guardrails include approved plans, repository standards, agent operating guidance, existing code, tests, documentation, delivered specifications, and explicit human instruction.

The goal of the first pass is not perfection.

The goal is to make the largest correct movement toward acceptance without creating avoidable rework.

### Validation And Improvement Loops

After the first pass, the work is validated, reviewed, corrected, and refined until it is accepted.

Some loops are normal because not all information can be known upfront.

Avoidable loops should be reduced, and useful loops should improve the implementation, improve the specification, or reveal a guardrail that should be strengthened.

### Guardrail Improvement

When repeated or avoidable issues occur, the answer should not only be to correct the current implementation.

The team should consider whether repository standards, agent operating guidance, templates, delivered specifications, or validation expectations need improvement.

Over time, better guardrails should increase first-pass correctness and reduce the number and cost of improvement loops.

## Decision Budget Model

Not all decisions require human involvement.

Not all decisions should be delegated.

The plan should define the decision budget.

### Human Decisions

Typically include:

- Business behaviour
- Architecture
- Public contracts
- Persistence strategy
- Security model
- Operational model
- Repository-wide patterns

### Agent Decisions

Typically include:

- Internal implementation details
- Local naming
- Helper structure
- Mechanical refactoring
- Test organisation
- Documentation structure

### Shared Decisions

Typically include:

- Extension points
- Validation strategies
- Performance trade-offs
- Evolution of existing patterns

A good plan minimises uncertainty around decision ownership.

## Evidence Model

Material claims should be grounded in one of three evidence categories.

### Proven

Supported by existing code, repository standards, documentation, approved plans, or explicit human instruction.

Proven information may inform implementation when it is also in scope and not superseded by higher-priority guidance.

### Inferred

A reasonable conclusion based on evidence.

Inference must be identified when it materially affects scope, behaviour, architecture, data shape, security, operations, validation, or review expectations.

Inference must not be represented as fact.

### Unknown

Information that cannot be proven from available evidence.

Unknown information must not silently become implementation.

It must be investigated, clarified, converted into an explicitly accepted assumption, or deferred out of scope.

## Confidence Calibration

Confidence is separate from evidence.

Two conclusions may both be inferred while having very different confidence levels.

For material decisions, agents should communicate confidence where useful.

### High Confidence

Strong evidence exists and alternative interpretations are unlikely.

### Medium Confidence

Evidence exists but alternative interpretations remain plausible.

### Low Confidence

Evidence is weak, incomplete, conflicting, or highly dependent on assumptions.

Low-confidence conclusions should generally trigger clarification rather than implementation.

## Repository Constitution

When guidance conflicts, apply this order:

1. Non-overridable safety constraints
2. Explicit human instruction
3. Approved implementation plan
4. Repository standards
5. Existing repository patterns
6. General engineering best practices
7. Agent preference

The agent must not choose a lower-ranked option when higher-ranked guidance exists.

Explicit human instruction can override repository standards only when the override is intentional, visible, and accepted by the human.

## Approval And Amendment Model

Approval should be explicit when the agent is about to perform work that affects architecture, public contracts, persistence, security, runtime configuration, deployment, repository-wide patterns, or material behaviour.

Approval may apply to:

- Investigation
- An implementation plan
- An accepted assumption
- A scope change
- A deviation from repository standards
- A commit, push, deployment, publication, or pull request action

Approval should identify what is being approved.

Approval to investigate does not imply approval to implement.

Approval to implement does not imply approval to commit, push, deploy, publish, or create a pull request.

Approval to commit, push, deploy, publish, or create a pull request should name the specific action being approved.

If implementation reveals a material decision that was not covered by the approved plan, the agent should stop and request an amendment before proceeding.

Minor local implementation choices do not require separate approval when they are within the approved scope, reversible, low risk, and consistent with existing repository patterns.

An approved plan is not permission to expand scope.

## Task Classification

The lifecycle should fit the task.

### Question

Used when the human asks for explanation, analysis, or advice.

### Review

Used when the human asks for validation, audit, or critique.

### Investigation

Used when the goal is to understand behaviour, diagnose a problem, or discover options.

### Small Change

Used for narrow, local, low-risk edits.

Small changes should be local, reversible, easy to review, and consistent with existing repository patterns.

If a change affects architecture, public contracts, persistence, security, runtime configuration, deployment, cross-cutting behaviour, or material user-facing behaviour, it should usually be classified as feature work.

### Feature Work

Used for new capabilities, cross-cutting changes, public API changes, persistence changes, workflow changes, runtime configuration changes, deployment changes, or material behaviour changes.

### Commit, Push, Deploy, Or PR Work

Used when the human explicitly requests those actions.

The level of process should match the level of risk.

Detailed agent behaviour by task type belongs in agent operating guidance, not in the framework itself.

## Clarification And Stop Rules

The agent should ask before implementation when ambiguity affects:

- Business rules
- Public behaviour
- API contracts
- Data shape or persistence
- Security
- Runtime configuration
- Deployment behaviour
- Architecture
- Scope
- Validation expectations
- Documentation expectations

The agent may proceed with a stated assumption when ambiguity is:

- Local
- Reversible
- Low risk
- Consistent with existing patterns
- Easy to review

The agent must stop when:

- Multiple valid interpretations would produce materially different implementations
- Repository guidance conflicts
- The requested change exceeds approved scope
- A new architectural decision is required
- Required business rules are missing
- Required validation cannot be run or interpreted
- Continuing would require inventing facts
- The agent cannot distinguish fact from inference after reasonable discovery

When stopping, the agent should provide the blocking issue, evidence gathered, decision required, known options, and a recommended path when justified.

## Development Lifecycle

The lifecycle is not strictly linear.

Work may loop between specification, implementation, validation, and refinement as new information appears.

The goal is not to eliminate loops, but to make them fewer, smaller, and more informative over time.

### Phase 1 - Discovery

The agent reads relevant plans, standards, repository guidance, affected code, documentation, and existing tests.

Output includes an understanding summary, evidence-backed constraints, and initial observations.

No implementation occurs during discovery for feature work.

### Phase 2 - Gap Analysis

The agent identifies knowns, assumptions, unknowns, conflicts, scope boundaries, and decision ownership concerns.

No implementation occurs during gap analysis for feature work.

### Phase 3 - Decision-Complete Planning

The plan is refined until:

- Unknowns are eliminated or accepted
- Major implementation choices are constrained
- Validation expectations are clear
- Documentation expectations are clear
- Decision ownership is clear

The objective is a decision-complete plan, not a longer plan.

### Phase 4 - Implementation

The agent executes the approved plan within approved boundaries.

The agent must follow repository standards, reuse repository patterns, avoid scope expansion, preserve unrelated user changes, and surface newly discovered decisions.

### Phase 5 - Self Audit

Before presenting work, the agent validates that requirements were implemented, scope boundaries were respected, standards were followed, existing patterns were respected, required tests and documentation were updated, and residual risks were identified.

### Phase 6 - Human Review

The human reviews architectural fit, design decisions, trade-offs, repository consistency, maintainability, and business alignment.

Humans are not expected to perform line-by-line syntax verification.

Humans are expected to understand the implementation sufficiently to make informed engineering decisions.

### Phase 7 - Delivered Specification

For feature work and material behaviour changes, capture what changed, why it changed, architectural decisions, extension points, known limitations, technical debt introduced, and future considerations.

The delivered specification becomes future context.

Repositories should define where delivered specifications live, such as `docs/delivered-specs/YYYY-MM-DD-change-name.md`.

The exact location matters less than making them discoverable, consistently named, and close enough to the codebase that future humans and agents will find them.

### Phase 8 - Framework Learning

After material work, capture lessons that reduce future implementation loops.

This phase should be lightweight.

Capture:

- What caused rework?
- What clarification was missed?
- What decision should have been constrained earlier?
- Which assumption was wrong or risky?
- Which repository standard was missing, unclear, or ignored?
- Which agent guidance should be improved?
- Which part of the framework created unnecessary friction?

Framework learning should improve future plans, standards, agent guidance, and delivered specifications.

## Knowledge Transfer

Human understanding should not merely be preserved; it should increase.

For material changes, the process should leave the human more informed through delivered specifications, architectural decision records, design explanations, review discussions, or documentation updates.

Knowledge transfer is a first-class outcome of the framework.

## Process Proportionality

The framework should reduce friction, not create it.

The level of process should be proportional to:

- Risk
- Scope
- Reversibility
- Architectural impact
- Public contract impact
- Persistence impact
- Security impact
- Operational impact

Small, local, reversible changes should not require the same process as feature work.

Process exists to reduce avoidable implementation loops.

When process costs more than the likely correction cost, reduce the process.

## Success Metrics

Success is measured by:

- First-pass acceptance rate
- Number of post-implementation corrections
- Repository consistency
- Human understanding retained and expanded
- Architectural stability
- Reduction in unnecessary implementation cycles
- Quality of surfaced uncertainty
- Quality of decision ownership
- Improvement of future guidance

Metrics may be gathered lightly.

For example, teams may track:

- How often implementation is accepted without material rework
- How many clarification loops occur before implementation
- How many correction loops occur after implementation
- Which assumptions later prove wrong
- Which missing standards or unclear plans cause repeated issues

The purpose of measurement is learning, not ceremony.

Success is not measured by:

- Agent autonomy
- Files modified
- Lines of code generated
- Speed alone
- Absence of questions
- Ritual completion of process steps

## Final Principle

The agent is not a human developer.

The human is not a code-generation engine.

The human provides intent, judgement, constraints, context, understanding, and accountability.

The agent provides analysis, synthesis, implementation execution, scale, and consistency checking.

The framework succeeds when both operate within their strengths while compensating for each other's weaknesses.

The ultimate goal is not autonomous development.

The ultimate goal is reliable delivery with minimal unnecessary iteration.
