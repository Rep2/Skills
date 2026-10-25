---
name: merge-before-testflight
description: >-
  Always merge product changes to the default branch via PR before shipping any
  build — TestFlight, Play Store, web deploy, or equivalent. Use when uploading
  betas, store builds, or production releases for any project.
---

# Merge before ship

## Rule

**Always merge product changes into the default branch (`main` / `master`) via PR before shipping any build** (TestFlight, Play Store, web deploy, or equivalent). Never leave release-only commits sitting only on a feature branch.

Applies to **every project** (iOS, Android, web, and others) — not a single platform or client repo.

## When this skill applies

- User asks to commit / push / upload / deploy / ship a new build or release
- Preparing any beta, store, or production train
- Fixing a bug that will go into the next shipped build

## Required order

1. Land the product commits on a PR into the default branch (exclude cancelled experiments).
2. Merge the PR; confirm `origin/<default>` has the intended product changes.
3. Cut the ship build **from the merged default branch** (or from a release branch already based on it).
4. Bump versions as needed; upload/deploy to the target channel (ASC / Play / web host / etc.).
5. Only then update release / project docs.

## Checks before ship

- [ ] PR merged; default branch contains the fix (not only a feature branch)
- [ ] Soft/cancelled work is **not** reintroduced
- [ ] Version / train matches the store or deploy target (closed train → bump)
- [ ] No force-push to the default branch

## Anti-pattern

Shipping a TestFlight, Play, or web build from an unmerged feature branch while `main` still lacks those fixes — always merge first, then treat the release as a build of the default branch.
