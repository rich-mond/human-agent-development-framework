# Adoption Guide

Version: 0.8.3 Draft

This guide helps teams adopt the Human-Agent Development Framework without turning it into ceremony.

The goal is to improve human-agent delivery quality by reducing avoidable implementation loops.

## Adoption Principle

Start with the smallest useful set of guardrails.

Add process only when it reduces rework, protects important decisions, or improves future delivery.

## Day 1 Adoption

Use this when a team wants immediate value without changing its delivery process.

1. Read `framework.md`.
2. Copy `templates/agents-template.md` into the repository as `AGENTS.md` or the equivalent agent guidance file.
3. Add repository-specific guidance for:
   - How to run tests
   - How to run formatting and static analysis
   - Where standards live
   - When the agent must stop
4. Use `templates/small-change-template.md` for narrow, reversible changes.

Day 1 adoption is successful when agents ask better questions, preserve repository patterns, and report validation more clearly.

## Week 1 Adoption

Use this when agents are regularly making production code changes.

1. Identify recurring sources of implementation loops.
2. Add or improve repository standards for those areas.
3. Use `templates/plan-template.md` for feature work and material behaviour changes.
4. Capture delivered specifications for changes that future agents or humans will need to understand.
5. Review whether stop conditions and approval expectations are clear.

Week 1 adoption is successful when plans constrain the right decisions and first-pass implementations require fewer material corrections.

## Full Adoption

Use this when a team wants continuous improvement of human-agent delivery.

1. Maintain repository standards as first-class guidance.
2. Maintain `AGENTS.md` as agent operating guidance.
3. Use decision-complete plans for material work.
4. Store delivered specifications in a discoverable location.
5. Periodically review framework learning notes.
6. Update standards, templates, and agent guidance when avoidable loops repeat.

Full adoption is successful when repeated issues become improved guardrails rather than repeated corrections.

## Approval Levels

Use explicit approval only where it matters.

### Approval To Investigate

The agent may inspect files, gather evidence, and report findings.

This does not approve implementation.

### Approval To Implement

The agent may change files within the approved scope and assumptions.

This does not approve commit, push, deployment, publication, or pull request creation.

### Approval To Publish Or Operate

The agent may perform an explicitly requested external action such as commit, push, deploy, publish, or create a pull request.

This approval should name the action.

## Minimum Viable Feature Plan

For many feature changes, a useful plan can be shorter than the full template.

At minimum, capture:

- Objective
- Goals and non-goals
- Requirements and acceptance criteria
- Evidence reviewed
- Human-owned decisions
- Scope boundaries
- Implementation approach
- Validation plan
- Stop conditions
- Approval to implement

Use the full template when the change affects architecture, public contracts, persistence, security, runtime configuration, deployment, or cross-cutting behaviour.

## Common Adoption Mistakes

- Using the full plan template for tiny changes
- Treating existing code as the only source of guidance
- Letting unknowns silently become implementation
- Asking agents to make business or architecture decisions without approval
- Skipping delivered specifications for changes that future work will depend on
- Capturing lessons but not updating guardrails
