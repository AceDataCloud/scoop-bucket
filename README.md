# AceDataCloud Scoop bucket

[Scoop](https://scoop.sh/) bucket for AceDataCloud command-line tools on Windows.

## coding-bridge

Run Claude Code / Codex on your own machine and drive it from the web.

```powershell
scoop bucket add acedata https://github.com/AceDataCloud/scoop-bucket
scoop install coding-bridge
```

Verify and pair — pairing prints a code you enter in the web app:

```powershell
coding-bridge status
coding-bridge pair
```

### Keep it running in the background

```powershell
coding-bridge service install
```

That registers a per-user Scheduled Task (`CodingBridge`) which starts the
daemon at logon. Manage it with `service start` / `stop` / `status` /
`uninstall`.

> **Pair before installing the service** — a background task can't do the
> interactive pairing step.

> **Don't also run `coding-bridge up` in a terminal** while the service is
> running: two daemons share one node token and fight over the connection.

If the daemon can't find your `claude` / `codex` CLI once running as a service,
pass an explicit path (`--claude-path`) or set `CODING_BRIDGE_CLAUDE_PATH`.
Logs are under `%USERPROFILE%\.ace-bridge\logs\`.

Full docs: [AceDataCloud/CodingBridge](https://github.com/AceDataCloud/CodingBridge).

## Notes

`coding-bridge` installs from [PyPI](https://pypi.org/project/coding-bridge/)
into your per-user Python (`pip --user`) and exposes a `coding-bridge` shim, so
Scoop's `python` is a dependency.

The manifest version is bumped automatically by CI after each release;
`checkver` tracks PyPI.
