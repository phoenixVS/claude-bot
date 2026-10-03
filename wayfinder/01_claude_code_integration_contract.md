# Ticket: Define Claude Code integration contract

**Type:** `wayfinder:grilling`  
**Status:** Open  
**Assigned:** (unclaimed)  
**Blocks:** [State schema](03_state_schema.md), [Dashboard UI spec](02_dashboard_ui_spec.md)  
**Blocked by:** [Tmux session lifecycle](04_tmux_session_lifecycle.md)

---

## Question

How should the macOS app spawn, communicate with, and read output from Claude Code running in a persistent tmux session?

Specifically:
1. **Spawning:** Does the app call `claude` CLI directly, or manage the tmux session first and then send `claude` commands into it?
2. **Prompt delivery:** How does the app pass the initial goal and subsequent "Update Goal" prompts to Claude Code? Via stdin, file, or tmux send-keys?
3. **Output reading:** Should the app tail `tmux capture-pane` output, or capture Claude Code's stdout/stderr directly?
4. **Session management:** Does the app create a named tmux session on first run and reattach on subsequent runs? What happens on app restart—continue the session or start fresh?
5. **Error handling:** If Claude Code crashes or exits unexpectedly, how does the app detect and respond?

---

## Notes

- This decision blocks the dashboard UI (what data is available to show?), state schema (what do we persist?), and test story.
- Recommend a prototype or spike: test spawning Claude Code in tmux and confirming we can read multi-line output reliably.
