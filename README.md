# Koadic organization standards

This repository holds shared guidance and templates for Koadic Developments.
It is not a product repository. Each product repository should document its
own purpose, setup, configuration, and release process.

## Contents

| Path | Purpose |
| --- | --- |
| `CONTRIBUTING.md` | Development, review, and release guidance |
| `SECURITY.md` | Private vulnerability reporting instructions |
| `README_STANDARD.md` | Product-specific README structure and accuracy rules |
| `CODEOWNERS` | Repository ownership rules |
| `profile/README.md` | Draft organization profile for GitHub |
| `.github/ISSUE_TEMPLATE/` | Issue templates |
| `.github/PULL_REQUEST_TEMPLATE.md` | Pull request checklist |
| `.github/workflows/` | Shared CI and preview workflows |

## Shared workflows

Other repositories can call the reusable workflows in this repository. These
are event-driven workflows, not recurring uptime or drift checks. The
`faelles-port.yml` workflow provides the shared PHP and shell checks. The
`forhaandsvisning.yml` workflow manages an isolated pull request preview for
repositories configured to use it.

```yaml
jobs:
  port:
    uses: Koadic-Developments/.github/.github/workflows/faelles-port.yml@main
```

Callers should choose checks that fit their language and runtime. Do not add
scheduled operational monitoring to GitHub Actions; use the existing
monitoring service for that purpose.

## Visibility

This repository is currently private. GitHub does not publish
`profile/README.md` as the organization profile while this repository is
private. The profile draft must be reviewed alongside repository contents and
workflow security before changing visibility.
