# Open this research case in Open-Science
Version 0.2.5 — 2026-11-24; complete first-run setup before import; model setup may be skipped

Use the case-page URL in the user's request to identify the target. Read that page's visible AI assistant guide link and Download research package link (or their equivalents). Resolve relative links against the case page. The request may include only the case-page URL; a separate package URL is optional. If supplied, it must agree with the page. Do not infer the package from the case name alone. If the page or required links cannot be read, report the missing link and ask for it; do not guess a different case. This guide works across cases and receiving assistants, including WorkBuddy, Codex, Claude Code and OpenCode. Reply in the user's language.

The goal is to import the supplied archive and bring the correct Open-Science desktop window forward. A visible, actionable **Open imported Session** for this import is an acceptable handoff. Opening the matching archived conversation is also complete.

Preserve existing projects, sessions, attachments and working account settings. Reading an archive requires no new model request. The receiving assistant's chat model and the model configured inside OS are independent.

## 1. Install or update the official desktop

Identify the operating system and CPU architecture. Visit the [AIPOCH download page](https://aipoch.com/open-science/download), record the latest stable version shown there and choose the matching official installer. Use the installed app's version when deciding whether to update. Keep a newer installed version and explain any difference. Use the supported updater or official installer for an older version.

Install missing OS using the platform's standard supported flow. Follow the official release's signature and checksum information where provided. Preserve the user's data during an update. This guide uses the official desktop and its existing capabilities.

If installation needs an ordinary approval, identify the exact application and operation and ask the user to approve it through the offered control. Count installation approval separately from model-provider authorization. If the security layer rejects the operation without an approval option, stop automated installation and report its exact message and the incomplete destination. WorkBuddy has rejected temporary-file deletion during a Mac application copy. A verified archive or a partial app directory does not prove installation. Do not retry equivalent commands, disable protections, or delete partial copies without authorization. Give the user the official installation instructions and the required next action; continue only after the permitted installation is complete.

Launch the intended installed desktop. Read the actual running version from About or its desktop service and compare it with the official version after installation or upgrade. Record both values. A downloaded installer version alone is insufficient.

## 2. Complete first-run setup before importing (required)

**Model setup is optional for archive viewing; completing first-run setup is required.** You may select **Skip** at the model-provider step, then continue through the remaining wizard and select **Finish**. Do not leave the user at the wizard and report the case-opening task as complete. Do not import a new case until the workspace check below passes.

On an existing profile already showing the workspace, preserve its working configuration. On a new profile, complete the visible wizard on the same desktop/profile that will receive the archive, in this order:

1. **Environment:** wait for the required checks to pass, then select **Continue**. Green checks mean the environment is ready; they do not mean first-run setup is finished.
2. **Data location:** confirm the intended research location using the supported controls. Preserve existing data. If recovering a case already imported in this task, first identify its existing location; do not silently switch to a new empty data root. Complete any required restart and resume the wizard.
3. **Agent runtime:** prefer the user's requested compatible runtime when available. For WorkBuddy, CodeBuddy may be used with the appropriate regional subscription. If its installation cannot complete, or only archive viewing is needed, use the built-in **Open-Science Agent** when offered and ready. It requires no separate runtime download and does not bind the WorkBuddy plan. Do not repeatedly install missing external runtimes when the supported built-in runtime is ready.
4. **Model provider:** an existing working setup may be retained. Otherwise **Skip** is allowed for opening an archived case; model configuration does not have to succeed. Use the visible Skip control and wait for the next wizard step. In OS 1.3.4, Skip adds a default Kilo provider before advancing; this is not a verified user subscription and is not literally “no configuration changes.” Send no model messages. If the user explicitly asks to configure a subscription now, use step 3 of this guide, then return and finish the wizard. If Skip fails or is unavailable, report that exact step instead of inventing a skip method.
5. **Notebook runtime:** leave optional Notebook/Python/R installation deferred for archive viewing, then select **Finish** (or the equivalent completion control actually shown). Skipping the model step does not perform this final action. Wait for completion; a click followed by an error or the same wizard is not success.

**Required workspace check:** confirm that the first-run wizard is no longer displayed and the intended desktop shows its Home/Projects workspace. Record how this was confirmed: direct UI observation, or the user's explicit confirmation when UI access is unavailable. A supported first-run completion status can supplement this check. Verify that subsequent CLI operations use that same desktop service/profile and intended data location. Never change internal completion flags or settings files to manufacture a passed check.

A running process, connected backend, successful `project list`, ready built-in runtime, `doctor` result, or successful CLI import does not prove the wizard is complete. Conversely, `provider_missing` alone does not explain why the wizard remains visible: provider readiness and first-run completion are separate. A missing or unverified model may remain deferred after the workspace opens; it must not trigger a model test request or block archive import by itself.

**If you cannot complete or observe the wizard:** use only supported controls available to your agent. A supported local browser interface must belong to the same desktop/profile. Keep sign-in links private. If manual help is required, pause before import and give the exact remaining sequence in one message. For example, adapt this to the controls actually present:

> “OS 已安装，但首次设置尚未完成，暂未导入案例。请在向导里继续：确认数据位置 → 选择已就绪的 Open-Science Agent → 模型页点‘跳过’ → Notebook 页暂不安装，点‘完成’。看到主页或项目列表后告诉我，我再继续导入；不需要登录套餐或发送模型消息。”

If the current screen is Environment, include its **Continue** button first. Wait for confirmation before continuing dependent work. Providing these instructions is a handoff, not proof that the user performed them. Record every user action separately from provider authorization.

## 3. Configure a subscription only when the supported path is available

Only after the workspace check in step 2 passes: if optional external-runtime or model setup was deferred, proceed to step 4. Do not restart a failed setup or require authorization again for archive reading. If configuring a provider while still in the wizard, return to step 2 and complete Notebook → Finish before importing.

Respect the user's requested plan, even if a different assistant receives the request. Reuse an existing ready configuration unless the user requests a change. If region or plan is ambiguous and configuration will proceed, ask one focused question. Do not infer region from language or inspect unrelated account files.

For WorkBuddy, check **Settings → Agent** for CodeBuddy. In **Settings → Model**, choose the corresponding CodeBuddy China or International subscription if the installed release offers it. Existing same-region CodeBuddy CLI login can be reused only when OS confirms it is ready. A WorkBuddy desktop login alone does not prove OS access. Otherwise use OS's **Sign in with Open-Science → Sign in with browser**, or the equivalent supported control.

Keep one authorization request active while the owner signs in on the provider's page. A success page in the browser is followed by checking that OS received the account and model list. If a request expires while waiting for the user, explicitly report expiry and offer a fresh request when the user is ready. Do not overlap login attempts. If authorization fails, mark configuration pending and continue archive viewing when the workspace permits it.

Select a Main model from the subscription's returned list using the user's supported preference or its recommended/default choice. Read back the saved Main model and its provider/region. A new provider card alone does not prove Main model changed. Keep passwords, tokens, API keys and authorization URLs out of chat, logs and screenshots.

For Codex, use a compatible OS framework and the offered Codex subscription flow. For Claude Code, use Claude subscription access only where the installed framework offers it. OpenCode identifies a runtime; choose an actually supported authorized provider. Follow the [framework guide](https://aipoch.com/docs/guides/frameworks/) and [provider guide](https://aipoch.com/docs/guides/providers/). These paths have different support and verification states.

Use OS settings and readiness checks only. Do not send an OK request or another model message as part of opening the archive. Report configuration as ready, deferred, or failed independently of import success.

## 4. Verify and import the supplied archive once

**Before any new import, require the completed workspace check from step 2.** If the wizard is still visible or completion is unconfirmed, stop here and finish that step, even if the CLI can already write projects.

Read the case title, package link and one distinctive artifact or finding from the supplied case page. Use the exact .science URL linked by that page. Match that package to the page and the [official case manifest](https://statics.aipoch.com/open-science/usecases/manifest.json). Verify its exact byte count and SHA-256. Stop on a mismatch. A previously downloaded copy may be reused after the same verification.

Use the running desktop's own service, profile and CLI. On macOS the bundled CLI is typically Contents/Resources/backend/cli.mjs, run with Contents/Resources/node-runtime/node. For the Windows 1.3.4 packaged desktop observed in the test record, the entry points were `<install-dir>\resources\node-runtime\node.exe` and `<install-dir>\resources\cli\index.mjs`; verify their existence and the installed help rather than applying the Mac layout. Quote paths and pass arguments separately. CLI and desktop version numbers can differ: identify the running desktop/service version, not just the CLI `version` output. Use only flags supported by that installed CLI; add `--json` only if supported, since import may already return JSON without it.

Confirm the backend is running and that the intended desktop is connected. A single boolean may not describe all connections; interpret status fields according to the installed release. After launch, allow startup to complete and retry a read-only status check once on a transient timeout. Use the desktop's supported Retry/Reconnect control for a failed service. On Windows verify that the app is running in the user's interactive desktop. If needed, ask the user to launch it from Start. Avoid creating a second background service for this task.

**Windows startup handling:** start the installed desktop in the user's interactive session and check that it remains running after the launch command returns. If it prints Node help instead of opening a window, inspect the launch context for an inherited `ELECTRON_RUN_AS_NODE`; unset that variable for the desktop launch subprocess only. Inspect relevant inherited Node options before changing them; do not globally remove proxy, certificate or security settings. If the agent's execution session terminates its child GUI processes, ask the user to open OS from Start and leave it running, then verify the service and workspace again. Record this manual launch; do not count it as automatic foregrounding. Do not try scheduled tasks, persistent launchers, alternate equivalent commands or a second backend to work around a security denial. If standalone `start` reports a missing backend, use the installed desktop's supported host rather than building or installing an unrelated service.

**Capacity check:** inspect free space on the download, OS temporary and research-data volumes before a large import. The package's compressed size, logical file totals and peak physical disk use are different. Use supported OS estimates where available; do not invent a fixed expansion requirement. If OS reports insufficient space, preserve the exact path, stage and required/available values; a “next stage” estimate is not a whole-import guarantee. Stop repeated imports, preserve existing data and request a specific permitted cleanup/location action. Moving only the downloaded package does not move Windows temporary storage. Do not delete user files or rewrite global TEMP settings automatically.

A backend/database/desktop connection failure still blocks import. Missing optional CodeBuddy or model configuration can be deferred once the archive workspace is usable.

Choose a unique project title containing the case title and a timestamp. Use the supported CLI import on the intended profile, for example:

    open-science session import "$archive_path" --new-project "$unique_project_name" --non-interactive

Use the bundled executable and supported profile option where appropriate. Save the returned project ID and session ID. Use these IDs to distinguish this import from same-name older projects. On interruption or timeout, check this operation's result before retrying; an import can succeed before a response is lost. Stop on an uncertain outcome rather than creating duplicates. A supported desktop import is an alternative when no CLI import has started. MCP is optional for verification; it is not required for this CLI path.

## 5. Bring forward OS and guide the final click

Let the desktop respond to import completion. If it remains in the background, use a permitted activation mechanism for the installed app, such as its documented protocol or the operating system's ordinary application activation. The basic open-science://open URI activates the registered app; it does not encode a session ID. If multiple OS builds exist, target the intended installation explicitly.

After import, give a short completion statement and ask whether the user can see the OS window. Guide the remaining click in the same message, in the user's language. For example:

> “线虫案例已导入，我已尝试唤起 Open-Science。你现在看到 OS 窗口了吗？如果看到导入完成提示，请点「Open imported Session」查看案例正文；如果正文已经显示，就不需要再点。如果没有看到 OS，请告诉我当前画面。”

Adapt the case name and describe only actions actually completed. If activation was confirmed, say that OS was brought forward; if it was attempted but not confirmed, say it was attempted. Use the exact visible button label when available. The import-completion button opens the already imported session: do not tell the user to import the package again. If the button cannot be inspected, condition the instruction on the completion prompt being visible, rather than claiming the button is there.

If the desktop instead shows Projects, identify the exact new project and session from this import's IDs and timestamp. Give that route only as the fallback if the completion prompt is absent. If onboarding remains visible despite an earlier import, report the workspace check as not satisfied. Preserve the existing import IDs, complete step 2 including Finish, and locate that already imported session. Do not import again to fix a display problem. If the data location changed, first resolve the profile/location mismatch without moving or deleting research data silently.

Keep three outcomes separate: (1) import succeeded; (2) OS reached the foreground; (3) the user can see the correct session body. A visible **Open imported Session** is an acceptable one-click handoff, but it is not proof that the session body opened automatically. Ask for user confirmation when direct observation is unavailable. Record whether the user clicked the completion button or manually switched apps. If the user later corrects an earlier observation, update the result accordingly.

Do not require screenshots, screen-recording permission, or Accessibility permission just to finish this archive-viewing task. Do not keep taking screenshots or investigating window lists after import and an ordinary activation attempt when the remaining question can be answered by the user. A process, menu bar, import receipt, MCP lookup, app-specific screenshot, or web replay does not by itself prove what the user sees in the foreground. A screenshot captured after the user's click does not prove automatic opening. Observe the permissions of the receiving assistant; a past WorkBuddy System Events denial on one Mac does not determine every assistant's capabilities.

Record the installed/running version, configuration status, import IDs, and the three distinct outcomes. Keep the user-facing closing message short and centered on the completed import and the remaining click. Configuration may remain pending while the archived case is successfully open. Do not send model test messages as part of this handoff.

## Verification and reporting

Report installation/running version, first-run completion, optional model configuration, import, foregrounding and visible case content as separate results. Record each manual launch, wizard click, authorization and final session-opening click. Do not label the overall task “completed” while the wizard remains visible. A visible import-completion button counts only as the agreed one-click handoff; it does not prove the body is already displayed.

This patch responds to a Windows + WorkBuddy + OS 1.3.4 run in which installation, package verification and CLI import succeeded but no wizard controls were operated. That run did not pass first-run completion or case-display acceptance. The revised sequence has been checked against the guide and OS 1.3.4 source, but has not yet passed a new end-to-end Windows run. Codex, Claude Code and OpenCode are supported as receiving assistants only to the extent their available tools and the installed OS support each operation; they were not verified by that WorkBuddy run.

Reference behavior for OS 1.3.4: [startup gate](https://github.com/aipoch/open-science/blob/v1.3.4/src/renderer/src/pages/onboarding/startup-gate.ts), [model Skip](https://github.com/aipoch/open-science/blob/v1.3.4/src/renderer/src/pages/onboarding/ProviderStep.tsx), [final Finish](https://github.com/aipoch/open-science/blob/v1.3.4/src/renderer/src/pages/onboarding/NotebookStep.tsx). Match controls and CLI capabilities to the installed release rather than assuming they never change.
