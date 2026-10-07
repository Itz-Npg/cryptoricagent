# cryptoricagent

Documentation site for **`cryptoricagent`** — the Cryptoric Chan command line:
the same staged agent pipeline that runs inside the Cryptoric Agent desktop app,
headless.

## The source code is not in this repository

This repository publishes the page you are reading and nothing else. The
implementation lives in the project the CLI belongs to:

**→ [Itz-Npg/Cryptoric-Agent](https://github.com/Itz-Npg/Cryptoric-Agent)** — the
CLI is in [`cli/`](https://github.com/Itz-Npg/Cryptoric-Agent/tree/main/cli)

That is not a filing preference, it is a dependency: the CLI bundles itself from
that repository's `src/main/` — the agent runtime, the stage pipeline, the tool
layer, the permission policy and the system prompts are the same source files
the desktop app uses. A copy of `cli/` alone would not build, which is why there
is no copy here.

| | |
|---|---|
| Package | [`cryptoricagent`](https://www.npmjs.com/package/cryptoricagent) |
| Command | `cryptoric` |
| Source | [Itz-Npg/Cryptoric-Agent](https://github.com/Itz-Npg/Cryptoric-Agent) (`cli/`) |
| Site | https://itz-npg.github.io/cryptoricagent/ |
| Node | 20.11 or newer |
| Licence | MIT © 2026 Itz-Npg |

## Install

```bash
npm install -g cryptoricagent
cryptoric doctor
```

## What is in here

| File | What it is |
|---|---|
| `index.html` | The whole site. Hand-written. |
| `styles.css` | The only stylesheet. |
| `.github/workflows/pages.yml` | Publishes the site to GitHub Pages on every push to `main`. |

There is no build step, no framework, no bundler and no dependency. The CSS
carries the application's own design tokens, so the page reads as part of the
product rather than as a separate website.

The page makes **no third-party request**: fonts are the system stack, the script
is inline, and there is no font CDN, no analytics and no telemetry. The one
remote asset is the terminal capture, which is served by GitHub from the source
repository so it cannot silently go stale — that repository's CI regenerates it
and fails if the committed copy stops reproducing.

## Status

The first npm release is **staged and awaiting approval**. Staging is npm's own
gate on a brand-new package name: the name resolves to a `0.0.0-stage`
placeholder until a maintainer approves the real version with two-factor
authentication. Until that approval, `npm install -g cryptoricagent` installs the
placeholder and installs no `cryptoric` command.

Everything else on the site is drawn from the source repository's own
documentation and its test suite, and the exit codes, flags and environment
variables are the ones the code actually implements.

## Editing

Change `index.html` and `styles.css` and push to `main`. There is nothing to
install and nothing to build, so a change is reviewable as the diff it is.
