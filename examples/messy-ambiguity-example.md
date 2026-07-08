# Messy Ambiguity Example

Version: 0.8.2 Draft

This example shows how HADF handles a request that looks simple but contains hidden product, data, and operational decisions.

## Initial Request

> Make archived projects disappear from the project list.

## Initial Classification

Initial classification: Investigation

Reason:

The request sounds like a small UI change, but "disappear" could mean hidden from one screen, excluded from search, unavailable through API responses, removed from reports, or soft-deleted.

## Discovery

Evidence reviewed:

- Project list UI filters active projects client-side.
- Search results come from a separate API endpoint.
- Reports include archived projects for historical accuracy.
- Existing project records have an `archived_at` field.
- No repository standard defines archive visibility rules.

## Proven

- Archived projects are still valid project records.
- The project list and search use different data paths.
- Reports intentionally include historical project data.

## Inferred

- The likely user intent is to hide archived projects from the default project list, not remove them everywhere.
- Search and reporting behaviour require explicit product decisions.

## Unknown

- Whether archived projects should appear in search.
- Whether users need a way to view archived projects.
- Whether API consumers expect archived projects in default responses.

## Stop Decision

The agent should not implement the initial request yet.

Reason:

Multiple valid interpretations would produce materially different behaviour.

## Clarification Needed

Decision required:

- Should archived projects be hidden only from the default project list?
- Should there be a "show archived" control?
- Should archived projects remain searchable?
- Should API default responses change?
- Should reports continue including archived projects?

Recommended path:

Treat this as feature work unless the human explicitly narrows the request to a local UI-only filter.

## Accepted Narrow Scope

If the human clarifies:

> Hide archived projects from the default project list only. Do not change search, reports, API contracts, or archive management.

Then classification may become: Small Change

Proceeding assumption:

- Existing archived projects remain accessible through existing non-list routes.

Stop conditions:

- The project list API must change.
- Search behaviour must change.
- No existing test can distinguish archived from active projects.

## Framework Learning

This request reveals a missing repository standard:

- Archive visibility rules should be documented by surface: list, search, reports, API, and exports.

Adding that standard would reduce future implementation loops around archived data.

