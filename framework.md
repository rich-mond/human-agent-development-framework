# Human-Agent Development Framework (HADF)

Version: 0.8.4 Draft

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

The objective is reliable, maintainable delivery with human understanding, proportionate verification, and low avoidable rework and cost.

Agent autonomy is valuable only when it contributes to those goals.

## Core Thesis

Code generation can be relatively inexpensive in agent-assisted development.

Implementation convergence can account for a substantial part of delivery cost, depending on the change and its context.

Implementation convergence is the effort required to move from initial request to accepted implementation.

Convergence cost can arise from incomplete specifications, hidden assumptions, incorrect decisions, failures to follow explicit instructions, defective implementation, misread repository evidence, inadequate or misleading validation, excessive process or repeated verification, and unnecessary implementation complexity.

The framework aims to reduce avoidable convergence cost by making decisions, assumptions, evidence, and uncertainty explicit before they become code, then checking implementation against the agreed target. Better specifications reduce an important class of failures; execution, compliance, verification, and process design still need attention.

## Why This Framework Exists

Modern coding agents can produce large amounts of code quickly.

When code generation is quick, implementation speed may be less limiting than the effort needed to reach a correct, maintainable result.

Convergence work includes clarifying requirements, correcting misunderstandings and defects, preserving valid architectural intent, maintaining system understanding, and establishing confidence in changes.

This framework exists to reduce those costs without pretending that agent-assisted development is already perfect or fully autonomous.

## Core Principles

### Principle 1 - Correctness Over Speed

Fast generation offers little benefit if correction and review outweigh the time saved.

Success combines correct, maintainable delivery, compliance with material requirements, human understanding, proportionate verification, and low unnecessary cost. First-pass acceptance and fewer correction loops are useful indicators, but justified iteration can improve the result.

Success is not measured by lines of code generated, number of files modified, or initial implementation speed.

### Principle 2 - Grounding Over Fluency

An agent response that sounds coherent but is not grounded is a delivery risk.

The agent should prioritise accuracy, evidence, and uncertainty disclosure over confident fluency.

When evidence is incomplete, the agent should say what is known, what is inferred, and what remains unknown.

The agent must not invent facts, command output, file contents, repository behaviour, citations, test results, or human intent.

Evidence must support the specific claim being made. Code shows what was implemented; documentation can establish intent. Neither alone establishes correct runtime behaviour, and an agent's assertion of compliance is not independent evidence.

### Principle 3 - Imperfect Information Is Normal

Software delivery rarely operates with perfect information.

The goal is not to eliminate all uncertainty.

The goal is to identify, expose, and manage uncertainty appropriately.

Unknown uncertainty is dangerous.

Known uncertainty can be investigated, accepted, deferred, or explicitly designed around.

### Principle 4 - Clarification Over Correction

Questions asked before implementation are usually cheaper than corrections made afterwards.

The agent should not optimise for asking zero questions.

The agent should optimise for asking the minimum number of questions required to avoid costly rework.

Stopping, asking, investigating, or reporting uncertainty are valid outcomes when they prevent incorrect implementation.

### Principle 5 - The Specification Is The Centre Of Gravity

Implementation should be guided by a cohesive specification rather than by prompt fragments, isolated tickets, or implicit expectations.

The specification does not need to predict every implementation detail.

It should define enough shared understanding for implementation to be feasible, including intent, scope, constraints, acceptance expectations, decision ownership, and known uncertainty. A decision-complete plan sufficiently resolves or assigns the material decisions needed for implementation; it does not prescribe every detail or guarantee correct execution.

When the specification changes, the implementation target changes.

The agent should treat the approved specification as the primary description of what is being made.

### Principle 6 - Open Decisions Need Ownership

An unresolved decision creates a risk of an unauthorised assumption; it does not transfer authority to the agent.

Distinguish decisions explicitly delegated to the agent, decisions reserved for humans, and local implementation choices within approved boundaries. Material decisions discovered during implementation require clarification or amendment when existing approval does not cover them.

### Principle 7 - Decision Quality Matters

Decision quality can substantially affect rework, so producing more code is not a substitute for resolving material decisions. Even fully specified work can be implemented incorrectly.

Plans should minimise unnecessary decisions, and agents should follow valid approved decisions rather than reopen them without reason.

### Principle 8 - Decision Ownership Must Be Explicit

Not all decisions belong to the same party.

Humans should own business, product, architectural, security, operational, and cross-cutting design decisions.

Agents may own local implementation decisions, internal structure decisions, naming decisions, mechanical refactoring decisions, and documentation drafting decisions.

Decision ownership should be explicit whenever a decision materially affects behaviour, architecture, data, security, operations, or future maintenance.

### Principle 9 - Preserve Repository Equilibrium

Repositories contain patterns, conventions, architectural intent, and operational knowledge that should inform changes.

Existing implementation is evidence, not authority. Code, tests, abstractions, workflows, and documentation may be obsolete, incorrect, unnecessarily complicated, inconsistent with approved requirements, or historical compromises that no longer fit.

Respect valid architectural intent and repository-specific conventions. When approved requirements justify removal or replacement, prefer the simplest coherent solution over unnecessary compatibility or obsolete machinery. Avoid redundant state, duplicate responsibilities, and speculative abstractions.

Consistency alone does not justify preserving obsolete design, and a theoretically better design alone does not justify a rewrite. Material architectural decisions remain human-owned; agents must not initiate broad changes outside approved scope.

### Principle 10 - Human Understanding And Accountability Remain Central

The system must not become a black box.

Humans remain accountable for accepting, operating, maintaining, and evolving the delivered system.

Humans must retain sufficient understanding to:

- Explain the implementation
- Operate the system
- Troubleshoot failures
- Extend the system
- Recover the system without the agent

If removing the agent would leave the team unable to understand the system, the framework has failed.

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
- Grounding failure: the agent produces plausible but unsupported claims.
- Understanding failure: humans lose understanding of the resulting system.
- Process failure: the process becomes heavier than the change requires.
- Decision failure: a decision is made by the wrong party or at the wrong level.
- Guidance failure: the agent misinterprets or fails to apply relevant instructions or their priority.
- Implementation failure: the implementation is defective despite an adequate specification.
- Verification failure: selected checks or reported results do not adequately establish the claimed properties.
- Complexity failure: unnecessary implementation or process machinery increases delivery and operational cost.

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
- Misinterpret explicit instructions or fail to apply relevant guidance
- Claim compliance or successful validation without sufficient evidence
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

Each layer has a distinct purpose. These are sources of guidance and context, not mandatory enforcement layers.

Written instructions communicate expectations but do not independently guarantee compliance. Verification provides evidence of actual outcomes; enforced constraints can prevent prohibited operations where suitable mechanisms exist. For consequential properties, consider existing enforcement tools according to risk, impact, practicality, and implementation cost. Stronger wording alone does not establish more reliable compliance.

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

Provides evidence about how the system is implemented and operated today.

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
4. Framework learning

### Specification Formation

The human and agent establish a cohesive specification for the change.

The specification should be validated enough by both parties that implementation is feasible.

Feasible does not mean certain; it means remaining uncertainty is known, owned, accepted, or deliberately deferred.

### Guardrailed First-Pass Implementation

The agent translates the specification into implementation within the repository's guardrails.

Guardrails may include approved plans, repository standards, agent operating guidance, tests, and enforced constraints where available. Existing code, documentation, and delivered specifications provide context and evidence. These sources differ in authority and assurance; written guidance alone does not ensure execution stays within bounds.

The goal of the first pass is not perfection.

The goal is to make the largest correct movement toward acceptance without creating avoidable rework.

### Validation And Improvement Loops

After the first pass, the work is validated, reviewed, corrected, and refined until it is accepted.

Some loops are normal because not all information can be known upfront.

Avoidable loops should be reduced. Useful loops may correct implementation, improve the specification or verification, or reveal unnecessary complexity or process. Verification should exercise meaningful supported behaviour, including representative user workflows where appropriate. Selected checks passing does not by itself establish acceptance.

### Framework Learning

Recurring failures should prompt examination of their causes, rather than an automatic increase in guardrails. They may reveal defective implementation, excessive complexity, conflicting guidance, obsolete standards, unnecessary verification, or a risk not worth eliminating.

Consider clarifying guidance, improving an existing check, correcting implementation, simplifying a workflow, removing redundant mechanisms, or accepting proportionate residual risk. Add a control only when its necessity and expected benefit justify its cost.

A successful learning outcome may be less machinery. The aim is better delivery and fewer avoidable loops, not more governance.

## Decision Budget Model

Not all decisions require human involvement.

Not all decisions should be delegated.

The plan should define the decision budget. Unresolved human-owned decisions remain reserved; shared decisions need an agreed resolution when material. Local agent choices remain subject to approved boundaries.

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

Directly established by evidence appropriate to the claim, within stated limits. Code may establish that an implementation exists; standards, documentation, plans, or human instruction may establish an intended requirement. A passing test establishes success for the exercised conditions, and a successful build establishes that the selected build completed, not correct behaviour.

Describe what the evidence establishes and its limits. Documentary support alone does not prove runtime behaviour; an agent's own compliance assertion is not independent assurance. Proven information may inform implementation when it is in scope and not superseded by higher-priority guidance.

### Inferred

A reasonable conclusion based on evidence.

Inference must be identified when it materially affects scope, behaviour, architecture, data shape, security, operations, validation, or review expectations.

Inference must not be represented as fact.

### Unknown

Information that cannot be proven from available evidence.

Unknown information must not silently become implementation.

It must be investigated, clarified, converted into an explicitly accepted assumption, or deferred out of scope.

## Confidence Calibration

Confidence is separate from evidence. High confidence does not broaden what the available evidence establishes.

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
5. Existing repository patterns as contextual guidance where valid
6. General engineering best practices
7. Agent preference

The agent must not choose a lower-ranked option when higher-ranked guidance exists. Existing implementation cannot override approved requirements. This order communicates authority; it does not mechanically enforce compliance.

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

Minor local implementation choices do not require separate approval when they are within the approved scope, reversible, low risk, and consistent with applicable standards and valid architectural intent. An unresolved human-owned decision is not such a choice.

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

- Material unknowns are resolved, explicitly accepted, or deferred out of scope
- Material implementation decisions are resolved or assigned to an authorised owner
- Validation expectations are clear
- Documentation expectations are clear
- Decision ownership is clear

The objective is a decision-complete plan, not a longer plan. Local implementation details may remain open within delegated authority. Planning reduces uncertainty but does not guarantee correct execution.

### Phase 4 - Implementation

The agent executes the approved plan within approved boundaries.

The agent must follow repository standards, respect valid architectural intent, avoid scope expansion, preserve unrelated user changes, and surface newly discovered material decisions. Reuse, removal, or replacement should serve approved requirements with the simplest coherent implementation.

### Phase 5 - Self Audit

Before presenting work, the agent checks compliance with approved scope, requirements, and standards, reviews implementation correctness, and performs appropriate validation. Check required test and documentation updates and identify residual risks. Report separately what changed, which checks ran and their results, and what behaviour remains unverified.

Self-audit can find mistakes but is not proof of correctness or independent assurance. Human review and independently observable evidence remain important in proportion to the change and its risks.

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
- What should be corrected, simplified, removed, or accepted rather than controlled?

Framework learning should improve future delivery, including reducing unnecessary implementation and process machinery. New controls need a demonstrated purpose.

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

When process costs more than the likely correction cost, reduce the process. Unnecessary complexity is itself a delivery risk in both software and collaboration. Retain mechanisms needed for approved requirements and credible operational risks.

Choose focused verification for the relevant properties and risks of the change. Do not use test count as a quality measure, repeat validation without a reason, test imaginary or unreachable scenarios, or preserve obsolete tests solely because they exist. Re-run or broaden checks when changes, failures, or unresolved concerns justify the cost.

## Success Metrics

Success combines correct and maintainable delivery, human understanding, compliance with material requirements and constraints, proportionate verification, low avoidable rework, and low unnecessary process and operational cost.

Useful indicators include:

- First-pass acceptance rate
- Number of post-implementation corrections
- Repository consistency
- Human understanding retained and expanded
- Architectural stability
- Reduction in unnecessary implementation cycles
- Quality of surfaced uncertainty
- Quality of decision ownership
- Useful improvement, simplification, or removal of guidance and mechanisms
- Implementation simplicity and maintenance and operational cost

First-pass acceptance alone can conceal defects, complexity, poor understanding, or inadequate verification. Justified iteration may improve the eventual outcome.

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

The ultimate goal is correct, maintainable delivery that humans understand, with proportionate verification, minimal avoidable iteration, and low unnecessary process and operational cost.
