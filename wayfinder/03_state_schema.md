# Ticket: State schema

**Type:** `wayfinder:grilling`  
**Status:** Open  
**Assigned:** (unclaimed)  
**Blocks:** None  
**Blocked by:** [Claude Code integration contract](01_claude_code_integration_contract.md)

---

## Question

What is the JSON structure for persisting task state, iterations, logs, and metadata in `~/.config/my-app/tasks/`?

Specifically:
1. **Directory structure:** One JSON file per task (task.json + logs.json)? Single file? Nested directories by timestamp?
2. **Task metadata:** What fields? (id, name, created_at, updated_at, status, max_iterations, current_iteration, goal, elapsed_time)?
3. **Logs storage:** Should each iteration's Claude Code output be a separate log entry? How do we handle multi-line output?
4. **Dashboard query:** What does the app need to read from state to populate the dashboard? Can it be efficient?
5. **Recovery:** If the app crashes, what state should be recovered on restart? The current run? All tasks?

---

## Notes

- Blocked by Claude Code integration contract (what data does the integration produce?).
- Recommend sketching the JSON structure first, then validating with the dashboard needs.
