# Delivered Specification Example

Version: 0.8.1 Draft

This example continues the fictional task management application scenario from `feature-plan-example.md`.

## 1. Change Name

Name: Require project names to be unique per workspace

Date: 2026-06-25

Related plan: `examples/feature-plan-example.md`

## 2. Summary

Project creation now rejects duplicate project names within the same workspace while allowing the same name in different workspaces.

## 3. Why It Changed

Duplicate project names made search, reporting, and support conversations ambiguous.

## 4. Requirements Implemented

- R1: Same-workspace duplicate project names are rejected.
- R2: Cross-workspace duplicate project names are allowed.
- R3: Duplicate-name failures produce a clear field-level validation message.

## 5. Behaviour Delivered

When a user creates a project, the service normalizes the submitted name and checks for an existing project with the same normalized name in the same workspace.

If one exists, project creation fails with:

- `field`: `name`
- `code`: `duplicate`
- `message`: `A project with this name already exists in this workspace.`

## 6. Architecture And Design Decisions

- Reused the existing structured validation error pattern.
- Reused the repository's existing name normalization helper.
- Added persistence enforcement with a unique index on `(workspace_id, normalized_project_name)`.

## 7. Files Or Areas Changed

- Project creation service
- Project validation tests
- Database migration
- Project creation form test

## 8. Extension Points

- Future project rename behaviour should reuse the same uniqueness validation.
- Bulk import should validate duplicate names before inserting records.

## 9. Known Limitations

- Existing duplicate remediation is not included because no duplicates were found during migration precheck.

## 10. Technical Debt Introduced

- None identified.

## 11. Validation Performed

- Focused service tests passed.
- API validation tests passed.
- Migration precheck found no duplicate project names.
- Manual validation confirmed same-workspace duplicate failure and cross-workspace duplicate success.

## 12. Validation Not Performed

Item: Full production-scale load test

Reason: The change uses a scoped unique index and existing project creation flow.

Residual risk: Low; index performance should be monitored if project volume grows substantially.

## 13. Future Considerations

- Apply the same validation to project rename if rename support is added.
- Document project-name normalization if more name-based constraints are introduced.

## 14. Framework Learning

- The plan correctly identified migration data quality as the main stop condition.
- Repository standards should document whether uniqueness constraints require service-layer checks, database constraints, or both.

