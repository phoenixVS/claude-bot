# Ticket: App entry point & error handling

**Type:** `wayfinder:grilling`  
**Status:** Open  
**Assigned:** (unclaimed)  
**Blocks:** [Test story](08_test_story.md)  
**Blocked by:** None

---

## Question

How should the app be invoked and configured?

Specifically:
1. **CLI invocation:** What should the command look like? (e.g., `claude-runner start`, `claude-runner --goal "my task.md"`, `claude-runner --interactive`)?
2. **Config file:** Should the app read a config file (e.g., `~/.config/my-app/config.json` or `.claude-runner.json` in the project)?
3. **Goal input:** Confirm flow: app looks for prompt file (default path or provided path), or reads from interactive input if file doesn't exist?
4. **Error handling:** How should the app respond to:
   - Claude Code crashes mid-run?
   - Dashboard port already in use?
   - Tmux session already exists?
   - Permission errors (sudo)?
5. **Graceful shutdown:** Should Ctrl+C on the CLI cleanly stop the run and save state?

---

## Notes

- Unblocked; can be sketched independently.
- Answer informs the test story (what does "working" look like?).
