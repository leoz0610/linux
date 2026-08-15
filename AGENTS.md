# Repository Instructions for Codex

## Branch Policy

- `master` mirrors the source branch and must remain free of personal changes.
- `main` is the trunk branch for this fork. Put repository guidance and other
  intentional long-lived changes on `main`.
- Create topic branches from `main` for non-trivial work. Use the `codex/`
  prefix for branches created by Codex.
- Target `main` as the base branch for future pull requests unless the user
  explicitly requests a different base.
- Never merge, rebase, reset, force-push, or update `master` unless explicitly
  requested.
- Do not commit, push, or create a pull request unless explicitly requested.
- Before changing files, inspect the current branch and worktree state. Do not
  discard or overwrite unrelated user changes.

## Working Style

- Follow the Linux kernel coding style and the guidance in
  `Documentation/process/`.
- Prefer small, reviewable patches and follow subsystem-local conventions.
- Locate the relevant maintainers, documentation, nearby implementations, and
  tests before designing a change.
- Use `scripts/checkpatch.pl` for new patches when practical.
- Run the narrowest relevant build or test first, then expand validation in
  proportion to the change.
- Report exactly what was tested, what passed, and what was not run.
- Do not add generated files, build output, downloaded dependencies, or large
  binary artifacts to Git.

## Hands-On Lab Policy

- For every lab exercise, show the complete commands used so the user can
  reproduce the work manually. Include host setup, build, VM launch, commands
  run inside the guest, verification, and cleanup commands when applicable.
- Present commands in execution order and identify the environment for each
  command, such as the macOS host, build VM, or test VM. Do not replace
  essential commands with prose, ellipses, shell-history references, or
  unstated prior setup.
- Make command examples copy-pasteable. Define paths and other values before
  using them, and clearly mark any value the user must replace.
- Before a command that partitions, formats, overwrites, deletes, or otherwise
  mutates persistent data, identify the exact target and explain the effect.
  Keep destructive lab operations confined to explicitly disposable devices
  or files.
- After each command group, state the expected observable result and include
  commands that verify it. If Codex used a different diagnostic command while
  troubleshooting, show that command and its relevant result as part of the
  lab record.

## Platform Note

This checkout may be used on a case-insensitive filesystem. The Linux tree has
tracked paths that differ only by capitalization, so Git may report apparent
modifications or checkout collisions for those paths. Treat them as platform
artifacts and do not stage, restore, or modify them unless explicitly asked.

See `CODEX.md` for the repository workflow and validation guide.
