# Security

## Supported versions

Only the latest release receives fixes.

## Reporting a vulnerability

Please **don't open a public issue**. Use **Security › Report a vulnerability** in this
repository (GitHub's private reporting): only the maintainer can read it. Include the
Pane version, macOS version and the steps to reproduce. You will get an answer within a
week.

## How Pane protects you

Pane controls displays and, on request, runs your own shell commands, so its entry
points are deliberately narrow:

- **`pane://` links** (any web page or email can open one) can only run display
  controls from an allow-list. Shell commands, file writes, settings import/export,
  security preferences and configuration are refused. Parameter names must be plain
  words, so a link can't smuggle in extra arguments.
- **The local HTTP server** is off by default. When on, it listens on 127.0.0.1 only,
  accepts only the exact host names `127.0.0.1` and `localhost` (no DNS rebinding),
  refuses requests coming from web pages (`Origin`, `Sec-Fetch-Site`) and can require a
  token. It has the same allow-list as links.
- **Imported settings files** that would add shell commands (commands on connect,
  disconnect, sleep, wake, or custom controls) are shown to you and need your
  confirmation first.
- **Risky display changes** (resolution, refresh, rotation, EDID, colour mode) revert by
  themselves unless you confirm them, and resets always take a backup first.
- Pane has no account, no telemetry and no network traffic except the devices you add
  yourself (network TVs, LED processors) and the local server if you turn it on.
