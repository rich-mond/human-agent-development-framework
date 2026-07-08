# Decision-Complete Implementation Plan Template

Version: 0.8.2 Draft

This template is intended for feature work, material behaviour changes, cross-cutting changes, public API changes, persistence changes, workflow changes, runtime configuration changes, deployment changes, or other work where implementation decisions matter.

Small, local, reversible changes may use a lighter plan.

When approved, this plan becomes the implementation specification for the change.

Section markers mean:

- [Required]: complete for every feature-work plan
- [Conditional]: complete when the change affects that area
- [Optional]: complete when useful for learning or future context

## 1. Feature Or Change Name [Required]

Name:

## 2. Task Classification [Required]

Select one:

- Question
- Review
- Investigation
- Small Change
- Feature Work
- Commit, Push, Deploy, Or PR Work

Reason for classification:

## 3. Objective [Required]

Describe the outcome to achieve.

## 4. Business Context [Required]

Explain why this change is needed.

Include relevant business rules, product context, operational context, or user impact.

## 5. Goals [Required]

The change must:

- 
- 
- 

## 6. Non-Goals [Required]

The change must not:

- 
- 
- 

## 7. Requirements [Required]

Use stable identifiers so implementation and validation can be traced.

### R1

Requirement:

Acceptance:

### R2

Requirement:

Acceptance:

### R3

Requirement:

Acceptance:

## 8. Repository Guidance Reviewed [Required]

List the guidance that applies.

### Human Instruction

- 

### Repository Standards

- 

### Agent Operating Guidance

- 

### Existing Repository Patterns

- 

### Supporting Documentation

- 

## 9. Evidence Summary [Required]

### Proven

Information supported by existing code, standards, documentation, approved plans, or explicit human instruction.

- 
- 

### Inferred

Reasonable conclusions based on evidence.

- 
- 

### Unknown

Information not yet proven.

- 
- 

## 10. Decision Budget [Required]

Define which decisions are human-owned, agent-owned, or shared.

### Human-Owned Decisions

These must not be decided by the agent without approval.

- Business behaviour:
- Architecture:
- Public contracts:
- Persistence:
- Security:
- Operations:
- Repository-wide patterns:

### Agent-Owned Decisions

These may be decided by the agent within existing standards and approved scope.

- Internal implementation details:
- Local naming:
- Helper structure:
- Mechanical refactoring:
- Test organisation:
- Documentation structure:

### Shared Decisions

These require judgement and may need clarification if material.

- Extension points:
- Validation strategy:
- Performance trade-offs:
- Evolution of existing patterns:

## 11. Scope Boundaries [Required]

### Expected Areas To Change

- 
- 

### Areas Not Expected To Change

- 
- 

### Out Of Scope

- 
- 

## 12. Architecture And Design [Required]

Describe the intended design.

Include:

- Existing patterns to reuse
- Components affected
- New components required
- Dependencies introduced
- Alternatives considered
- Reason for selected approach

## 13. Data And Persistence Impact [Conditional]

State whether the change affects:

- Domain model
- Database schema
- Migrations
- Seed data
- Queries
- Transactions
- Concurrency
- Backward compatibility

Details:

## 14. API And Contract Impact [Conditional]

State whether the change affects:

- Public API
- Request models
- Response models
- Events
- Messages
- Queues
- Files
- External integrations
- Backward compatibility

Details:

## 15. Security, Privacy, And Authorization Impact [Conditional]

State whether the change affects:

- Authentication
- Authorization
- Roles or permissions
- Secrets
- Tokens
- Personal data
- Audit logging
- Data exposure

Details:

## 16. Runtime, Configuration, And Deployment Impact [Conditional]

State whether the change affects:

- Configuration
- Environment variables
- Feature flags
- Infrastructure
- Deployment pipeline
- Runtime dependencies
- Operational monitoring
- Rollback

Details:

## 17. Implementation Approach [Required]

List the planned steps.

### Step 1

Description:

Requirements covered:

Files or areas:

### Step 2

Description:

Requirements covered:

Files or areas:

### Step 3

Description:

Requirements covered:

Files or areas:

## 18. Validation Plan [Required]

List the validation required before completion.

### Build

Command or method:

Expected result:

### Tests

Command or method:

Expected result:

### Manual Validation

Steps:

Expected result:

### Static Analysis Or Formatting

Command or method:

Expected result:

### Validation Not Required Or Not Possible

Item:

Reason:

Residual risk:

## 19. Documentation Plan [Conditional]

State whether documentation must be updated.

### Required Documentation Updates

- 
- 

### Documentation Intentionally Not Required

Reason:

## 20. Stop Conditions [Required]

The agent must stop if:

- 
- 
- 

Include any project-specific stop conditions.

## 21. Assumptions Accepted For Implementation [Required]

List assumptions explicitly accepted by the human.

- 
- 

No unstated assumption should become implementation.

## 22. Risks [Required]

### Implementation Risks

- 

### Architectural Risks

- 

### Operational Risks

- 

### Review Risks

- 

## 23. Acceptance Criteria [Required]

The change is accepted when:

- 
- 
- 

## 24. Delivered Specification Requirements [Conditional]

For feature work and material behaviour changes, the delivered specification should capture:

- What changed
- Why it changed
- Requirements implemented
- Architectural decisions
- Extension points
- Known limitations
- Technical debt introduced
- Validation performed
- Future considerations

Delivered specification location:

Recommended convention:

- `docs/delivered-specs/YYYY-MM-DD-change-name.md`

## 25. Framework Learning Questions [Optional]

After completion, answer if useful:

- What caused rework?
- What clarification was missed?
- What decision should have been constrained earlier?
- Which assumption was wrong or risky?
- Which repository standard was missing, unclear, or ignored?
- Which agent guidance should be improved?
- Which part of the process created unnecessary friction?

## 26. Approval [Required]

Approval level:

- Approval to investigate:
- Approval to implement:
- Approval to commit, push, deploy, publish, or create a pull request:

Approved by:

Date:

Notes:
