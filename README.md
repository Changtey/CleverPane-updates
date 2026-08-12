<p align="center">
  <img src="assets/cleverpane-logo.svg" width="112" alt="CleverPane logo">
</p>

<h1 align="center">CleverPane</h1>

<p align="center">
  A Windows AI assistant that works beside Microsoft Word, Excel, and PowerPoint and can make real, controlled changes to the file you have open.
</p>

<p align="center">
  <a href="https://github.com/Changtey/CleverPane-updates/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/Changtey/CleverPane-updates?display_name=tag&sort=semver"></a>
  <img alt="Platform" src="https://img.shields.io/badge/platform-Windows-0078D4">
  <img alt="Microsoft Office" src="https://img.shields.io/badge/Microsoft%20Office-Word%20%7C%20Excel%20%7C%20PowerPoint-185ABD">
  <img alt="Current status" src="https://img.shields.io/badge/status-active%20development-f59e0b">
</p>

## What CleverPane is

CleverPane turns plain-language requests into useful work inside desktop Microsoft Office. It opens as a task pane beside the active document, reads only the context needed for the request, and uses Office's own automation system to edit the live file.

It is designed to help both beginners and experienced users write, calculate, format, redesign, explain, and automate Office work without memorizing every ribbon command or formula.

Examples:

- "Make this report look professional."
- "Rewrite only the selected paragraph in a formal tone."
- "Explain this formula and correct it if necessary."
- "Format this table, keep every value and formula unchanged."
- "Redesign the active slide and preserve its meaning."
- "Create a clean five-slide presentation from these points."

## Main features

### One assistant for three Office applications

| Application | What CleverPane can do |
| --- | --- |
| **Word** | Read document structure, work on selected text, rewrite or insert text, find and replace, apply fonts and paragraph styles, create tables, add comments, professionalize a document, undo AI actions, and export to PDF. |
| **Excel** | Read sheets and selected ranges, write values in batches, test formulas before inserting them, inspect formula results, format ranges, set page layout, autofit columns, redesign a sheet without changing its data or formulas, and create charts. |
| **PowerPoint** | Read slides and selected shapes, rewrite selected or named text, add clean slides, format selected items, redesign one slide or a full deck, add text boxes, and create speaker notes. |

### Context-aware work

- Detects whether Word, Excel, or PowerPoint is active.
- Uses the current selection as the default target.
- Keeps chat history, model choice, drafts, attachments, and running work separate for each Office file.
- Stops safely if the active document changes during a task.
- Groups repeated Excel formatting into larger safe ranges when possible.

### AI services and models

CleverPane supports several ways to connect an AI service:

- Official ChatGPT/Codex sign-in, including multiple isolated accounts.
- OpenAI API.
- Anthropic Claude.
- Google AI Studio (Gemini), including multiple API keys.
- DeepSeek, Kimi, MiniMax, xAI/Grok, 9Router, and OmniRoute.
- Custom OpenAI-compatible and Anthropic-compatible services.

The available model list is detected from the selected service when supported. Reasoning levels are shown only when the chosen model supports them. If a configured account or key reaches a limit before output begins, CleverPane can try another enabled route without repeating completed Office changes.

You provide and control your own AI access. Provider charges, limits, and availability are determined by the provider, not by CleverPane.

### Attachments and visual checking

CleverPane can use common images, PDFs, Word files, spreadsheets, presentations, and text files as request context. It can also capture the active Office window after significant work so the AI can visually check the result.

Whole-screen sharing and web searches require confirmation because they can expose or transmit information outside the active Office file.

### Personal learning, under your control

CleverPane can remember short preferences such as a preferred Word font or a preference for concise answers.

- Clear "always" preferences can be saved immediately.
- Ordinary style instructions must be repeated before they become preferences.
- Preferences are stored locally for the current Windows user.
- Document contents, attachments, assistant replies, passwords, account details, links, and long identifying numbers are excluded from learning.
- You can review, edit, pause, remove, or erase learned preferences in Settings.
- The current request and every safety rule always take priority over an older preference.

This is a small, inspectable preference profile. It is not hidden training of an AI model.

## Safety and privacy

CleverPane is built around visible and reversible work:

- It reads a file before changing it and targets the selected content when possible.
- New Excel formulas are tested before being written.
- Destructive actions require confirmation.
- Completed edits are kept if a long task reaches its Office-action safety limit; the app pauses and asks the user to continue instead of repeatedly calling tools.
- API secrets are encrypted with Windows Data Protection for the current Windows account.
- Provider passwords stay on the provider's own sign-in page and are not requested by CleverPane.
- Personal learning is local, inspectable, optional, and reversible.
- Update notices are signed, and every downloaded installer is checked against its expected size and SHA-256 fingerprint before it can run.

When a cloud AI service is selected, the information needed for the request is sent to that service. Users should follow their organization's data rules and the chosen provider's privacy terms.

## Interface

- Native Office task pane that reserves document space instead of covering the worksheet, page, or slide.
- Light and dark themes that follow the active Office theme.
- Word-blue, Excel-green, and PowerPoint-orange accents.
- Streaming replies, visible Office actions, Stop control, conversation history, attachments, and token information.
- Provider, model, and supported reasoning-level selectors.
- No separate tray or taskbar clutter: the helper starts with an Office document and exits after the last supported Office file closes.

## Requirements

- 64-bit Windows.
- Desktop Microsoft Word, Excel, or PowerPoint with normal COM registration.
- An internet connection for cloud AI services, model discovery, web search, and software updates.
- Access to at least one supported AI service or compatible endpoint.

CleverPane is a Windows desktop application. It does not support Office for the web, macOS, Android, iOS, or unsupported Microsoft Store-only Office installations.

## Install or update

1. Download the newest installer from [GitHub Releases](https://github.com/Changtey/CleverPane-updates/releases/latest).
2. Save your Office files.
3. Run `CleverPane-Setup-<version>.exe` as an administrator.
4. Open a Word document, Excel workbook, or PowerPoint presentation.
5. Open the **CleverPane** ribbon tab and choose **Open Assistant** if the pane is not already visible.
6. In Settings, connect an AI service and select a model.

Existing settings under `%APPDATA%\MSOfficeAI` are preserved during an update. The legacy internal folder name remains for upgrade compatibility.

### Secure automatic updates

CleverPane checks the signed stable update notice once a day while Office is in use. A manual update check is also available in the top bar. The app downloads an update only after the user agrees, verifies it, waits for Word, Excel, and PowerPoint to close, and then starts the normal installer.

## Current release

### CleverPane 1.0.24

- Adds selectable chat text with quick copy and edit controls.
- Keeps saved chat history synchronized when a previous message is edited.
- Checks up to 500 contiguous Excel formula cells in one fast batch.
- Groups nearby Excel reads to reduce repeated Office actions.
- Keeps rate-limit and quota messages accurate when switching between saved accounts or keys.
- Avoids duplicate automatic retries when CleverPane is already handling fallback.

Download: [CleverPane 1.0.24](https://github.com/Changtey/CleverPane-updates/releases/tag/v1.0.24)

SHA-256:

```text
1050d149fb906cacaa1d467b2373fe37e4dee9212a1f6d47960ec2ea89247321
```

## Development and verification status

CleverPane is actively developed. Version 1.0.24 passed **195 automated checks**.

Important current limits:

- Inserting or generating new pictures inside Office files is planned for a later phase. Existing selected pictures can be inspected or repositioned.
- AI output can be wrong. Review important content, calculations, and changes before relying on them.
- The Windows installer is currently distributed without a commercial Authenticode certificate, so Windows may show a publisher warning. Always download from this repository and compare the SHA-256 fingerprint when in doubt.
- Some advanced roadmap items are still under development and are not presented here as completed features.

## Troubleshooting

- **The pane is not visible:** Open an Office file, select the CleverPane ribbon tab, and choose **Open Assistant**.
- **A model cannot complete a request:** Read the specific message. It may indicate missing model access, an account usage limit, a temporary provider issue, an invalid key, or a long Office task that paused safely.
- **A long task paused:** Review the completed work, then ask CleverPane to continue with the remaining part.
- **The model list is empty:** Reconnect the selected service or refresh its models in Settings.
- **An update will not install:** Save and close Word, Excel, and PowerPoint, then try again.

For a problem report, include the CleverPane version, Office application, Windows version, selected AI service and model, the action you requested, and the exact visible error. Never include passwords, API keys, OAuth tokens, confidential documents, or personal data.

## Repository purpose

This public repository is the official download and signed-update channel for CleverPane. It contains release information and the public update notice. The full application source code is not currently published here.

## Contact

**Created by Changtey W Momin**

- Email: `Changwatre@gmail.com`
- WhatsApp: `+91 9875482192`

When requesting support, do not send passwords, API keys, account tokens, confidential Office files, or sensitive personal information.

## Disclaimer

CleverPane is an independent application. It is not affiliated with, endorsed by, or sponsored by Microsoft, OpenAI, Anthropic, Google, or the other AI service providers it can connect to. Microsoft, Word, Excel, PowerPoint, ChatGPT, Claude, Gemini, and other product names are trademarks of their respective owners.

