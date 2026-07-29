# standards — retired

**The fleet's standards live in `~/dev/standards/`.** Start at its `README.md`.

This repo was the first attempt at a rulebook and was superseded in 2026. It is kept only for its
git history; nothing here is current, and nothing new should be added.

## Why it was retired rather than left alone

The name is the problem. Anything searching for "standards" finds this repo, and by the end it was
not merely out of date — it *contradicted* the canonical rulebook on two points that change what
you do:

- **Git flow.** It prescribed `develop`/`master`, `feature/*` and `release/*` branches, and a PR
  review cadence for a team. The fleet is trunk-based: every repo's default branch is `main` and
  all work lands there directly.
- **Conventional commit types.** It listed `feature:`, `bugfix:`, `performance:`, `wip:`, `ops:`.
  The real set is `feat`, `fix`, `perf`. Using `feature:` instead of `feat:` does not fail — it
  silently produces no release, which is the worst possible failure mode for a wrong convention.

The rest was link collections that were never acted on, an empty `python.md` sitting next to a
real one in `~/dev/standards/`, and a release-tooling TODO list long since superseded by
`~/dev/standards/release.md` and actual releases.

One rule was worth keeping and was promoted: column names carry their type in a prefix or suffix
(`is_`/`has_` booleans, `_date`, `_ts`). It now lives in `~/dev/standards/data.md` with its
reasoning.
