# Wayfinder Map: Claude Code Autonomous Runner

**Label:** `wayfinder:map`

---

## Destination

A macOS CLI app (Node.js + TypeScript) that keeps the Mac awake, runs Claude Code in a persistent tmux session in autonomous or interactive mode, and provides a local web dashboard for monitoring and control. Phase 1: macOS app + Remote Control integration for read-only iPhone status checks. Phase 2 (separate effort): custom companion iOS app for full interactive control.

---

## Notes

- **Tech stack:** Node.js/TypeScript, Express/Fastify for dashboard, tmux integration, JSON state
- **Authentication:** Reuse Claude CLI auth from `~/.claude/`
- **Deployment:** Run from source (`npm install` + `npm start`)
- **Skills to consult:** none yet—grilling and domain-modeling have settled the design tree

---

## Decisions so far

*(none yet—frontier is live)*

---

## Open decisions (frontier)

**Unblocked (can start now):**
1. **[Tmux session lifecycle](wayfinder/04_tmux_session_lifecycle.md)** — Create, reattach, cleanup on startup/shutdown ⟵ *Start here*
2. **[Sleep control integration](wayfinder/05_sleep_control_integration.md)** — `pmset` calls on app start/exit
3. **[App entry point & error handling](wayfinder/07_app_entry_point.md)** — CLI flags, config, graceful shutdown

**Blocked (waiting for unblocked tickets):**
4. **[Define Claude Code integration contract](wayfinder/01_claude_code_integration_contract.md)** ← *Blocked by: Tmux session lifecycle*
5. **[State schema](wayfinder/03_state_schema.md)** ← *Blocked by: Claude Code integration contract*
6. **[Dashboard UI/UX spec](wayfinder/02_dashboard_ui_spec.md)** ← *Blocked by: Claude Code integration contract*
7. **[Remote Control integration](wayfinder/06_remote_control_integration.md)** ← *Blocked by: Dashboard UI spec*
8. **[Test story for phase 1](wayfinder/08_test_story.md)** ← *Blocked by: Claude Code integration, Dashboard UI, App entry point*

---

## Not yet specified

- Custom iPhone app architecture (phase 2; out of scope for this map)
- Advanced features: persistence, resumable sessions, multi-task queuing
- Platform-specific macOS permissions/sandboxing

---

## Out of scope (phase 2 or later)

- Custom iOS companion app — saved for separate effort after phase 1 ships
- Remote access beyond Tailscale VPN
- Advanced goal termination detection (Claude signals goal achieved via output)
- Multi-user support or authentication on dashboard
