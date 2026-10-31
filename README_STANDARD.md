# Repository README standard

Every repository README should feel part of the same organization while
remaining specific to the product in that repository. Use the presentation
strengths of the Koadic Developer Platform and Multica references: clear
identity, a useful one-sentence description, grouped capabilities, a path to
get started, and links to the right documentation.

The reference repositories are examples of structure, not sources of product
claims. Do not copy their feature lists, badges, screenshots, architecture,
license statements, or setup instructions into another repository.

## Recommended order

1. Product name, logo if licensed, and one-sentence value proposition.
2. Product status and the intended audience.
3. Capabilities that exist in the current code, grouped by user outcome.
4. A short getting-started path with verified prerequisites and commands.
5. Configuration and secret handling, naming variables but never showing
   secret values.
6. Architecture and integrations, only where they help an operator or
   contributor.
7. Deployment, release verification, and rollback guidance.
8. Security reporting, support, license, and links to deeper documentation.

## Accuracy rules

- Verify commands, environment variable names, domains, and release behavior
  against the current repository and deployment configuration.
- Distinguish implemented, planned, internal, and publicly available features.
- Do not claim an integration, security control, uptime level, privacy
  guarantee, or compliance status without current evidence.
- Do not expose private URLs, customer information, tokens, credentials, or
  production configuration values.
- Preserve upstream notices, product names, logos, and license obligations.
- Keep badges only when they point to a real workflow or release source.
- Do not say a system is live just because its source code contains a domain.

## Review before publishing

Compare the README with the current implementation, configuration, and
deployment workflow. Confirm that links and commands are valid, that no
secrets or internal-only details are exposed, and that licensing and third-
party attribution are preserved. For the organization profile, review every
product and security statement as public-facing material.
