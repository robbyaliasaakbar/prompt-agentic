# prompt-agentic

A collection of system prompts and skills for **Udin**, a local agentic AI setup
running on Ollama + OpenWebUI. This repo exists so the setup can be restored
on any machine with a simple clone — and it's public in case it's useful to
anyone else building something similar.

## Structure

### `System Prompt/`
| File | Purpose | Model it's tuned for | Status |
|------|---------|----------------------|--------|
| (filename) | (what it does) | (e.g. Gemma4 12B Q4_K_M) | STABLE / RAW |

### `Skills/`
| File | Purpose | Used in which mode |
|------|---------|---------------------|

## Using this yourself

Everything here is set up as a template. You only need to change **two things**:

1. **Workspace path** — replace the path placeholder in the prompts/skills with
   your own workspace directory.
2. **Soul** — replace the identity/persona block (name, tone, role) with your
   own agent's identity.

Leave everything else as-is — the reasoning structure, tool-calling logic, and
tuning parameters are already validated and work as defaults regardless of
your hardware.

## Setup

1. Install Ollama and OpenWebUI (Docker).
2. Clone this repo.
3. Load the relevant file from `System Prompt/` as your model's system prompt
   (via OpenWebUI custom prompt, or a Modelfile `SYSTEM` block).
4. Load the relevant file from `Skills/` into your MCP/tool-calling setup.
5. Match each prompt to the model it was tuned for — parameters differ per
   model, so mixing them can degrade output quality.

## Notes

- Built and iterated through 100+ calibration runs on consumer hardware
  (no cloud fine-tuning).
- Tuning status per model role:
  - Parsing — STABLE
  - Roleplay — STABLE
  - Brainstorming — RAW (in progress)
  - Code — RAW (in progress)

## License

(add one if you want others to freely reuse/modify — MIT is a common pick for this kind of thing)
