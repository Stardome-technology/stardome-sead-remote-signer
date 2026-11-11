# AGENTS.md

## Hard rules

1. This is the **public mirror** of `stardome-sead-remote-signer-private`
   (GitLab). Content lands here from the private repo — do not develop features
   directly on this mirror.
2. The remote signer is a **software attestation class** (schema 2.0.1) — its
   output must never be presented or verifiable as a hardware attestation.

## OpenSpec skills — human sessions only

The `.github/skills/openspec-*` and `.github/prompts/opsx-*` shipped here are
for **human interactive sessions on machines that have the `openspec` CLI**
(the Hermes orchestrator). The benches deliberately do NOT install openspec
(`which openspec` must print nothing) — decision 2026-11-11, D8.

Kanban/bench agents: **ignore these skills.** Work from the change's `tasks.md`
(plain markdown) per `strix.md` § OpenSpec conventions. Never run the `openspec`
CLI; never create, archive, or sync changes/specs — authoring is human work and
archiving is the orchestrator's `__close-digest__` card job.

<!-- git-workflow: v1 -->
## Git workflow
- forge: github                # github | gitlab
- status: development          # production | development | fork-submodule
- default branch: dev
- main/master are promotion staging only: updated exclusively by the dev→main squash
  (use whichever of main/master the repo already carries; do not create the other)
- one unit of work = one short-lived branch, spun from origin/dev:
  - feat/<short-descriptive-name>   # features; OpenSpec change ⇒ feat/<change-id>
  - bug/<short-descriptive-name>    # bug fixes
- merge back: squash PR/MR into dev, then delete the work branch
- promotion to production: squash dev→main (or dev→master), tag it, then replace this
  section with the production (GitHub Flow) variant
- after a squash-merge: do NOT re-merge old branches (tips are not ancestors of the
  default branch); refresh with `git fetch --prune && git reset --hard origin/<default-branch>`
- NEVER:
  - push directly to a protected branch
  - force-push a protected branch
  - reuse an already-merged branch
  - commit directly into main/master
