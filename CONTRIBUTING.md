# Contributing

Thanks for taking the time. Small, focused pull requests get merged fastest.

## Before you start

- Open an issue first for anything bigger than a bug fix, so we can agree on the shape.
- Check the README: if it promises something the code does not do, that is a bug report, not a feature request.

## Setup

```
git clone https://github.com/exasyncai/<repo>.git
cd <repo>
python -m pip install pytest
python -m pytest tests -q
```

No build step, no dependencies beyond the standard library unless the README says otherwise.

## Rules that CI enforces

- Tests pass on Linux, Windows and macOS.
- `python tools/check_text.py` passes: no long dashes (U+2013, U+2014) and no internal paths in any text file. Use a comma, a colon or a hyphen instead.
- No secret, customer name, real mailbox, hostname or personal path in code, tests, fixtures or commit messages. gitleaks scans the full history on every push.
- GitHub Actions are pinned to a commit SHA. Dependabot updates the pins.

## Commit messages

Conventional style, lower case, imperative: `feat: ...`, `fix: ...`, `docs: ...`, `tests: ...`, `chore: ...`. The first line explains what changed and why in plain words; the PR carries the discussion.

## Pull requests

- One topic per PR. Squash-merge is the default, so intermediate commits do not need to be pretty.
- Fill in the PR template and set one label for the release notes (`feature`, `fix`, `security`, `documentation`, `breaking`).
- A maintainer reviews within a few working days. We may ask for a test that reproduces the bug before the fix.

## Releases

Maintainers tag `vX.Y.Z` on `main`. The release workflow builds the archives, writes `SHA256SUMS`, attests provenance and publishes the GitHub Release with generated notes. Installers only ever fetch tagged releases.

## Code of conduct

This project follows the [Contributor Covenant](CODE_OF_CONDUCT.md). Be kind, assume good faith, keep it about the code.
