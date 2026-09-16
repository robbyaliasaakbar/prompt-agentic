# prompt-agentic

A collection of system prompts and skills for **Udin**, a personal agentic AI
setup. These prompts aren't tied to one runtime — they're written to be
portable across any tool that accepts a custom system prompt or agent
definition (local LLM UIs, IDE agents, CLI coding agents, etc).

This repo is public in case it's useful to anyone building something similar.

## Structure

### `System Prompt/`
| File | Purpose | Status |
|------|---------|--------|
| (filename) | (what it does) | STABLE / RAW |

### `Skills/`
| File | Purpose | Notes |
|------|---------|-------|

## Using this yourself

These are template prompts. You only need to change **two things** before
dropping them into any tool:

1. **Workspace path** — replace the path placeholder with your own project/
   workspace directory.
2. **Soul** — replace the identity/persona block (name, tone, role) with
   your own agent's identity.

Everything else — reasoning structure, tool-calling logic, tuning notes —
is meant to work as-is regardless of hardware or runtime.

## Where to put these, per tool

| Tool | Where the prompt goes |
|------|------------------------|
| **Ollama** | `SYSTEM` block in a Modelfile, or passed via API `system` field |
| **OpenWebUI** | Workspace → Models → custom system prompt field |
| **Claude Code** | `CLAUDE.md` in the project root (or `~/.claude/CLAUDE.md` for global) |
| **Cline** | `.clinerules` in the project root, or Cline's custom instructions setting |
| **VS Code (GitHub Copilot)** | `.github/copilot-instructions.md`, or a custom chat mode file under `.github/chatmodes/` |
| **OpenCode agents** | agent config's system prompt field (check your OpenCode agent definition file) |
| **Antigravity agents** | agent definition's system/persona field |
| *(any other tool)* | Anywhere it accepts a system prompt / agent instructions file — same content works, just paste it in |

> Exact filenames/paths vary by tool version — check the tool's docs if the
> path above has changed.

## Notes

- Developed and refined through 100+ calibration runs, tested across
  multiple runtimes and consumer hardware.
- Tuning status per role:
  - Parsing — STABLE
  - Roleplay — STABLE
  - Brainstorming — RAW (in progress)
  - Code — RAW (in progress)

## License

(add one if you want others to freely reuse/modify — MIT is a common pick)
