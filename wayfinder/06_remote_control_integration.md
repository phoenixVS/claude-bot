# Ticket: Remote Control integration

**Type:** `wayfinder:grilling`  
**Status:** Open  
**Assigned:** (unclaimed)  
**Blocks:** None  
**Blocked by:** [Dashboard UI spec](02_dashboard_ui_spec.md)

---

## Question

How should the macOS app expose task status and logs to Claude's Remote Control feature on iPhone?

Specifically:
1. **Data exposure:** What information should be available via Remote Control? (task status, last N log lines, current iteration)?
2. **Integration method:** Does Claude Remote Control have an API or webhook we can call, or do we expose it via the local dashboard and Remote Control reads from there?
3. **Limitations:** Based on research, Remote Control requires approval for tool calls. What does this mean for our read-only status checks—can we surface them without approval?
4. **Phase 1 scope:** For phase 1, is basic status + recent logs enough, or does Remote Control need richer integration?

---

## Notes

- Blocked by dashboard UI spec (need to know what the dashboard looks like before we expose it to Remote Control).
- Research ticket: use the Skill tool to investigate Claude Remote Control's actual API/integration points.
- The earlier research found that Remote Control requires approval for tool calls, which blocks autonomous mode—but read-only access should be possible.
