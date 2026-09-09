# Agent Workbench

A desktop workbench for running and supervising coding-agent CLI sessions
(Claude Code, Codex, Gemini, Aider, OpenCode). Each session is a real terminal;
around it the app adds what a terminal alone cannot: live status with
notifications (running, waiting for input, done, error), per-repository
grouping with GitHub/GitLab sign-in, diff summaries against a baseline, CI
status of the linked PR, MCP server inspection, cost tracking, and PR Hero, a
game window where your open pull requests are monsters your hero fights.

This repository hosts the public downloads and release notes. The source code
lives in a private repository; this is the place to get the app and follow
what changed between versions.

## Download

Grab the installer for your platform from the
[**latest release**](https://github.com/Vocabulo-Confiante/agent-workbench-releases/releases/latest).
Every release ships all platforms:

| Platform | File | Notes |
|---|---|---|
| macOS (Apple Silicon) | `Agent.Workbench-<version>-arm64.dmg` | Signed and notarized |
| Windows (x64) | `Agent.Workbench.Setup.<version>.exe` | NSIS installer |
| Linux (x64) | `Agent.Workbench-<version>.AppImage` | Portable, no install |
| Linux (Debian/Ubuntu) | `agent-workbench_<version>_amd64.deb` | System package |

All previous versions stay available on the
[releases page](https://github.com/Vocabulo-Confiante/agent-workbench-releases/releases).

## Installing

### macOS

Open the `.dmg` and drag **Agent Workbench** to Applications. The build is
Developer ID signed and notarized by Apple, so it opens without warnings.

### Windows

Run the installer. SmartScreen may warn on first launch until the build is
Authenticode signed: click **More info**, then **Run anyway**.

### Linux

AppImage: make it executable and run it.

```bash
chmod +x Agent.Workbench-*.AppImage
./Agent.Workbench-*.AppImage
```

Debian/Ubuntu package:

```bash
sudo dpkg -i agent-workbench_*_amd64.deb
```

## Requirements

Agent Workbench supervises CLIs you already use. None are required to start
the app, and the built-in settings screen can detect, validate, or install
them for you:

- One or more agent CLIs: `claude`, `codex`, `gemini`, `aider`, `opencode`
- `git`, plus `gh` (GitHub) or `glab` (GitLab) for forge features such as CI
  status and PR Hero
- Optionally an IDE launcher (`idea` or `code`) for the open-in-IDE shortcut

## Release notes and versioning

Versions follow `v<major>.<minor>.<patch>` tags. The notes on each release are
generated from the commit history, grouped into Features, Bug fixes,
Performance, and so on, so they reflect exactly what shipped. Releases marked
**pre-release** are early builds published before the first stable version.

Every release is built and published by CI: the pipeline runs the full test
suite plus real-machine install integration tests on macOS, Windows, and Linux
before packaging, so a build with a broken installer never publishes.

## Feedback and issues

Found a bug or have a feature request? Open an issue in this repository's
[issue tracker](https://github.com/Vocabulo-Confiante/agent-workbench-releases/issues).
Please include your OS, the app version (visible in the title bar menu), and
steps to reproduce.
