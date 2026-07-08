# Small Change Example

Version: 0.8.3 Draft

## 1. Change Name

Name: Clarify empty project list message

## 2. Objective

Update the empty-state message shown when a user has no projects so it is clearer and less technical.

## 3. Scope

### Expected Files Or Areas

- `src/projects/ProjectListEmptyState.tsx`
- Related snapshot or component test if one exists

### Out Of Scope

- Project creation flow
- Project data model
- API behaviour
- Visual redesign

## 4. Known Context

Relevant instructions, standards, existing patterns, or files:

- Existing empty states use short, action-oriented copy.
- Component text is kept inline unless reused across multiple screens.

## 5. Assumptions

- The change is copy-only unless an existing test snapshot must be updated.
- No accessibility behaviour changes are required.

## 6. Stop Conditions

Stop and ask before implementation if:

- The component is shared outside the project list screen
- The copy is loaded from a translation system
- The change requires modifying project creation behaviour

## 7. Validation

### Commands Or Checks

- Run the component test or snapshot test for the project list empty state.
- If no focused test exists, run the nearest project-list test file.

### Validation Not Required Or Not Possible

Item: Full application regression test

Reason: Copy-only local change

Residual risk: Low; nearby component validation is sufficient.

## 8. Completion Summary

After implementation, capture:

- Files changed
- Final copy used
- Validation performed
- Any snapshot updates
