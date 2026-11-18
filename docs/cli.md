# CLI reference

Run these commands from the root of a project that has release-it installed.

| Command | What it does |
| --- | --- |
| `npx release-it --dry-run` | Walk through a release and see which commands would run. |
| `npx release-it --release-version` | Print the next version and exit. If there is no next version, the output is empty. |
| `npx release-it --changelog` | Print the changelog and exit. |

In a [dry run](dry-runs.md), `$` marks a read-only command that ran. A line starting with `!` shows a command that
would change something, such as creating a tag. See [configuration](configuration.md) for project-specific options.
