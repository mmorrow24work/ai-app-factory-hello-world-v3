# ai-app-factory-hello-world-v3

Create a simple hello-world site to test the ai-app-factory build process Built and evolved via the unattended (Lane B) Claude Code pipeline: label an issue `claude-go` and `.github/workflows/claude.yml` implements it, opens a PR, and records the run in `docs/journal.md`.

**Live site:** <https://mmorrow24work.github.io/ai-app-factory-hello-world-v3/>

This is a disposable test of the ai-app-factory build process, not a maintained
project — it exists to exercise the pipeline end-to-end, not to be kept up over
time. It's the requester-driven counterpart to
[ai-app-factory-hello-world](https://github.com/mmorrow24work/ai-app-factory-hello-world)
(v1): where v1's issues were driven by the repo owner, this repo's issues are
driven by the requester below, who reviews and approves each pull request
themselves. See [`about.html`](about.html) for the full step-by-step trace of
who did what to build this site.

## Requested by

[@mmorrow2012](https://github.com/mmorrow2012), via [ai-app-factory](https://github.com/mmorrow24work/ai-app-factory).

## Viewing locally

Clone the repo and open `index.html` in a browser, or serve the directory with
any static file server, e.g. from the repo root:

```sh
python3 -m http.server
```

then visit `http://localhost:8000/`.

Opening the files directly as `file:///path/to/index.html` isn't a faithful
preview of the deployed site: GitHub Pages serves this project at the
`/ai-app-factory-hello-world-v3/` subpath, not at a domain root. All of this
repo's local references (`style.css`, the `index.html`/`about.html`
cross-link) are relative, so they happen to resolve correctly either way —
but a `file://` preview can't catch a reference that was accidentally written
as an absolute path (e.g. `/style.css` instead of `style.css`), which would
work under `file://` or a root-served local server yet 404 once deployed under
the subpath. Serving locally with the checkout itself placed in a directory
named `ai-app-factory-hello-world-v3` gets closer to the real path shape.

## Support & Handoff

### Support

Open an issue, or comment on an existing one:

- Apply the `claude-go` label (or comment `@claude`) to have the unattended pipeline attempt a fix.
- Mention `@mmorrow24work` for anything the pipeline can't or shouldn't handle unattended — design decisions, ambiguous requirements, anything labeled `lane:manual`.

### Handoff

Once this project's milestones are complete, fork the repo to take ownership.

GitHub forks do **not** inherit the parent repo's Actions secrets, so `claude-go` stops working on the fork the instant it's created — no separate revoke step needed on the original owner's side. To keep the unattended pipeline running, the new owner sets up their own `CLAUDE_CODE_OAUTH_TOKEN`/`GH_PAT` secrets on their fork (same `claude setup-token` / `gh secret set` steps documented in the `ai-app-factory` repo's own `README.md`).
