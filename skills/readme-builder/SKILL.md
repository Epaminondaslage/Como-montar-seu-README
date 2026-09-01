---
name: readme-builder
description: Generate or modernize a project's README.md following a fixed 9-section structure (title/badges, description, TOC, demo, prerequisites, installation, usage, contribution, license). Use when the user asks to "create a README", "write a README", "montar um README", "modernizar o README", or invokes /readme-builder.
---

# README Builder

Generates a project README by inspecting the actual repository — never
placeholder text — following the structure documented in
[Como-montar-seu-README](https://github.com/Epaminondaslage/Como-montar-seu-README).

## Process

1. **Inspect the repo before asking anything.** Read (in this order, whichever exist): `package.json`/`pyproject.toml`/`Cargo.toml`/`go.mod` (name, description, dependencies, scripts), any existing `LICENSE` file, the primary language and entry point, existing tests or CI config, and any existing README to preserve tone/content worth keeping.
2. **Ask only what the repo can't tell you** — one question at a time:
   - Project name and one-line purpose, if not inferable.
   - Target audience (who is this README for: end users, contributors, both?).
   - License, if no `LICENSE` file exists.
   - Whether a demo screenshot/GIF exists or should be referenced as a placeholder path.
3. **Write the 9 sections, in this order, skipping only what genuinely doesn't apply** (e.g. a library has no "Uso" screenshot, a script has no "Contribuição" if it's personal-use only — ask before skipping, don't assume):
   1. **Título e badges** — project name as `# H1`; badges only for facts you can verify (license file present, CI config present, version in a manifest) — never fabricate a badge for something that doesn't exist in the repo.
   2. **Descrição** — what it does, for whom, what problem it solves. Derived from the code/manifest, not generic filler.
   3. **Sumário** — a working table of contents with anchor links matching the actual headers you write.
   4. **Demonstração** — a screenshot/GIF reference if one exists in the repo (check `docs/`, `screenshots/`, root); otherwise omit the section rather than invent a placeholder image.
   5. **Pré-requisitos** — exact versions/tools found in the manifest or config files, not generic guesses.
   6. **Instalação** — the actual install command for this stack (`npm install`, `pip install -r requirements.txt`, `cargo build`, etc.) verified against what's really in the repo.
   7. **Uso** — a real example: an actual script invocation, API call, or command found in the repo's own scripts/tests.
   8. **Contribuição** — only if the project looks intended for external contributors (has a LICENSE permissive enough, a public remote, or the user says so); otherwise skip.
   9. **Licença** — from the actual `LICENSE` file if present; ask if absent, never assume MIT.
4. **Markdown hygiene**: every code fence must close; a fenced block containing another fenced block (e.g. showing markdown syntax itself) uses one more backtick than its content (4 backticks around 3). Verify every anchor link in the TOC matches an actual header slug before finishing.
5. **Show the draft in chat first** for approval before writing the file, unless the user explicitly said to write directly.

## Anti-patterns to avoid

- Never write "Descrição do projeto aqui" or any bracketed placeholder — if you don't have the information, ask instead of guessing, or omit the section.
- Never add a badge for a service not actually configured in the repo (no CI badge without a CI config file, no coverage badge without a coverage tool).
- Never claim a license the repo doesn't declare.
- Keep the tone matching the project's existing voice if a README already exists — this skill restructures and fills gaps, it doesn't impose a new personality on someone else's project uninvited.
