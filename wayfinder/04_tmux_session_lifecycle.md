# Ticket: Tmux session lifecycle

**Type:** `wayfinder:grilling`  
**Status:** Open  
**Assigned:** (unclaimed)  
**Blocks:** [Claude Code integration contract](01_claude_code_integration_contract.md)  
**Blocked by:** None

---

## Question

How should the app manage the tmux session that Claude Code runs in?

Specifically:
1. **Session naming:** What should the named tmux session be called? (e.g., `claude-runner` or `claude-code-task-{timestamp}`)?
2. **Startup behavior:** On app start, should the app create a new session each time, or attach to an existing one?
3. **Window/pane structure:** Should Claude Code run in a single pane, or do we need multiple windows?
4. **Cleanup:** When the app exits, should the tmux session be killed, or left running so the user can attach manually?
5. **Persistence across restarts:** If the user closes the app and reopens it 10 minutes later, should they see the old Claude Code session or a fresh one?

---

## Notes

- Unblocked; can be resolved independently.
- Answer will influence the Claude Code integration contract (session naming, how we spawn Claude into the session).
