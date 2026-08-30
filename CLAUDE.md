# personality-ai

<!-- What is this repository, what does it deploy to, and what must an agent
     not break? Two or three sentences from somebody who knows is worth more
     than everything below, which is only what is true everywhere. -->

_Not yet described. The house rules below are estate-wide and were synced
here; what makes this repository different is still to be written._

<!-- estate:house-rules -->
<!-- Synced from flashyos/tools/estate-house-rules.mjs. Edit it there, not here.
     Anything outside these two markers is this repository's own and is never
     touched by the sync. -->

## House rules — true in every repository in this estate

**`main` is not necessarily the default branch.** Eleven of thirty-five
repositories deploy from a `claude/*` branch. Ask, every time:

```bash
git symbolic-ref --short refs/remotes/origin/HEAD
```

Work pushed to `main` in one of those deploys nothing and is read by nobody,
and the failure is silent — the push succeeds.

**Say which branch you measured.** Reading `git ls-files` or the working tree
tells you about your checkout, not about the repository. That mistake reported
the estate's secret scanning as 35/35 when it was 15/35, and was then made a
second time, in a different tool, by a different agent, four hours later. If a
claim is about what ships, read the ref.

**Re-vendor before you trust a vendored change.** Files named `vendor-*.mjs`
are copies of a package in flashyos. Changing the source does nothing here
until the copy is replaced, and a stale copy does not fail — it disagrees,
silently, about whichever field somebody has just changed.
`node tools/estate-hygiene.mjs` in flashyos reports every copy that has
drifted.

**No secret in a file, a repo, or an artifact.** Secret Manager only. A
committed credential is burned the moment it lands and stays burned after the
file is deleted, because history keeps it — removal is not rotation.

**The licence is declared once**, in `tools/estate-licences.mjs` in flashyos,
along with the copyright holder. Do not decide a repository's licence inside
that repository. Client work is never open-licensed: the grant is not ours to
make.

**A generated file is regenerated, never hand-edited.** `shiplog.fragment.json`,
`backlog.fragment.json`, built `public/` directories and lockfiles are outputs.
Editing one is a change that the next run silently discards.

**Report what happened, including when it is worse than expected.** A number
somebody assumed is worth less than a number somebody measured, and a
measurement nobody checked is an opinion with a progress bar.
<!-- /estate:house-rules -->
