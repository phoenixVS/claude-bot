# Ticket: Test story for phase 1

**Type:** `wayfinder:grilling`  
**Status:** Open  
**Assigned:** (unclaimed)  
**Blocks:** None  
**Blocked by:** [Claude Code integration contract](01_claude_code_integration_contract.md), [Dashboard UI spec](02_dashboard_ui_spec.md), [App entry point](07_app_entry_point.md)

---

## Question

How do we validate that phase 1 is working end-to-end?

Specifically:
1. **Happy path:** What's the minimal scenario that proves the app works? (e.g., "Run the app with a 3-iteration task, see logs on the dashboard, task completes")?
2. **Manual testing:** What steps should a human follow to verify phase 1?
3. **Test coverage:** Should we write automated tests (unit, integration, e2e), or is manual testing + documentation enough for phase 1?
4. **iPhone test:** How do we verify Remote Control status checks work from iPhone? (manual connection via Tailscale?)
5. **Success criteria:** What should we be able to demonstrate by the end of phase 1?

---

## Notes

- Blocked by the core design tickets: need to understand Claude Code integration, dashboard UI, and CLI invocation before defining the test story.
- Recommend: a living checklist, not a test suite, for phase 1. Formalize testing in phase 2.
