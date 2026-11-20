# Open the worm longevity case in Open-Science

The requested outcome is the imported research session visible in the Open-Science desktop application. Carry out the steps on the user's machine. Use a local desktop-capable client. If the chat runs in a web sandbox, ask the user to reopen this request in its local desktop or CLI client. Preserve existing projects. Use a previously imported, matching session when available.

## Case identity

- Market title: **Worm longevity genes and human exceptional-longevity evidence**
- [Official case page](https://aipoch.com/open-science/use-cases/worm-longevity-genes-and-human-exceptional-longevity-evidence)
- [Download the .science package](https://statics.aipoch.com/open-science/usecases/worm-longevity-genes-and-human-exceptional-longevity-evidence/Worm-longevity-genes-and-human-exceptional-longevity-evidence.science)
- Expected bytes: 269483106. SHA-256: `2e64bebbcdc6140d234ba316aa10ee3d8c1111b1afe584e257ba12c6705df76d`. If the publisher has updated the file, verify the new size and digest against the matching entry in the [market manifest](https://statics.aipoch.com/open-science/usecases/manifest.json).

## Prepare the desktop and model

1. Check the installed desktop version and OS/architecture. Compare it with the [official stable release](https://github.com/aipoch/open-science/releases/latest). Install the appropriate desktop package if missing. Update an older installation through its supported channel and resume after any system approval. Launch the desktop app, then confirm the CLI targets the same profile with its status command.
2. Identify the assistant receiving this request. Open Open-Science **Settings** and reuse a working configuration for the matching framework. Use the method below when setup is needed. Check the selected framework with `open-science settings agent-routing show --json`, and validate the connection in Settings. Keep credentials inside the provider's own sign-in flow.

   | Assistant running this request | Model setup in Open-Science |
   | --- | --- |
   | WorkBuddy | Select **CodeBuddy**, choose the regional site that owns the user's plan, and select **Use existing CodeBuddy CLI sign-in**. Complete the site's authorization if prompted. |
   | Codex | Select **Codex** and **Codex subscription**. Import the existing ChatGPT sign-in or complete the displayed sign-in, then validate and activate the subscription. |
   | Claude Code | Select **Claude Code** and **Claude subscription**. Use the existing Claude Code sign-in if offered, or complete the Claude browser authorization in Settings. Claude web chat needs a local client with access to this desktop. |
   | OpenCode | Select **OpenCode**, let OS detect the local OpenCode executable, and select an already-authorized provider and model offered by OS for this framework. If none is available, ask which provider the user wants to connect and complete its supported setup in Settings. OpenCode does not imply a particular subscription. |

   If account authorization requires the owner, continue with independent archive preparation and identify the required sign-in. Opening an archived session does not require running a new model turn.

## Import once and display the result

3. **Browser and desktop route.** Open the official case page above in a top-level browser tab. Click **Open in Open-Science**, accept any browser-to-app prompt, choose the destination in OS and complete the import. Wait until the desktop reports completion. A download or transfer receipt alone is insufficient.
4. **Terminal alternative.** Download the linked file over HTTPS with the browser or an HTTP client. Verify its byte count and SHA-256. Use the installed CLI's session import help to locate its executable. Import the verified absolute path. The following example creates a clearly named destination project for a first import:

   ```sh
   open-science session import "/absolute/path/to/case.science" --new-project "Worm longevity evidence" --non-interactive --json
   ```

   On a macOS desktop installation with no launcher on PATH, the bundled equivalent is /Applications/Open-Science.app/Contents/Resources/node-runtime/node followed by /Applications/Open-Science.app/Contents/Resources/backend/cli.mjs and the same arguments. Confirm both paths exist. Save the returned project and session identifiers. If the call times out, inspect the destination before retrying. Optional MCP tools such as list_sessions and get_session can check the session by ID in a connected local profile.
5. **Desktop navigation.** Bring Open-Science to the foreground. If the import did not already select the session, open the destination project in the sidebar (for the command above, **Worm longevity evidence**), select the imported session and inspect the visible transcript. Match the topic of worm longevity genes and human exceptional longevity; the archived analysis maps nine worm genes to 21 human candidates. Stop once the correct session is visible. On the tested desktop, selecting the worm project from the home project list immediately opened its only read-only session, whose title starts “I would like to examine how a small, clearly sel…”. The visible transcript includes longevity_report.md and the 75 eligible records. If UI access or model authorization requires the owner, report the exact remaining click or approval and the project name. Report a completed CLI import and a visibly opened desktop session separately.

## Report what you observed

Before reporting success, inspect the visible Open-Science desktop window. State the selected project and one matching detail from the visible conversation. If you only have a terminal or MCP lookup, bring the desktop forward using the normal application launcher and give the user the exact project to click. If the project is already selected, verify the visible conversation directly. Avoid relaunching the application to guess which session is active. Report any remaining login, desktop permission or manual click separately.
