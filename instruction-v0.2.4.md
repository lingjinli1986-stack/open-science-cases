# Open this research case in Open-Science
Version 0.2.4 — archive viewing with a user-confirmed desktop handoff

Use the case-page URL and .science package URL in the user's request to identify the target. This guide works across cases and receiving assistants, including WorkBuddy, Codex, Claude Code and OpenCode. Reply in the user's language.

The goal is to import the supplied archive and bring the correct Open-Science desktop window forward. A visible, actionable **Open imported Session** for this import is an acceptable handoff. Opening the matching archived conversation is also complete.

Preserve existing projects, sessions, attachments and working account settings. Reading an archive requires no new model request. The receiving assistant's chat model and the model configured inside OS are independent.

## 1. Install or update the official desktop

Identify the operating system and CPU architecture. Visit the [AIPOCH download page](https://aipoch.com/open-science/download), record the latest stable version shown there and choose the matching official installer. Use the installed app's version when deciding whether to update. Keep a newer installed version and explain any difference. Use the supported updater or official installer for an older version.

Install missing OS using the platform's standard supported flow. Follow the official release's signature and checksum information where provided. Preserve the user's data during an update. This guide uses the official desktop and its existing capabilities.

If installation needs an ordinary approval, identify the exact application and operation and ask the user to approve it through the offered control. Count installation approval separately from model-provider authorization. If the security layer rejects the operation without an approval option, stop automated installation and report its exact message and the incomplete destination. WorkBuddy has rejected temporary-file deletion during a Mac application copy. A verified archive or a partial app directory does not prove installation. Do not retry equivalent commands, disable protections, or delete partial copies without authorization. Give the user the official installation instructions and the required next action; continue only after the permitted installation is complete.

Launch the intended installed desktop. Read the actual running version from About or its desktop service and compare it with the official version after installation or upgrade. Record both values. A downloaded installer version alone is insufficient.

## 2. Reach the workspace; defer optional runtime and model setup if blocked

On an existing profile, retain a compatible working setup. On a new profile, use the visible first-run wizard. Keep the chosen research location. The installer itself does not bind a subscription.

Work on the same desktop/profile that will receive the archive. Use your supported desktop controls. A permitted local browser interface connected to that same OS service may help where the installed release supports the required operation. Keep local sign-in links private. If you cannot operate the required interface, give the user its exact remaining controls in one handoff.

**Prefer the user's requested plan when configuration is available.** For WorkBuddy, use CodeBuddy with the matching regional subscription offered by OS. If the required runtime is already usable, retain it. If installation can proceed normally, use the OS Agent panel's supported installation flow. After an error, missing option, or permission denial, defer CodeBuddy installation for this archive-viewing task.

**Use the supported fallback to finish onboarding.** The official framework guide describes a built-in Open-Science Agent that needs no separate runtime download. If the wizard offers it and its environment check passes, select it to reach the next step. This does not connect the user's WorkBuddy plan. At the model step, use the visible **Skip** or equivalent option when available. Defer optional Notebook/Python/R setup and finish the wizard. A default provider created by Skip is not a confirmed user subscription. Send no model messages with that default.

If an authorized user login is needed and the user is ready, follow the offered subscription flow below. If setup cannot be completed or the user defers it, use Skip and proceed to import once the desktop workspace and import service are usable. State “模型配置暂未完成，先打开已有研究案例。” Missing provider readiness alone is not an import blocker in this version.

If the installed release prevents reaching the workspace without a working runtime, and no ready built-in runtime or supported skip is available, report that specific wizard step and the minimum action required. Do not fabricate a Skip control or change internal settings to bypass onboarding.

## 3. Configure a subscription only when the supported path is available

If runtime or model setup was deferred in step 2, go directly to step 4. Do not restart a failed setup or require authorization again for archive reading.

Respect the user's requested plan, even if a different assistant receives the request. Reuse an existing ready configuration unless the user requests a change. If region or plan is ambiguous and configuration will proceed, ask one focused question. Do not infer region from language or inspect unrelated account files.

For WorkBuddy, check **Settings → Agent** for CodeBuddy. In **Settings → Model**, choose the corresponding CodeBuddy China or International subscription if the installed release offers it. Existing same-region CodeBuddy CLI login can be reused only when OS confirms it is ready. A WorkBuddy desktop login alone does not prove OS access. Otherwise use OS's **Sign in with Open-Science → Sign in with browser**, or the equivalent supported control.

Keep one authorization request active while the owner signs in on the provider's page. A success page in the browser is followed by checking that OS received the account and model list. If a request expires while waiting for the user, explicitly report expiry and offer a fresh request when the user is ready. Do not overlap login attempts. If authorization fails, mark configuration pending and continue archive viewing when the workspace permits it.

Select a Main model from the subscription's returned list using the user's supported preference or its recommended/default choice. Read back the saved Main model and its provider/region. A new provider card alone does not prove Main model changed. Keep passwords, tokens, API keys and authorization URLs out of chat, logs and screenshots.

For Codex, use a compatible OS framework and the offered Codex subscription flow. For Claude Code, use Claude subscription access only where the installed framework offers it. OpenCode identifies a runtime; choose an actually supported authorized provider. Follow the [framework guide](https://aipoch.com/docs/guides/frameworks/) and [provider guide](https://aipoch.com/docs/guides/providers/). These paths have different support and verification states.

Use OS settings and readiness checks only. Do not send an OK request or another model message as part of opening the archive. Report configuration as ready, deferred, or failed independently of import success.

## 4. Verify and import the supplied archive once

Read the case title, package link and one distinctive artifact or finding from the supplied case page. Match the supplied package to the page and the [official case manifest](https://statics.aipoch.com/open-science/usecases/manifest.json). Verify its exact byte count and SHA-256. Stop on a mismatch. A previously downloaded copy may be reused after the same verification.

Use the running desktop's own service, profile and CLI. On macOS the bundled CLI is typically Contents/Resources/backend/cli.mjs, run with Contents/Resources/node-runtime/node. On Windows use the installed launcher documented by that release. Check the installed help before using commands. Quote paths and pass arguments separately.

Confirm the backend is running and that the intended desktop is connected. A single boolean may not describe all connections; interpret status fields according to the installed release. After launch, allow startup to complete and retry a read-only status check once on a transient timeout. Use the desktop's supported Retry/Reconnect control for a failed service. On Windows verify that the app is running in the user's interactive desktop. If needed, ask the user to launch it from Start. Avoid creating a second background service for this task.

A backend/database/desktop connection failure still blocks import. Missing optional CodeBuddy or model configuration can be deferred once the archive workspace is usable.

Choose a unique project title containing the case title and a timestamp. Use the supported CLI import on the intended profile, for example:

    open-science session import "$archive_path" --new-project "$unique_project_name" --non-interactive --json

Use the bundled executable and supported profile option where appropriate. Save the returned project ID and session ID. Use these IDs to distinguish this import from same-name older projects. On interruption or timeout, check this operation's result before retrying; an import can succeed before a response is lost. Stop on an uncertain outcome rather than creating duplicates. A supported desktop import is an alternative when no CLI import has started. MCP is optional for verification; it is not required for this CLI path.

## 5. Bring forward OS and guide the final click

Let the desktop respond to import completion. If it remains in the background, use a permitted activation mechanism for the installed app, such as its documented protocol or the operating system's ordinary application activation. The basic open-science://open URI activates the registered app; it does not encode a session ID. If multiple OS builds exist, target the intended installation explicitly.

After import, give a short completion statement and ask whether the user can see the OS window. Guide the remaining click in the same message, in the user's language. For example:

> “线虫案例已导入，我已尝试唤起 Open-Science。你现在看到 OS 窗口了吗？如果看到导入完成提示，请点「Open imported Session」查看案例正文；如果正文已经显示，就不需要再点。如果没有看到 OS，请告诉我当前画面。”

Adapt the case name and describe only actions actually completed. If activation was confirmed, say that OS was brought forward; if it was attempted but not confirmed, say it was attempted. Use the exact visible button label when available. The import-completion button opens the already imported session: do not tell the user to import the package again. If the button cannot be inspected, condition the instruction on the completion prompt being visible, rather than claiming the button is there.

If the desktop instead shows Projects, identify the exact new project and session from this import's IDs and timestamp. Give that route only as the fallback if the completion prompt is absent. If onboarding remains visible, finish the supported skip path before promising a final click.

Keep three outcomes separate: (1) import succeeded; (2) OS reached the foreground; (3) the user can see the correct session body. A visible **Open imported Session** is an acceptable one-click handoff, but it is not proof that the session body opened automatically. Ask for user confirmation when direct observation is unavailable. Record whether the user clicked the completion button or manually switched apps. If the user later corrects an earlier observation, update the result accordingly.

Do not require screenshots, screen-recording permission, or Accessibility permission just to finish this archive-viewing task. Do not keep taking screenshots or investigating window lists after import and an ordinary activation attempt when the remaining question can be answered by the user. A process, menu bar, import receipt, MCP lookup, app-specific screenshot, or web replay does not by itself prove what the user sees in the foreground. A screenshot captured after the user's click does not prove automatic opening. Observe the permissions of the receiving assistant; a past WorkBuddy System Events denial on one Mac does not determine every assistant's capabilities.

Record the installed/running version, configuration status, import IDs, and the three distinct outcomes. Keep the user-facing closing message short and centered on the completed import and the remaining click. Configuration may remain pending while the archived case is successfully open. Do not send model test messages as part of this handoff.
