# .github

Fælles skabeloner, retningslinjer og workflows for **alle** Koadic-repoer.

## Hvad der ligger her

| Fil | Hvad den gør |
|---|---|
| `CONTRIBUTING.md` | de seks trin fra ændring til kunde |
| `SECURITY.md` | hvor sårbarheder meldes |
| `CODEOWNERS` | hvem der ejer hvad |
| `profile/README.md` | organisationens forside på GitHub |
| `.github/ISSUE_TEMPLATE/` | fejl, funktion, opgave |
| `.github/PULL_REQUEST_TEMPLATE.md` | spørgsmålene, en PR skal svare på |

## Fælles workflows

To workflows kaldes fra de andre repoer, så reglerne kun står ét sted:

```yaml
jobs:
  port:
    uses: Koadic-Developments/.github/.github/workflows/faelles-port.yml@main

  forhaandsvisning:
    uses: Koadic-Developments/.github/.github/workflows/forhaandsvisning.yml@main
    with:
      system: design
```

| Workflow | Hvad |
|---|---|
| `faelles-port.yml` | syntaks, fejlfindingsrester, `exit('tekst')`, UTF-8 |
| `forhaandsvisning.yml` | `pr-<n>-<system>.koadic.dk` pr. åben PR |

## Bemærk: repoet er privat

GitHub bruger kun en fælles `SECURITY.md` og `CONTRIBUTING.md` fra `.github`,
**hvis det repo er offentligt**. Vores er privat, så filerne her gælder ikke
automatisk de andre repoer — de har hver deres kopi.

Gøres repoet offentligt en dag, kan de kopier fjernes igen. Workflows virker
uanset, fordi adgangen er sat til organisationen.

---
© 2026 Koadic Developments
