# Agent Conductor

Official Windows downloads and release notes for Agent Conductor, a local dashboard
for orchestrating AI coding agents.

This repository contains release files and public metadata (such as the agent/model
catalog). The application source code is maintained separately.

## What it does

Agent Conductor runs entirely on your own machine and coordinates multiple AI coding
agents (Claude, Codex, GitHub Copilot, Grok, Gemini) across your GitHub projects from a
single dashboard:

- **Multi-agent PR review** — combine several agents to review a pull request, track
  unresolved comments, and re-review after fixes.
- **Execution plans** — queue GitHub issues (or imported work items) as an ordered plan
  and run them one after another.
- **Merge automation** — auto-merge only once configurable gates (tests, CI, review
  resolution) are satisfied.
- **Plan proposals** — an agent can suggest an implementation order and model
  assignment from your open work items; a human reviews and approves it.
- **Plan dependencies** — make one plan wait on another so multiple workstreams can run
  safely in parallel.
- **Local-first** — binds to `127.0.0.1` only; no account, no hosted service, no
  telemetry beyond the optional checks described below.

See the version-specific [release notes](https://github.com/chibivaru1225/agent-conductor/blob/main/docs/release-notes)
in the application source repository for what's new and known limitations in each
release.

## License

Agent Conductor runs unlicensed with free-tier limits (a small number of projects and
one concurrent agent run). Purchasing a license removes those limits.

**[Purchase a license on Polar.sh](https://buy.polar.sh/polar_cl_BtZIOJDdD1abSue5TMZR4DLUaeuMc7zUTCxPv3FGIMp)**

After purchase, activate the license key from the app's **License** settings page.
License verification is a deterrent against casual misuse, not DRM — see the
application's EULA for details.

## Download

Open the [Releases](https://github.com/chibivaru1225/agent-conductor-releases/releases)
page and download the explicitly attached file named:

```text
agent-conductor-<version>-win-x64-portable.zip
```

Do not download GitHub's automatically generated `Source code` archives. Those archives
do not contain the runnable Windows package.

## Start

1. Extract the entire ZIP to a folder you can write to.
2. Double-click `start.cmd`.
3. Keep the console window open while using Agent Conductor.

The package is self-contained and does not require a separate .NET installation. Git
and any coding-agent CLIs you want Agent Conductor to use must be installed separately.

Application data is stored under `%LOCALAPPDATA%\AgentConductor`.

## Windows security notice

The current Portable preview is unsigned. Windows Smart App Control or another
application-control policy may block it. Do not disable a security policy solely to run
Agent Conductor. A signed distribution may be provided in a future release.

## Verify the download

Each Portable ZIP has a matching `.sha256` asset. You can verify it in PowerShell:

```powershell
Get-FileHash .\agent-conductor-<version>-win-x64-portable.zip -Algorithm SHA256
```

The displayed hash must match the value in the downloaded `.sha256` file.

## Agent/model catalog

Agent Conductor downloads a small JSON catalog from this repository's GitHub Pages site
to learn about supported agents and models without requiring an application update:

```text
https://chibivaru1225.github.io/agent-conductor-releases/catalog/v1/agents.json
```

The file only lists agent/model IDs, display names, and lifecycle state (`active`,
`deprecated`, `retired`, `hidden`). It never contains commands, executables, or
arguments. See [`docs/catalog/v1/schema.json`](docs/catalog/v1/schema.json) for the
schema.

## Update check

Agent Conductor also periodically checks a small JSON manifest from this repository's
GitHub Pages site to let you know when a newer version is available:

```text
https://chibivaru1225.github.io/agent-conductor-releases/version/v1/version.json
```

The file only contains the latest version number and a link to its release page.

## Feedback

Report distribution problems in this repository's
[Issues](https://github.com/chibivaru1225/agent-conductor-releases/issues).
