# Public Release Checklist

Use this checklist before promoting a new public draft or stable release.

The repository is already public, so this checklist is no longer about first publication. It is about keeping each public release coherent, consistent, and usable.

## Current Public State

- Repository: `https://github.com/rich-mond/human-agent-development-framework`
- Pages site: `https://rich-mond.github.io/human-agent-development-framework/`
- Current draft: `0.8.3 Draft`
- License: Creative Commons Attribution 4.0 International
- Copyright: Alan Cavanagh
- Public feedback: issues and pull requests are guided by `CONTRIBUTING.md`

## Before Each Draft Release

- Confirm all active version markers match the intended draft version
- Update `CHANGELOG.md` with deliberate framework, template, example, site, or packaging changes
- Review `README.md` for accurate Start Here guidance and repository contents
- Review `ADOPTION.md` for current adoption guidance
- Review `framework.md` for clarity, concision, and duplication
- Review templates for consistency with the framework
- Review examples for usefulness and version alignment
- Review `docs/index.html` for current version, links, and public positioning
- Confirm `docs/robots.txt` and `docs/sitemap.xml` still point to the correct Pages URL
- Check for private notes, internal references, secrets, credentials, signed URLs, or local-only configuration
- Confirm the working tree is clean before tagging
- Create an intentional commit for the release
- Create and push a version tag when the release should be referenceable

## Before Stable 1.0

- Decide whether to create a GitHub Release in addition to tags
- Decide whether the framework needs a stable versioning policy
- Decide whether examples are sufficient for first-time adopters
- Confirm the license is still appropriate for public reuse
- Confirm contribution expectations are clear enough for public issues and pull requests
- Review whether the framework makes proportionate claims and remains positioned as practical guidance rather than a definitive standard

## Optional Promotion Tasks

- Add or update repository topics
- Confirm the GitHub repository About description and website URL
- Confirm GitHub Pages is deployed from `main` and `/docs`
- Confirm Google Search Console verification still works
- Submit or resubmit the sitemap after material Pages changes
- Consider writing a short announcement post for major draft or stable releases
