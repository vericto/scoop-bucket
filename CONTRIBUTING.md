# Contributing to the Vericto Scoop bucket

Thanks for your interest in the Vericto Scoop bucket. This repository only
packages the [Vericto CLI](https://github.com/vericto/vericto-cli) for
[Scoop](https://scoop.sh); its files are under the
[Apache License 2.0](LICENSE).

## Code of Conduct

This project follows the [Contributor Covenant](CODE_OF_CONDUCT.md). Be
respectful, constructive, and technically precise.

## What belongs here

- **The bucket's CI**: `.github/workflows/validate.yml`, which checks that
  `bucket/vericto.json` is a valid manifest pinned to the CLI's release,
  `test.yml`, which installs it with Scoop on Windows x64 and arm64 and runs the
  binary, and `gitleaks.yml`.
- **Documentation**: `README.md`.

What does not:

- **`bucket/vericto.json`.** It is generated in the CLI's release workflow
  (`windows/package.js scoop`) and pushed here by its `scoop-publish` job, which
  waits for approval of the CLI repository's `prod` environment. Do not edit it
  by hand: the next release replaces it. A fix to the manifest belongs in
  [vericto/vericto-cli](https://github.com/vericto/vericto-cli), in
  `windows/package.js` or `.github/workflows/scoop-publish.yml`.
- **The CLI itself** (flags, output, exit codes) →
  [vericto-cli issues](https://github.com/vericto/vericto-cli/issues/new/choose).

A problem that only shows up through Scoop (an install, hash or upgrade
failure) can be opened here as an issue.

## Testing locally

On Windows, with Scoop installed:

```powershell
scoop bucket add vericto-local $PWD   # add this checkout as a bucket
scoop install vericto-local/vericto
vericto --version
scoop uninstall vericto
scoop bucket rm vericto-local
```

## Pull requests

- Required checks: `validate manifest`, `scoop install (x64)`, `scoop install (arm64)`
  and `gitleaks`.
- Keep actions pinned to full commit SHAs with a version comment, as in
  vericto-cli; Dependabot keeps them current.
- Write commit messages, comments and pull request descriptions in English. The
  manifest commits from the CLI release are named `vericto X.Y.Z`.
- At least one maintainer review (CODEOWNERS requests it).

Pull requests are merged with a merge commit; squash and rebase merges are
disabled.

## Releases

This repository has no releases or changelog of its own. Each
[vericto-cli release](https://github.com/vericto/vericto-cli/releases) from
1.11.0 publishes the new manifest to `main` here; its changes are in the CLI's
[CHANGELOG](https://github.com/vericto/vericto-cli/blob/main/CHANGELOG.md).

## Reporting security issues

Do **not** open a public issue for vulnerabilities. See [SECURITY.md](SECURITY.md)
or email [security@vericto.com](mailto:security@vericto.com).

## License

The files in this repository are under the [Apache License 2.0](LICENSE). The
Vericto CLI that the manifest installs is a separate program, licensed under
the [Functional Source License, Version 1.1, ALv2 Future
License](https://github.com/vericto/vericto-cli/blob/main/LICENSE)
(`FSL-1.1-ALv2`); see the CLI's
[LICENSING.md](https://github.com/vericto/vericto-cli/blob/main/LICENSING.md).
The licenses grant no right to the Vericto name or logo; see
[TRADEMARKS.md](TRADEMARKS.md).
