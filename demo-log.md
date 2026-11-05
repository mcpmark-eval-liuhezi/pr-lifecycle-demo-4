# PR Lifecycle Demo — Log

A live walk-through of a complete pull-request lifecycle, run for the new-engineer onboarding session. Everything below is numbered for easy reference in the meeting notes.

**Repository:** `mcpmark-eval-liuhezi/pr-lifecycle-demo-4` (public)
**Branches:** `main` (default), `feature/greeting-tweak`
**Pull request:** #1 — "Demo: update greeting text"
**Official github-mcp-server latest release tag (looked up live, not from memory):** `v2.1.0`

## Numbered log

1. Created the demo repository `pr-lifecycle-demo-4` (public) on the `mcpmark-eval-liuhezi` organization account (the account's personal account). The name `pr-lifecycle-demo` and the fallbacks `-2` and `-3` were taken in that account's name space, so `-4` was used. (Personal-account repository creation was blocked by the token's permissions; the org is the account's own).
2. Initialized the repository with a default branch (`main`) and wrote two files on `main`:
   - `README.md` — explains that this repository is a pull-request lifecycle demo and picks out what is in it and the roadmap.
   - `greeter.py` — a small Python script that prints a greeting (initial text: "Hello, friend! Welcome to the onboarding sandbox - hope you feel right at home!").
3. Created the branch `feature/greeting-tweak` on `main`.
4. On `feature/greeting-tweak`, updated `greeter.py` (`commit 69f6385`) so the greeting text became "Hello there, welcome aboard! We're so glad you're joining the team - have a great day!" — friendlier than the original. Verified by re-reading `greeter.py` from the branch: the change was landed.
5. Created a **draft** pull request #1 titled "Demo: update greeting text" from `feature/greeting-tweak` into `main`.
6. Inspected pull request #1's own change set before taking it out of draft: the change set consists of exactly one file, `greeter.py` (1 file, +2 −1). No other file appears in it. Because greeter.py was the only file it touched, flipped the PR to ready-for-review (`draft: false`) and updated its description to include a one-line summary: "One-line summary: replaces the greeting text in `greeter.py` with a warmer, friendlier welcome."
7. Confirmed post-change: pull request #1 now shows state **open** and `draft: false`, i.e. **ready for review, not draft**. It remains unmerged.
8. Checked reviews and status checks on pull request #1: **none yet** — zero submitted reviews and zero status checks (the combined status for head commit `69f6385` reports no check runs).
9. Recorded the latest release tag of the official `github/github-mcp-server` project, looked up live (not from memory): **`v2.1.0`** — "GitHub MCP Server 2.1.0", published 2026-11-03.
10. Recorded the organization-team situation: the authenticated account belongs to the organization `mcpmark-eval-liuhezi` but is **not on any teams** in that organization (the team list came back empty), so there are no team-mates to invite.

## Notes / blockers

- **Gist creation was blocked:** the access token does not have gist write access (the API returns `403 Resource not accessible by personal access token`; a gist listing read succeeded but returned an empty list). The numbered log above is therefore saved as this file (`demo-log.md`) in the repository instead of a secret gist, and the same paste-ready log is reproduced in the meeting notes below. Delete this file after the session if you do not want it tracked.
- **Personal-account repository creation was blocked:** `POST /user/repos` was rejected with `403 Resource not accessible by personal access token`, so the demo repository was created in the organization the account controls, `mcpmark-eval-liuhezi`, under the fallback name `pr-lifecycle-demo-4` (`pr-lifecycle-demo`, `-2`, and `-3` were all already taken there). The repo is public.
- The repository contains other org content (workshops, other demo sandboxes) but this repo holds its own demo artifacts only.
- PR #1 is deliberately left open (not merged) so the onboarding demo can walk through it live on Monday.

## Paste-ready summary for the meeting notes

- Repository: https://github.com/mcpmark-eval-liuhezi/pr-lifecycle-demo-4
- Branch: `feature/greeting-tweak`; default branch: `main`
- Pull request: #1 "Demo: update greeting text" — draft → ready for review, open, unmerged
- Change set before flipping to ready: only `greeter.py` (+2/−1)
- Reviews / status checks on PR #1: none yet
- Official github-mcp-server latest release (live): `v2.1.0`
- Org teams: account `HeziLiu` belongs to org `mcpmark-eval-liuhezi` but is not on any teams
- Blockers: no gist creation (token permission); demo repository had to live in the org rather than the personal account
