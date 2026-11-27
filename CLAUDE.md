# cococolacake.party

Coco's website: one `index.html` and an `assets/` folder, served by GitHub Pages from `main` at cococolacake.party. Cloudflare is the domain registrar and DNS only. No build step, tests or releases. This file is how each change gets made.

## Workflow

Every change follows these steps. Coco is new to git: explain git and terminal steps simply, one at a time.

1. **Issue.** Every change starts as a GitHub issue.
   - Features: use the `grilling` skill to interview Coco until the plan is settled, write the plan into the issue, and wait for Coco to approve it (label `ready`).
   - Tiny fixes (a typo, a colour, a one-line bug): a two- or three-line plan in the issue is enough.
   - Before posting a plan, check each worked example in it (a rounding, a before and after) against the rule it illustrates.
   - Issues opened by other people: label and summarize them. Build nothing until Coco picks one.
2. **Build** on a branch named after the issue, e.g. `42-new-project-card`, starting from the latest `main` on GitHub rather than Coco's local folder.
3. **Review.** A subagent that didn't write the code runs `code-review` on the branch, against the issue and "Keep it lean" below. Fix what it finds, or say why not.
4. **Coco tests it.** Wait for Coco's OK before opening the PR.
5. **PR.** Put `Fixes #<issue>` in the PR description. Merging to `main` publishes the site.
   - Commit as `Coco <183875663+cococolacake@users.noreply.github.com>`.
   - Commits and PRs carry no AI attribution lines and no session links.
   - Coco merges.
6. **Wrap-up.** Comment on the issue with what's done and what's left, plus a short retro: what went wrong and what would prevent it. When something went wrong more than once, suggest a change to this file.

## Keep it lean

- Build exactly what the issue asks for. Put other ideas in the PR description as suggestions.
- Comments explain why, never what.
- Add a helper, option or flag only when something uses it now.
- Handle the errors that can really happen and let the rest surface.
- Remove unused CSS, debug logging and commented-out code before review.
- Reuse an existing helper before writing a new one.
- Fluff you spot outside the issue goes in the PR description, for its own `cleanup` issue.

## Rules for this repo

- Labels and buttons explain themselves. Skip hint text that repeats a label.
- Write without em dashes.

## Agent skills

### Issue tracker

Issues live in this repo's GitHub Issues, used through the `gh` CLI. See `docs/agents/issue-tracker.md`.

### Triage labels

needs-plan, needs-info, ready, ready-for-human, wontfix, with bug, feature, polish and cleanup for the type. See `docs/agents/triage-labels.md`.

### Domain docs

Single-context: `CONTEXT.md` and `docs/adr/` at the repo root. See `docs/agents/domain.md`.
