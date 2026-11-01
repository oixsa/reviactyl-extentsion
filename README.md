# Bedrock Version Changer

> A Reviactyl panel extension that lets you switch a Minecraft Bedrock Dedicated Server between the **Stable** and **Preview** channels and pick a specific version with one click.

<!-- TODO: add a screenshot to the repo (e.g. docs/screenshot.png) and uncomment the line below -->
<!-- ![Bedrock Version Changer](docs/screenshot.png) -->

---

## Features

- **One-click version switching** from the server's page in the panel.
- **Stable and Preview channels**: move between release and preview builds.
- **Live version list** from [Bedrock-OSS/BDS-Versions](https://github.com/Bedrock-OSS/BDS-Versions), cached for one hour, with a built-in fallback list if it can't be reached.
- **Confirmation dialog** before the server is reinstalled, to prevent accidental clicks.
- **Permission checks**: the user needs both the startup-update and reinstall permissions on the server.
- **Validated input**: only versions from the fetched list (or `latest` / `preview`) are accepted.
- **Activity log**: every version change is recorded in the server's activity log.

## How it works

Selecting a version sets the server's `BEDROCK_VERSION` startup variable and triggers Reviactyl's normal server reinstall. During the reinstall the server goes offline and the selected build is downloaded using the official Minecraft Bedrock Dedicated Server download URL.

<!-- TODO: confirm what your egg's install script keeps or backs up (server.properties, permissions.json, allowlist.json, worlds, packs) and describe it here -->
> **Back up first.** Whether configs and worlds are preserved during a reinstall depends on your egg's install script. Preview builds can also be unstable.

## Requirements

- A Reviactyl panel (this extension targets version `26.05.01`, API `RCYL_v26`)
- A Minecraft Bedrock Dedicated Server egg with a `BEDROCK_VERSION` startup variable
- In `extension.json`, `egg_ids` is set to `16`. Change it to the ID of your Bedrock egg.

## Installation

<!-- TODO: confirm whether the install command expects the extension id or the .rext file name -->
1. Copy the `.rext` file to your Reviactyl root directory.
2. Install the extension:

   ```bash
   php artisan extension:install bedrock-ver-changers
   ```

3. Enable the extension:

   ```bash
   php artisan extension:enable bedrock-ver-changers
   ```

## Usage

1. Open your Bedrock server in the panel.
2. Open the **Bedrock Version** page.
3. Choose **Stable** or **Preview**.
4. Select a version, or leave it on **Latest Stable**.
5. Click **Change Version** and confirm.

## Disclaimer

*NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.*

## Author

Made by [oixsa](https://github.com/oixsa). Also shared in the extension showcase of the Reviactyl community Discord.
