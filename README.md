# Office AI Add-in for Word, Excel, and PowerPoint

Automate repetitive Microsoft Office work with reusable one-click workflows.

[Download latest release](../../releases/latest) ? [Install guide](docs/install.md) ? [FAQ](docs/faq.md) ? [Privacy](docs/privacy.md) ? [Security](SECURITY.md)

> This public repository publishes signed installers, changelogs, docs, and issue tracking.
> The product source code is proprietary.

## Why this exists

Most Office users do not need another generic AI chat window.
They need reliable ways to finish recurring work inside Word, Excel, and PowerPoint:

- clean and standardize documents before delivery
- transform spreadsheet ranges without rebuilding the sheet every week
- batch-fix presentation text, titles, and footers
- turn repeated steps into reusable commands

## Key capabilities

### Word
- Formatting and selection workflows
- Cleanup before client/internal delivery
- Find and replace with safer review-oriented flows
- Batch-oriented document processing helpers

### Excel
- Range cleanup and preparation
- Grouping / summary oriented workflows
- Formula and generation helpers for the current selection
- Reusable recipes for recurring spreadsheet tasks

### PowerPoint
- Batch title and footer standardization
- Cross-slide text replacement
- Outline export / presentation cleanup helpers

### Workflows and commands
- Build reusable commands from real Office tasks
- Keep frequent operations one click away in the Office ribbon
- Optional script/workflow sharing for teams

## Requirements

- Windows 10 or Windows 11
- Microsoft Word, Excel, and/or PowerPoint
  - TODO: list exact supported Office builds (Microsoft 365 / Office 2021 / Office 2019 / Office 2016)
- Administrator permission may be required for first install
- Internet connection for AI-assisted features, license/account flows, and update checks

## Download

Download the latest signed Windows installer from GitHub Releases:

**[Latest release](../../releases/latest)**

Also available from the product website:

- Product site: `https://clippad.cc`  
  TODO: confirm the canonical English download URL before launch.

## Install

1. Close Word, Excel, and PowerPoint.
2. Download `OfficeAI-Setup-x.y.z.exe` from Releases.
3. Run the signed installer.
4. Reopen Office and look for **Office AI** on the ribbon.

If the ribbon entry is missing, see [docs/install.md](docs/install.md).

## Trust and safety

- Installer should be code-signed by your publisher identity.
- AI features send content only when the user explicitly triggers them.
- Do not paste secrets, customer documents, or confidential data into public issues.
- Read [docs/privacy.md](docs/privacy.md) and [SECURITY.md](SECURITY.md) before enterprise rollout.

## Support

- GitHub Issues: bug reports, install problems, feature requests
- Email: `support@clippad.cc`  
  TODO: replace with the real English support inbox if different
- Security reports: see [SECURITY.md](SECURITY.md)

## Repository contents

| Path | Purpose |
|---|---|
| `README.md` | Product overview |
| `CHANGELOG.md` | Version history |
| `docs/` | Install, FAQ, privacy |
| `SECURITY.md` | Vulnerability reporting |
| `LICENSE` | Proprietary license terms |
| GitHub Releases | Signed installers and checksums |

## Roadmap signals we care about

We prioritize workflows that save repeated Office labor:

1. Excel cleanup and recurring reporting prep
2. Word delivery cleanup and formatting QA
3. PowerPoint batch standardization
4. Better install reliability and enterprise trust docs

## License

Proprietary software. See [LICENSE](LICENSE).

You may download and use the published installer under the product terms.
You may not redistribute modified installers or claim the product is open source.
