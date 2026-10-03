# Ticket: Sleep control integration

**Type:** `wayfinder:task`  
**Status:** Open  
**Assigned:** (unclaimed)  
**Blocks:** None  
**Blocked by:** None

---

## Question

How should the app handle macOS sleep control?

Specifically:
1. **Startup:** When the app starts, run `sudo pmset -a disablesleep 1`. Should the app prompt for sudo, or assume the user has already granted passwordless sudo for this command?
2. **Shutdown:** When the app exits cleanly, run `sudo pmset -a disablesleep 0` to re-enable sleep?
3. **Error handling:** If the pmset command fails (no sudo, permission denied), should the app abort or proceed anyway?
4. **Always-awake window:** The user specified "always while the app is running." Confirm: sleep should stay disabled even when Claude Code is idle between iterations?

---

## Notes

- This is a task (manual integration work), not a decision. The answer is mostly straightforward; the tricky part is sudo handling.
- Recommend: prompt user for sudo on first run, cache it, or use a helper script that's pre-configured with sudo.
