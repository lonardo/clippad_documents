# Installation Guide

## Before you install

- Use Windows 10 or Windows 11.
- Confirm Microsoft Word, Excel, or PowerPoint is already installed.
- Save your work and close all Office apps.
- Download only from GitHub Releases or the official website.
- Prefer the code-signed installer.

## Standard install

1. Download `OfficeAI-Setup-x.y.z.exe` from the latest GitHub Release.
2. Optional but recommended: verify the SHA256 checksum published in the release notes.
3. Run the installer.
4. If SmartScreen appears, open the publisher details and confirm the expected signer name.
5. Finish setup.
6. Reopen Word, Excel, or PowerPoint.
7. Look for **Office AI** on the ribbon.

## First-run checks

- The add-in appears in the ribbon of the Office apps you use.
- Language / UI settings open successfully.
- A simple local command works before you try AI-assisted features.

## If the ribbon entry is missing

Try these steps in order:

1. Fully close all Office windows and reopen one app.
2. Reboot Windows once.
3. In Office, open **File ? Options ? Add-ins**.
4. Check **COM Add-ins** and ensure Office AI is enabled.
5. If it appears under Disabled Items, re-enable it.
6. Reinstall the latest signed build.
7. Temporarily check whether antivirus / endpoint protection quarantined the add-in.

## SmartScreen / antivirus prompts

New publishers and low-volume downloads are often challenged by Windows SmartScreen or endpoint software.

- Confirm the digital signature publisher name.
- Compare the file hash with the release notes.
- If your company blocks unsigned or uncommon software, ask IT to allow the official signer / installer hash.

## Silent / managed install

TODO: document enterprise silent-install parameters only after they are stable and tested.

Until then, assume interactive install is the supported path for public users.

## Uninstall

1. Close Office apps.
2. Open Windows **Settings ? Apps ? Installed apps**.
3. Uninstall **Office AI Add-in** / the published product name.
4. Reopen Office and confirm the ribbon entry is gone.

## After upgrading

- Prefer installing the newer build over the previous one.
- If ribbon state looks stale, restart Office once.
- Review `CHANGELOG.md` for behavior changes.

## Still stuck?

Open a GitHub issue with the **Install / ribbon missing** template, or email `support@clippad.cc`.
