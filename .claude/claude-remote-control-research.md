# Claude Remote Control: Capabilities & Limitations Research

## Overview

Claude Remote Control is an official feature that allows controlling Claude Code sessions on a Mac from the Claude iOS app. The local Claude Code process runs on your machine and initiates an outbound HTTPS connection to Anthropic's cloud, polling for instructions from the mobile app.

**Source:** [Claude Code Docs - Remote Control](https://code.claude.com/docs/en/remote-control)

## Capabilities

### What Remote Control CAN do:

1. **Session Sync**: Mirror every Claude Code session running on your Mac to your iPhone in real-time.
   - Source: [Anthropic Remote Control Release](https://venturebeat.com/orchestration/anthropic-just-released-a-mobile-version-of-claude-code-called-remote)

2. **Message Sending**: Send messages to Claude Code from your phone, terminal, or both—conversation stays synced across devices.
   - Source: [Claude Code Remote Control Guide](https://blakecrosley.com/blog/claude-code-desktop-remote-control-guide)

3. **Tool Call Approval**: Approve or deny tool calls / permission prompts with one tap from anywhere, without returning to your desk.
   - Source: [Claude Code Docs - Remote Control](https://code.claude.com/docs/en/remote-control)

4. **Full Local Context**: Access to local filesystem, project configuration, environment variables, and all configured MCP servers—identical to what's available at the terminal.
   - Source: [Claude Code Remote Control Capabilities](https://medium.com/@lalatenduswain/claude-code-remote-control-in-2026-how-to-control-your-local-terminal-from-any-device-575fca4ab0a1)

5. **Push Notifications**: Claude can send push notifications to your phone when tasks complete or decisions are needed.
   - Source: [How to use Claude Code from your iPhone](https://tacticremote.com/blog/2026-02-28-how-to-run-claude-code-from-iphone/)

6. **Terminal Access**: Read the full transcript and send keystrokes/messages into the terminal session.
   - Source: [Claude Code Phone Integration](https://zackproser.com/blog/claude-code-phone-remote-control)

### What Remote Control CANNOT do:

1. **Single Session Limit**: Only one active remote session per Claude Code instance. Multiple concurrent sessions require multiple Claude Code processes or use of `--spawn worktree` flag (requires Git repo).
   - Source: [Claude Code Remote Control Limitations](https://www.codebridge.tech/articles/claude-code-remote-control-what-tech-leaders-need-to-know-before-they-use-it-in-real-engineering-work)

2. **Requires Active Terminal**: Claude Code must keep running locally. Closing the terminal window or stopping the process ends the remote session immediately—no background daemon persistence.
   - Source: [Claude Code Remote Control Setup](https://claudefa.st/blog/guide/development/remote-control-guide)

3. **Network Timeout**: ~10-minute timeout if the Mac loses internet connectivity. If disconnected longer than ~10 minutes, the session exits.
   - Source: [Claude Code Remote Control Limitations](https://tessl.io/blog/claude-code-gets-remote-access-to-live-local-terminals)

4. **Permission Approval Overhead**: Tool calls still require confirmation even with Remote Control active. There is no reliable way to pre-approve all permissions for fully unattended execution.
   - Source: [Claude Code Remote Control: Advantages & Limits](https://www.codebridge.tech/articles/claude-code-remote-control-what-tech-leaders-need-to-know-before-they-use-it-in-real-engineering-work)

5. **Plan Requirements**: Pro or Max plans only—Team and Enterprise plans are not yet supported. API key authentication is not supported.
   - Source: [Claude Code Remote Control Setup](https://www.datacamp.com/tutorial/claude-code-remote-control)

6. **No Network Isolation**: Requires either same Wi-Fi or Tailscale for remote access. Not suitable for pure internet-only scenarios without additional setup.
   - Source: [Claude Remote Control on iPhone & Android](https://clauderemotecontrol.com/mobile/)

## Key Difference: Remote Control vs. Custom App

### Remote Control (Built-in)
- **Pros**: Official, no custom build, uses existing Claude auth, minimal setup
- **Cons**: Single session limit, permission approval required, network timeout, limited to Pro/Max plans

### Custom Companion App
- **Pros**: Full control over UX, no permission approval bottleneck, can manage multiple sessions, custom auth flow, better suited for autonomous agent mode
- **Cons**: Additional development required, separate app distribution, more complex architecture

## Recommendation for Your Use Case

**For autonomous agent execution** (your Hermes/openClaw use case), Remote Control has a critical limitation: tool calls require explicit approval, blocking unattended execution. A custom companion app would be more suitable because:

1. You could pre-configure permissions once to allow fully autonomous operation
2. You could multiplex multiple agent sessions without spawning multiple Claude Code processes
3. You could implement custom agents that don't require permission prompts (delegated authority)
4. You control the entire UX flow designed for agent monitoring, not general Claude interaction

**Start with Remote Control for phase 1** (read-only status check from iPhone), but plan a **custom app for phase 2** (autonomous agent execution with interactive control).

---

## Sources

- [Claude Code Docs - Remote Control](https://code.claude.com/docs/en/remote-control)
- [Claude Code Docs - Mobile](https://code.claude.com/docs/en/mobile)
- [Anthropic Remote Control Release - VentureBeat](https://venturebeat.com/orchestration/anthropic-just-released-a-mobile-version-of-claude-code-called-remote)
- [Claude Code Mac Desktop + Remote Control Guide](https://blakecrosley.com/blog/claude-code-desktop-remote-control-guide)
- [Claude Code Remote Control in 2026 - Medium](https://medium.com/@lalatenduswain/claude-code-remote-control-in-2026-how-to-control-your-local-terminal-from-any-device-575fca4ab0a1)
- [Claude Code Phone Remote Control](https://zackproser.com/blog/claude-code-phone-remote-control)
- [Claude Code Remote Control: Setup Guide 2026](https://claudefa.st/blog/guide/development/remote-control-guide)
- [Claude Code Remote Control: Limitations & Advantages](https://www.codebridge.tech/articles/claude-code-remote-control-what-tech-leaders-need-to-know-before-they-use-it-in-real-engineering-work)
- [Claude Code Remote Control - DataCamp](https://www.datacamp.com/tutorial/claude-code-remote-control)
- [How to Use Claude Code from iPhone](https://tacticremote.com/blog/2026-02-28-how-to-run-claude-code-from-iphone/)
- [Claude Remote Control on iPhone & Android](https://clauderemotecontrol.com/mobile/)
- [Claude Code Remote Control - Tessl](https://tessl.io/blog/claude-code-gets-remote-access-to-live-local-terminals)
