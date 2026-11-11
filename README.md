# Human-Agent Development Framework

[![Status: Draft](https://img.shields.io/badge/status-draft-orange?style=flat)](#status)
[![Version: 0.8.4](https://img.shields.io/badge/version-0.8.4-blue?style=flat)](CHANGELOG.md)
[![Licence: CC BY 4.0](https://img.shields.io/badge/licence-CC_BY_4.0-green?style=flat)](LICENSE)
[![Documentation](https://img.shields.io/badge/docs-website-555?style=flat)](https://rich-mond.github.io/human-agent-development-framework/)

Version: 0.8.4 Draft

The Human-Agent Development Framework (HADF) is a practical collaboration model for humans and AI coding agents.

It is designed to reduce avoidable implementation loops by making decisions, assumptions, evidence, uncertainty, and ownership visible before they become code.

## What Problem This Solves

AI coding agents can produce code quickly, but the expensive part of agent-assisted development is often not generation. It is convergence: the work required to move from an initial request to an accepted, maintainable implementation.

HADF helps teams reduce convergence cost by defining:

- How humans and agents share responsibility
- How decisions should be owned
- How uncertainty should be surfaced
- How repository standards and existing patterns should guide implementation
- When agents should ask, proceed, stop, validate, or document

Convergence cost can come from unclear requirements, poor decisions, execution or verification failures, and unnecessary implementation or process complexity. Success requires correct, maintainable delivery that humans understand, with proportionate verification and low avoidable rework and cost.

## A Practical Example

In the fictional [archived-project example](examples/messy-ambiguity-example.md):

- **Initial request:** "Make archived projects disappear from the project list."
- **Clarification:** "Should they be hidden only from the default list, or should search, API responses, reports and other access paths change too?"
- **Illustrative human decision:** "Hide them from the default list only. Leave search, reports, APIs and archive management unchanged."
- **Result:** The implementation scope is explicit, reducing the risk of unintended changes elsewhere. Correct implementation still needs proportionate verification.

## Who This Is For

This framework is intended for:

- Software teams using AI coding agents in real repositories
- Engineers who want higher first-pass acceptance from agent-assisted work
- Technical leads defining agent operating standards
- Teams that want agent speed without losing architectural control or human understanding

## Repository Contents

- [framework.md](framework.md) - the core framework
- [ADOPTION.md](ADOPTION.md) - practical adoption guidance for teams
- [CHANGELOG.md](CHANGELOG.md) - deliberate versioned changes to the framework and templates
- [LICENSE](LICENSE) - license notice and attribution guidance
- [PUBLICATION-CHECKLIST.md](PUBLICATION-CHECKLIST.md) - checks for coherent public draft and stable releases
- [CONTRIBUTING.md](CONTRIBUTING.md) - contribution and feedback guidance
- [examples/](examples/README.md) - compact worked examples, including one ambiguity example
- [templates/agents-template.md](templates/agents-template.md) - a template for repository-specific agent operating guidance
- [templates/plan-template.md](templates/plan-template.md) - a decision-complete implementation plan template for material changes
- [templates/small-change-template.md](templates/small-change-template.md) - a lightweight template for narrow, reversible changes
- [templates/delivered-spec-template.md](templates/delivered-spec-template.md) - a template for capturing what was actually delivered

## Start Here

Choose the entry point that fits your work:

- **Exploring:** Read the [framework](framework.md), then see the [archived-project ambiguity example](examples/messy-ambiguity-example.md).
- **Trying HADF:** Follow [Day 1 adoption](ADOPTION.md#day-1-adoption), copy and customise the [agent guidance template](templates/agents-template.md) as `AGENTS.md` or equivalent, and use the [small-change template](templates/small-change-template.md) for narrow, reversible work.
- **Planning material work:** Consult the [planning guidance](ADOPTION.md#minimum-viable-feature-plan), use the [full plan template](templates/plan-template.md) when justified by the change, and refer to the [feature-plan example](examples/feature-plan-example.md).

After material changes, use the [delivered-specification template](templates/delivered-spec-template.md) to capture what was built. See the [examples overview](examples/README.md) for the expected level of detail.

## Adoption Modes

### Lightweight Adoption

Use the agent operating guidance and small-change template only.

This is appropriate when teams want better agent behaviour without introducing a full planning process.

### Standard Adoption

Use the framework, agent operating guidance, small-change template, and plan template.

This is appropriate for teams using agents regularly across production code.

### Full Adoption

Use the framework, all templates, delivered specifications, and framework learning notes.

This is appropriate for teams that want to continuously improve agent-assisted delivery quality over time.

## Core Idea

Unresolved decisions create a risk of unauthorised assumptions; they do not transfer authority to the agent.

HADF supports delivery by making material decisions explicit with the right owner, then checking the implementation against approved requirements. Better planning reduces uncertainty but cannot guarantee correct execution.

The framework treats delivery as a convergence process:

1. Form a cohesive specification
2. Produce a guardrailed first-pass implementation
3. Validate and improve through focused loops
4. Learn what to clarify, correct, simplify, remove, or accept; add controls only when justified

```mermaid
---
config:
  look: handDrawn
  theme: base
  themeVariables:
    primaryTextColor: "#303a47"
    textColor: "#303a47"
    lineColor: "#596576"
    edgeLabelBackground: "#f5f0f7"
---
flowchart TB
    subgraph S[Specification creation]
        direction LR
        S1[Intent] --> S2[Clarify] --> S3[Decide] --> S4[Validate feasibility]
        S4 -. gaps .-> S2
    end

    subgraph I[Implementation]
        direction LR
        I1[Guardrailed first pass] --> I2[Validate] --> I3[Review] --> I4[Refine]
        I4 -. not done .-> I2
    end

    D[Delivered specification]
    G[Proportionate improvements]

    S -->|feasible spec| I
    I -->|accepted| D
    D --> G

    classDef default fill:#fffdf8,stroke:#73808d,color:#303a47
    classDef learning fill:#fff1e6,stroke:#b9a18b,color:#303a47
    class D,G learning
    style S fill:#f7f1fa,stroke:#bcaed0,color:#303a47
    style I fill:#f0f7fb,stroke:#b2c7d8,color:#303a47
```

## Status

This repository is currently a public draft.

The framework is usable, but the language, templates, and repository structure may continue to evolve before a stable `1.0` release.

## License

This draft is licensed under the Creative Commons Attribution 4.0 International License.

Copyright (c) 2026 Alan Cavanagh.

You may copy and adapt HADF templates, including for commercial use, subject to [LICENSE](LICENSE) and [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Give reasonable attribution identifying the original work and author, linking to the source and licence, and stating whether you made changes. Retain any existing modification notices. Attribution must not suggest endorsement by the author.

Attribution need not appear inside every copied template. An acknowledgement in repository documentation or a third-party notices file may be appropriate, depending on how the material is reused. One example you can adapt:

> Templates adapted from the [Human-Agent Development Framework (HADF)](https://github.com/rich-mond/human-agent-development-framework), Copyright (c) 2026 Alan Cavanagh, licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Modified for this repository.
