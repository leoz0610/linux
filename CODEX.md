# Codex Guide for This Linux Fork

## Repository Workflow

`master` is the source branch. `main` is the personal trunk and the default
base for future pull requests. Start normal work on a short-lived topic branch
created from `main`, and keep `master` free of personal commits.

For work intended for a pull request:

1. Update local branch information as requested.
2. Create a `codex/<topic>` branch from `main`.
3. Make and validate a focused change on that topic branch.
4. Open the pull request against `main` unless another base is explicitly
   requested.

Do not commit, push, rewrite branches, or open pull requests without explicit
authorization.

## Linux Development Guide

- Read `Documentation/process/coding-style.rst` and the applicable subsystem
  documentation before making broad changes.
- Use `scripts/get_maintainer.pl` to identify subsystem ownership when useful.
- Match nearby naming, locking, lifetime, error-handling, and logging patterns.
- Consider concurrency, memory ordering, ABI compatibility, userspace-visible
  behavior, and cleanup paths for every kernel change.
- Prefer existing test infrastructure under `tools/testing/`, KUnit, selftests,
  or subsystem-specific tests.
- Build the narrowest relevant target first and clearly distinguish compile
  validation from runtime or hardware validation.

## Checkout Characteristics

This repository was initially cloned with `--depth 1` from `master`. If work
requires older history, deepen it deliberately with `git fetch --deepen <n>` or
obtain full history with `git fetch --unshallow`.

On a case-insensitive filesystem, some tracked Linux paths collide by case.
Ignore the resulting pre-existing worktree noise unless the task specifically
concerns those files.
