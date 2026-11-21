# Open the requested research case in Open-Science Desktop
Version 0.2.0 · first-use acceptance candidate

Use the current request's case page and research package. Complete the work on the user's computer. Report four outcomes separately: running desktop version, actual model response from Open-Science (OS), archive import, and visible desktop session. Keep the user in the receiving chat whenever possible; group account selection, login and consent into one visit if the provider permits. Count any extra confirmations and return visits. Keep the production research profile, research history, attachments and WorkBuddy sign-in intact. Never reset an installation as part of opening a case.

## 1. Install, launch and check the running release

Read the OS and processor architecture and inspect the installed desktop bundle, if present. Look up the current compatible stable release at the [official AIPOCH download page](https://aipoch.com/open-science/download). Use its installer for this platform. If OS is absent, download, install and launch it. Update an older installation through its supported desktop update channel or matching official installer. Keep a newer installation and report its version. Respect operating-system confirmation dialogs.

Read the version from the running desktop or its attached backend. Verify the CLI's status reports that same desktop profile and intended version. Record the official release, download source, installed/running versions, and any mismatch. On macOS, if the launcher is absent, use the bundled node-runtime/node and backend/cli.mjs inside Open-Science.app/Contents/Resources. A downloaded installer or a version in a filename does not establish which release is running.

## 2. Connect the receiving assistant's plan in OS

The chat model in WorkBuddy executes this request. OS separately selects the Agent framework, account and main model for research. Inspect only the relevant framework, regional account status and model fields through OS's documented settings or CLI. Keep secrets out of the chat, clipboard, commands, logs, screenshots and reports. Never read token files, keychain entries or another project's messages. Never substitute a paid API, another account or another provider when subscription authorization fails.

**First launch with WorkBuddy.** In the 1.3.2 first-run wizard:
1. Complete Environment, then Data location. Keep the proposed location unless the user chose another.
2. On Agent runtime, choose **CodeBuddy** for the WorkBuddy plan. Install or re-detect the runtime through OS if needed. Check the selected framework. The built-in Open-Science Agent is the fresh-install default.
3. The 1.3.2 wizard's Model provider screen does not offer the regional CodeBuddy subscription cards. Use **Skip** if applicable, finish the Notebook step (Python/R can be deferred for this case), then **Finish**. Skip may select a free Kilo model; this is not the user's WorkBuddy plan.
4. On the desktop, check **Settings → Agent** shows CodeBuddy active. In **Settings → Model**, select the built-in **CodeBuddy China** or **CodeBuddy International** account card for the region that owns the plan. Reuse a valid sign-in for that region via the offered existing CodeBuddy CLI sign-in option. A running WorkBuddy chat alone does not establish that this login is available. If the region is ambiguous, ask once. If a login is required, take the user directly to the official authorization screen. Ask them to confirm only the relevant account, region and consent in that visit. Never ask them to paste a token or an API key into chat.
5. Validate the account and choose a **Main model** offered by that account; use its already selected or recommended compatible model when available. If multiple choices require a preference, ask in the same handoff. Re-read effective framework, provider and model. Use OS settings or supported CLI operations; do not assume an undocumented CLI can provision a subscription. For different installed versions, use the [current first-run](https://aipoch.com/docs/guides/onboarding/) and [provider instructions](https://aipoch.com/docs/guides/providers/) and report any material UI difference.

**Existing OS configuration.** Reuse a working configuration for the requested framework and account. Record reuse separately from a first binding. Ask before replacing an unrelated active setup. For other local clients, use the corresponding OS flow: Codex → Codex subscription; Claude Code → Claude subscription; OpenCode → an authorized compatible provider/model chosen for OpenCode. For an explicitly requested API-key setup, have the owner enter it directly into the provider's protected settings field. Close secret-bearing screens before gathering evidence.

## 3. Send one real model request from OS

Use a separate, uniquely named empty writable OS project/session for the connection check. Keep the case archive read-only. From OS (desktop or its attached public CLI), send **Reply with only OK.** For example, obtain a test project ID from project create, then use the installed CLI's supported syntax:

    open-science run --project "$probe_project_id" --prompt "Reply with only OK." --wait --json

Inspect only this run's result. Retain its run/session identifier, completion status, actual assistant text, and the provider and model attributed to the call by the run receipt, usage record or OS activity for this specific run. Never dump whole diagnostics. If only configured routing is visible, label it “configured”; mark actual provider/model attribution unverified. Require a completed response from the intended model for full acceptance. Record a different reply verbatim as a response-format discrepancy. A settings check, an available-model list, a reply from WorkBuddy, or a successful read of an archived session is insufficient. Report authentication, quota, network, and pending-user-login failures separately. On timeout, check the original run before retrying. You can still import and display the case if the model check fails; retain that failure in the final result.

## 4. Import this archive and show its transcript in the foreground

Open the supplied case page. Match its Download research package link to the supplied .science URL. Read one distinctive finding or artifact name. Match the archive filename and case in the [official manifest](https://statics.aipoch.com/open-science/usecases/manifest.json); verify the downloaded file's exact byte count and SHA-256. Stop on a mismatch. Do not substitute an earlier case, a similarly named project or a related package.

For each new request, import this verified archive into a fresh, uniquely named project (case title plus time or a short unique suffix). Preserve all existing projects. For example:

    open-science session import "$archive_path" --new-project "$unique_project_name" --non-interactive --json

Save the exact project ID and session ID from this operation. After a timeout, reconcile the original import before trying again. Optional documented MCP list_sessions/get_session operations can confirm this specific ID. They do not display it on screen.

Request activation of the OS desktop through the official **open-science://open** link (on macOS, the system open command can open this URI). It requests a window without accepting a project/session parameter. With an already-authorized desktop tool, select the uniquely named project and, if necessary, its imported session. Confirm OS owns the frontmost visible window, the transcript is on screen, and a distinctive finding or artifact matches this import. Use the returned IDs to disambiguate. If selecting a one-session project already shows its transcript, stop clicking. Never count an import toast, library listing, background window, or a replay's landing screen as a visible transcript.

If using the official desktop import preview **instead of** CLI import, record the new IDs through the supported import result/status. Its completion action **Open imported Session** targets that import; inspect the visible transcript before reporting success. Do not re-import an archive just to bring an existing import to the front.

If desktop control is unavailable or denied, stop driving the UI after one failed attempt. Leave OS running. Use the shortest user-facing instruction that fits the observed state. In a Chinese chat: “案例已导入。请在 Open-Science 首页的「Projects」里点「<本次唯一项目名>」。如果窗口没显示，先点 Dock 或任务栏里的 Open-Science。” If more than one session is visible, name the returned session to select; if the import-complete dialog is already visible, ask for **Open imported Session** instead. Do not change system protections, inspect private stores, try debug ports or use substitute input methods after denial.

## Acceptance record

Report the actual version and source; fresh or reused framework/account; the OS model check and attributed provider/model; the verified package, project and session IDs; and what was actually visible in the foreground. Record each follow-up prompt, app switch, click and authorization, who performed it, how many times the user had to leave WorkBuddy after sending, and the final automatic OS foreground transition separately. Use “not tested” or “blocked” for missing evidence and give the exact next click. Never report that the user saw the case based on backend data alone.
