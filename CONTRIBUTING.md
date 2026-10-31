# Engineering at Koadic

This guide describes how a change moves from an idea to production. It is a
practical, lightweight version of a Secure Development Lifecycle (SDL) and a
Safe Deployment Process (SDP). The safeguards should match the risk of the
change; routine work should not create unnecessary CI or monitoring noise.

## 1. Define the change

Before implementation, record the user problem, expected result, affected
systems, acceptance criteria, and any data, access, privacy, or availability
risks. For small fixes, a concise issue or pull request description is enough.
For changes that affect authentication, payroll, personal data, permissions,
or production infrastructure, document the design and rollback path before
implementation.

## 2. Make the change in a branch

Create a focused branch from `main` and keep the pull request limited to one
related change. Never put credentials, personal data, or production exports in
Git. Use least-privilege credentials and validate untrusted input at the
boundary where it enters the system.

## 3. Open a pull request and review evidence

The pull request should explain what changed, why, how it was checked, and how
to deploy or roll back. Reviewers should focus on behavior, security, data
handling, accessibility where relevant, and unintended effects on other
systems.

Repository-specific PR checks should run when a pull request is opened or
updated. Keep checks relevant to the changed code, such as syntax, typecheck,
build, focused tests, secret scanning, or dependency review. Do not add
scheduled uptime checks or recurring drift scans to GitHub Actions. Production
service monitoring belongs in the existing Better Stack setup.

Required checks must report on the latest commit. A green check is evidence
only for what that check actually ran; it does not prove a deployment or a
working production flow.

## 4. Verify in preview or staging

For user-facing or production-sensitive changes, deploy to an isolated preview
or staging environment and verify the affected flow there. Confirm the
environment, data source, and configuration are the intended ones. Record the
result and any limitations in the pull request. Documentation-only changes do
not need a product preview.

## 5. Approve and release

After the PR checks and review evidence are satisfactory, merge the change
through the repository's protected-branch process. Production releases should
be a distinct step from merging. A release owner confirms the target, impact,
deployment order, and rollback plan before a high-impact change goes live.

Where a system supports it, release first to an internal or limited group,
observe it, then expand the rollout. Small systems without release rings can
use a staging check followed by an explicit production release and a short
post-deploy verification.

## 6. Verify and learn

After deployment, verify the changed flow in the real target environment and
check the relevant Better Stack service or incident view. For an incident,
record impact, cause, mitigation, and a follow-up action. Avoid adding
duplicate polling jobs to GitHub Actions when an existing monitor or heartbeat
can cover the need.

## Pull request checklist

- [ ] The change and expected behavior are clear.
- [ ] Relevant PR checks passed, or the reason a check does not apply is stated.
- [ ] Security, privacy, access, and data effects were considered.
- [ ] Preview or staging verification is recorded when the change needs it.
- [ ] Deployment order and rollback are documented for production-sensitive changes.
- [ ] Production verification is planned and has an owner.

## Review model

Code review and release approval serve different purposes. A code reviewer
checks the proposed change. A release owner decides whether and when the
verified change should reach production. Require an independent reviewer for
high-risk changes when one is available. Do not make a second-person approval
a blanket requirement if the team cannot reliably provide it; record the risk
and use a release checklist instead.
