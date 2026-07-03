# Agent Conductor

Official Windows downloads and release notes for Agent Conductor, a local dashboard
for orchestrating AI coding agents.

This repository contains release files and public metadata (such as the agent/model
catalog). The application source code is maintained separately.

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

## Feedback

Report distribution problems in this repository's
[Issues](https://github.com/chibivaru1225/agent-conductor-releases/issues).
