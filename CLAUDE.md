# Agent Workbench releases

The public download page for Agent Workbench, the desktop app for running and supervising
CLI coding-agent sessions. It holds the README, the recordings it shows, and the releases;
the app's source is not here.

- `README.md`: what the app does, PR Hero, the download table, install steps per platform,
  requirements, versioning, and where to report issues
- `SECURITY.md`: how to report a vulnerability privately, and what the policy covers
- `assets/workbench.gif`, `assets/pr-hero.gif`: the two recordings the README embeds
- The installers and release notes are GitHub release assets, not files in the tree

## What publishes into it

Every release is built and published by CI. Versions follow `v<major>.<minor>.<patch>` tags,
release notes are generated from the commit history grouped by change type, and versions
below 1.0 are early builds.

## What not to do

- Do not create, edit or delete releases, tags or assets by hand. They come from the app's
  pipeline, which runs the tests and install integration tests on macOS, Windows and Linux
  before it publishes
- Do not add source code or build steps here
- Keep the README's download table in step with the files a release actually carries
  (`Agent.Workbench-<version>-arm64.dmg`, `Agent.Workbench.Setup.<version>.exe`,
  `Agent.Workbench-<version>.AppImage`, `agent-workbench_<version>_amd64.deb`)
- Commit messages are Conventional Commits with a `docs(readme):` style scope, as the
  history shows
