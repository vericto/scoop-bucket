# Vericto Scoop bucket

[Scoop](https://scoop.sh) manifest for the
[Vericto CLI](https://github.com/vericto/vericto-cli) (`vericto`), which checks
SQL against your Vericto workspace's security rules before it runs, in CI, in
git hooks or offline. Supported: Windows x64 and Windows on ARM (arm64).

## Install

```powershell
scoop bucket add vericto https://github.com/vericto/scoop-bucket
scoop install vericto/vericto
vericto --version
```

## Upgrade

```powershell
scoop update
scoop update vericto
```

A new manifest (`bucket/vericto.json`) is published here by the CLI's release
workflow for every release. It pins the SHA-256 of both Windows archives from
the release's `sha256.sum`; Scoop refuses a download whose hash does not match.

## Uninstall

```powershell
scoop uninstall vericto
scoop bucket rm vericto
```

## Other ways to install

PowerShell installer, winget, npm (`npm install -g @vericto/vericto-cli`) or the
release zip: see the [CLI's README](https://github.com/vericto/vericto-cli#install).

## Issues

Report problems with the CLI in
[vericto/vericto-cli](https://github.com/vericto/vericto-cli/issues), and
security issues as described in its
[SECURITY.md](https://github.com/vericto/vericto-cli/blob/main/SECURITY.md).

## License

This bucket is licensed under the Apache License 2.0 ([LICENSE](LICENSE)). The
Vericto CLI it installs is licensed under the Functional Source License 1.1,
ALv2 Future License (FSL-1.1-ALv2); see its repository.
