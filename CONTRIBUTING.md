# Contributing

## Issues

Issues welcome — bug reports, install problems, behavior questions, and feature suggestions. Open one freely; minimal template needed (what you tried, what happened, what you expected).

## Pull requests

Reviewed case-by-case. Small fixes (typos, doc clarifications, broken-link corrections, obvious bugs in skill instructions) are welcome and likely to merge fast. Larger changes — substantive skill rewrites, new skills, structural changes — please open an issue first to align on scope before opening the PR.

## Out of scope

This repo is a curated subset of a larger personal collection of Claude Code skills, many of which are still in-progress experiments. Only skills polished and validated for public use are published here. Requests to publish other skills are welcome as feature requests but treated as low-priority — the curation gap is intentional, not an oversight.

## Maintenance

This public repo is canonical for shipped fixes — bug reports get fixed here. Backports to private dev-staging are at maintainer discretion. Versioning is SHA-driven (no `version` field in `plugin.json`); every commit is a new release for plugin marketplace consumers, so install updates pull the latest published state automatically.
