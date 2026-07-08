# Small Change Template

Version: 0.8.3 Draft

Use this template for narrow, local, reversible changes that do not materially affect architecture, public contracts, persistence, security, runtime configuration, deployment, or cross-cutting behaviour.

If any of those areas are affected, use `plan-template.md` instead.

## 1. Change Name

Name:

## 2. Objective

Describe the outcome to achieve.

## 3. Scope

### Expected Files Or Areas

-

### Out Of Scope

-

## 4. Known Context

Relevant instructions, standards, existing patterns, or files:

-

## 5. Assumptions

List any assumptions that are local, reversible, low risk, and easy to review.

-

## 6. Stop Conditions

Stop and ask before implementation if:

- The change affects architecture, public contracts, persistence, security, runtime configuration, deployment, or cross-cutting behaviour
- Multiple valid interpretations would produce materially different implementations
- Existing repository guidance conflicts
- The implementation would require changing files outside the expected scope
- Required validation cannot be run or interpreted

## 7. Validation

### Commands Or Checks

-

### Validation Not Required Or Not Possible

Item:

Reason:

Residual risk:

## 8. Completion Summary

After implementation, capture:

- Files changed
- Behaviour changed
- Validation performed
- Residual risks or follow-up items
