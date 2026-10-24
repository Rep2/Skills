---
name: merge-before-testflight
description: >-
  Always merge product changes to the default branch via PR before uploading a
  TestFlight (or equivalent beta) build. Use when shipping TF / beta builds for
  any iOS app project.
---

# Merge before TestFlight

## Rule

**Always merge product changes into the default branch (`main` / `master`) via PR before uploading a TestFlight build.** Never leave TF-only commits sitting only on a feature branch.

Applies to every iOS app project, not a single client repo.

## When this skill applies

- User asks to commit / push / upload TestFlight / ship a new build number
- Preparing any version train for beta or App Store
- Fixing a bug that will go into the next TF build

## Required order

1. Land the product commits on a PR into the default branch (exclude cancelled experiments).
2. Merge the PR; confirm `origin/<default>` has the intended product changes.
3. Cut the TF build **from the merged default branch** (or from a release branch already based on it).
4. Bump marketing/build versions as needed, archive, upload to App Store Connect.
5. Only then update TestFlight / project docs.

## Checks before upload

- [ ] PR merged; default branch contains the fix (not only a feature branch)
- [ ] Soft/cancelled work is **not** reintroduced
- [ ] Version train matches ASC (closed train → bump marketing version)
- [ ] No force-push to the default branch

## Anti-pattern

Uploading a TestFlight build from an unmerged feature branch while `main` still lacks those fixes — always merge first, then treat TF as a build of the default branch.

Example (one-line): EELO TF 1.0.1 was built off an unmerged feature branch; do not repeat that for any project.
