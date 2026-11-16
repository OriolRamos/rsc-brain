# This fork

`OriolRamos/rsc-brain` is the source its owner installs and updates rsc-brain from. It follows
[ericrisco/rsc-brain](https://github.com/ericrisco/rsc-brain) without waiting for it:

- **Releases come from here.** A version is a tag `vX.Y.Z` on `main` with a GitHub release that carries
  `rsc-brain.sh` (from `deploy/`) and its SHA-256 in the notes, as upstream does. Installs point at this repository
  (`rsc-brain.sh install --repo https://github.com/OriolRamos/rsc-brain.git`), so `update` fetches these tags.
- **Version numbers.** Starting from an upstream version, a release that adds this fork's own changes takes the next
  patch number (`v0.7.0` + fixes = `v0.7.1`). When upstream publishes a version, merge its tag into `main`. If that
  version is newer than the last one here, release it under its own number. Otherwise, release the next patch.
  Updates only move forward.
- **Fixes go upstream too.** Each change made here is also offered upstream as a pull request. Once upstream has it,
  the fork's copy disappears in the next merge.
- **Watching upstream.** `.github/workflows/upstream-watch.yml` runs every Monday (and by hand). It keeps one open
  issue, labelled `upstream`, that lists the upstream commits and tags not yet in `main`. It closes that issue when
  nothing is left. Nothing merges by itself: a person reads the issue and decides.

## Changes carried here

| Change | Upstream PR | In release |
|---|---|---|
| Approve proposals whose new pages link each other (`src/domain/wiki/apply.ts`) | ericrisco/rsc-brain#53 | v0.7.1; upstream's rework of it in v0.7.2 |
