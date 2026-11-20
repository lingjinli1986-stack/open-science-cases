# Open a Market case in Open-Science

Use the case page URL and the .science package URL in the user's current request. Work on the user's own computer with a local desktop or CLI client.

## Identify the requested archive

1. Open the supplied HTTPS case page. Read its title and the destination of **Download research package**. Confirm that the supplied package URL matches that link. Ignore related cases. If the page or package is missing, ask for the current case link or for a fresh copy of the page's button text. Never substitute the previous case or a title search result.
2. Find the entry for this package in the [official Market manifest](https://statics.aipoch.com/open-science/usecases/manifest.json). Match the archive filename and case identity, and use the **case** object's byte count and SHA-256. If the page, package or manifest disagree, stop and report the mismatch before import.
3. Read one distinctive result or artifact name from the supplied page. Keep it with the target title and expected digest for final verification. Reuse an existing session only when its package provenance matches the requested archive. If this cannot be established, import the verified archive into a uniquely named project. Leave other projects intact.

## Install or update Open-Science

Detect the host operating system and CPU architecture, then check whether Open-Science Desktop is installed and read its installed version. Check the [AIPOCH official download page](https://aipoch.com/open-science/download) for the latest stable version and a compatible desktop installer.

| Local desktop state | Action |
| --- | --- |
| Missing | Download the matching stable installer from the official page, install Open-Science, and launch it. |
| Older than the published stable release | Update in place using the app’s supported stable update channel. If the platform requires a manual update, use the matching installer from the same official download page. Resume after any required system confirmation or restart. |
| Already on the current stable release | Open the installed app and continue to model setup. |
| Newer than the published stable release | Keep the installed version. |

After installation or update, read the running desktop version again and confirm it matches the intended release. Confirm the CLI targets the same profile with its status command. If the host lacks a compatible installer or the update cannot be completed, report the host, observed version and remaining step.

## Connect the model

Identify the assistant receiving this request. Open Open-Science **Settings** and reuse a working configuration for the matching framework. Use the method below when setup is needed. Check the selected framework with `open-science settings agent-routing show --json`, and validate the connection in Settings. Keep credentials inside the provider's own sign-in flow.

| Assistant running this request | Model setup in Open-Science |
| --- | --- |
| WorkBuddy | Select **CodeBuddy**, choose the regional site that owns the user's plan, and select **Use existing CodeBuddy CLI sign-in**. Complete the site's authorization if prompted. |
| Codex | Select **Codex** and **Codex subscription**. Import the existing ChatGPT sign-in or complete the displayed sign-in, then validate and activate the subscription. |
| Claude Code | Select **Claude Code** and **Claude subscription**. Use the existing Claude Code sign-in if offered, or complete the Claude browser authorization in Settings. Claude web chat needs a local client with access to this desktop. |
| OpenCode | Select **OpenCode**, let OS detect the local OpenCode executable, and select an already-authorized provider and model offered by OS for this framework. If none is available, ask which provider the user wants to connect and complete its supported setup in Settings. OpenCode does not imply a particular subscription. |

If account authorization requires the owner, continue with independent archive preparation and identify the required sign-in. Opening an archived session does not require running a new model turn.

## Import the requested package

Download the supplied archive over HTTPS into a local file. Check its byte count and SHA-256 against the manifest. Use the installed OS CLI to import it into a project named for the current case. For shell clients pass each argument separately or use quoted variables:

```sh
open-science session import "$archive_path" --new-project "$target_project" --non-interactive --json
```

Set archive_path to the absolute path of the verified download and target_project to the current page title or a unique variant. On macOS, if the CLI launcher is missing, the bundled Node executable and CLI entry point are under /Applications/Open-Science.app/Contents/Resources/node-runtime/node and /Applications/Open-Science.app/Contents/Resources/backend/cli.mjs. Save the project ID and session ID returned by the import. After a timeout check the import status before retrying. As a desktop alternative, open the verified local .science file in Open-Science and confirm the destination. Optional OS MCP list_sessions/get_session tools can help confirm identity by ID.

## Open the matching desktop session

Use an already-authorized desktop interaction tool to select the returned project and session. Check the visible transcript against the distinctive detail from the requested page. A CLI import or an MCP lookup confirms data availability only. Report a visible success only after inspecting the actual desktop conversation.

If no approved desktop tool is available, or one attempt is blocked by desktop permissions, finish immediately with **One click remaining**, naming the destination project and session to select. Leave the app running normally. Use documented OS CLI/MCP and user-facing controls only. Do not inspect private app storage, debug ports or internal APIs, restart the app, or try alternative input methods after a denial.
