# AceDataCloud Scoop bucket

[Scoop](https://scoop.sh/) bucket for AceDataCloud command-line tools on Windows.

## Usage

```powershell
scoop bucket add acedata https://github.com/AceDataCloud/scoop-bucket
scoop install coding-bridge
```

## Apps

| App | Description |
|---|---|
| `coding-bridge` | Run Claude Code / Codex on your own machine and drive it from the web. |

`coding-bridge` installs from [PyPI](https://pypi.org/project/coding-bridge/)
into your per-user Python (`pip --user`) and exposes a `coding-bridge` shim.

After installing, pair once and (optionally) register it as a background
service so it survives logout / reboot:

```powershell
coding-bridge pair
coding-bridge service install
```

Manifests track PyPI automatically via `checkver` / `autoupdate`.
