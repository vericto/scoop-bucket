# Security Policy

This bucket only packages the Vericto CLI: its manifest points at the Windows
release archives of [vericto/vericto-cli](https://github.com/vericto/vericto-cli)
and pins them by SHA-256.

## Reporting a vulnerability

**Do not open a public GitHub issue for security vulnerabilities.**

Email **security@vericto.com**, or open a private report on the CLI repository:
[Report a vulnerability](https://github.com/vericto/vericto-cli/security/advisories/new).
Vulnerabilities in the CLI itself are handled there; see its
[security policy](https://github.com/vericto/vericto-cli/blob/main/SECURITY.md).

In scope here: a manifest that installs anything other than the archive the
CLI release published (a wrong URL or hash), or a change to this repository's
workflows that could alter what `scoop install vericto/vericto` installs.
