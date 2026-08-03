# FAQ

## Product

### What is Office AI Add-in?
A Windows desktop add-in for Microsoft Word, Excel, and PowerPoint that helps automate repetitive office work through ribbon commands and reusable workflows.

### Is this an official Microsoft product?
No. It is an independent product that integrates with Microsoft Office.

### Is the source code open source?
No. This public GitHub repository is for releases, docs, checksums, and issue tracking. The product remains proprietary.

## Install and compatibility

### Which Office versions are supported?
TODO: publish the tested matrix before overseas launch.

Practical guidance:
- Microsoft 365 on Windows is the primary target.
- Recent perpetual Office versions may work, but should be listed explicitly after testing.

### Does it work on Mac?
No. The current product targets Windows desktop Office.

### Does it work with Office on the web only?
No. It requires installed desktop Office applications on Windows.

### Why does Windows SmartScreen warn me?
SmartScreen often warns on new or low-reputation downloads. Use the signed official installer and verify the SHA256 hash from the release notes.

### The installer finished, but I do not see the ribbon.
See [install.md](install.md). Most cases are fixed by restarting Office, checking COM Add-ins, or recovering a disabled add-in.

## Features

### Do I need the internet for every feature?
No. Local Office automation can work offline. AI-assisted features, account flows, updates, and online content require network access.

### Will it modify my documents automatically?
Only when you run a command or workflow. Always review important outputs, and back up critical files before batch operations.

### Can teams share reusable commands?
Yes, workflow/command reuse is part of the product direction. Exact sharing/marketplace behavior depends on the build you install.

## Privacy and accounts

### Does the add-in upload my whole document?
Not by default for local automation. AI-assisted actions may send selected content, prompts, or necessary context when you explicitly trigger them. See [privacy.md](privacy.md).

### Do I need an account?
Some community, license, or online features may require an account. Core install and local tools should be documented clearly per release.

## Pricing

### Is it free?
Public launch pricing may include a free tier and paid plans later. Publish the current commercial terms on the website and keep this FAQ synchronized.

### Do you support refunds or purchase invoices?
TODO: document the commercial policy before paid overseas launch.

## Support

### Where should I report bugs?
Use GitHub Issues with the bug template. For install-only problems, use the install template.

### Can I request a feature?
Yes. The most useful requests describe:
1. the Office app
2. the repeated manual workflow
3. the ideal one-click result
4. how often the task happens
