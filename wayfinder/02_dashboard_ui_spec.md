#Ticket: Dashboard UI/UX spec

**Type:** `wayfinder:prototype`  
**Status:** Open  
**Assigned:** (unclaimed)  
**Blocks:** [Remote Control integration](06_remote_control_integration.md)  
**Blocked by:** [Claude Code integration contract](01_claude_code_integration_contract.md)

---

## Question

What should the web dashboard (localhost:3000) show and allow the user to control?

Specifically:
1. **Live logs:** How much Claude Code output should be visible? Last N lines? Full transcript? Scrollable?
2. **Metadata display:** Current iteration count (e.g., "Iteration 3 of 10"), current goal, elapsed time, status (running/paused/stopped)?
3. **Controls:** Buttons for "Stop Run", "Update Goal" (text input), "Pause"? Where on the page?
4. **Task list:** Should the dashboard show past tasks, or only the current run?
5. **Responsive design:** Does it need to work on iPhone via Tailscale, or assume desktop for now?

---

## Notes

- Blocked by Claude Code integration contract (need to know what data is available to display).
- Recommend a lo-fi prototype (HTML sketch, wireframe) to nail down the layout before coding.
