# Security Policy

## Supported versions

Security updates are provided for the latest published release on GitHub Releases.
Older builds may not receive fixes.

| Version | Supported |
|---|---|
| Latest release | Yes |
| Older releases | Best effort only |

## Product security expectations

- Official installers should be code-signed.
- Prefer downloading only from GitHub Releases or the official website.
- Verify SHA256 checksums published in the release notes when provided.
- Treat community mirrors as untrusted unless we explicitly list them.

## Data handling summary

- Local Office automation stays on the device unless you explicitly run a
  cloud/AI-assisted action or upload feedback.
- Feedback packages may include logs, screenshots, or diagnostic data that you
  choose to send.
- Do not upload confidential documents, credentials, or customer data to public
  GitHub issues.

See [docs/privacy.md](docs/privacy.md) for the public privacy summary.

## Reporting a vulnerability

Please report security issues privately.

- Email: `security@clippad.cc`  
  TODO: replace with your monitored security inbox
- Include:
  - product version
  - Office and Windows versions
  - impact assessment
  - reproduction steps or proof-of-concept details
  - whether the issue is already public

Please allow a reasonable time for assessment before public disclosure.

## What not to report in public issues

- zero-day details that enable malware abuse
- private customer documents
- authentication tokens, private keys, or dump files with sensitive paths

## Acknowledgments

Responsible reporters may be credited in release notes if they want attribution.
