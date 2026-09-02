# Agent Handbook

Repository-owned handbook for autonomous and human agents working on `orangesor`.

## Rules

- **Theme Architecture**: This repository is a VS Code / Cursor color theme extension contributing `Orangesor Dark` (`themes/cursor-dark.json`) and `Orangesor Light` (`themes/cursor-light.json`), defined in `package.json`.
- **Palette Identity**:
  - Accent: `#F54E00` (warm orange accent across dark and light variants).
  - Dark background: `#14120B` (brownish-black).
  - Light background: `#F7F7F4` (warm beige).
- **Accessibility & Contrast**:
  - Maintain WCAG AA compliance (minimum 4.5:1 contrast ratio for all critical text and token pairs).
  - Use darker accent shades where `#F54E00` fails contrast thresholds on light surfaces.
- **Theme Parity & Semantics**:
  - Keep dark and light theme scopes in parity across workbench tokens, syntax highlighting (30+ token groups), bracket pair colors (`editorBracketHighlight`), and source control graph (`scmGraph`).
  - Maintain semantically correct ANSI color mapping (green=green, cyan=cyan).
  - Do not introduce deprecated VS Code color keys (e.g., `activityBarTop`, `paneComposite`, `paneCompositePart`, `sideBySideEditor`).
- **Repository Hygiene**:
  - Never commit `.vsix` binaries or build output; ensure `.gitignore` patterns remain respected.
  - Keep extension icon (`images/icon.png`) compressed and lightweight.
  - Maintain `.vscodeignore` to exclude development and IDE files while packaging `CHANGELOG.md` with releases.
  - `"task.allowAutomaticTasks": "off"` is set in `.vscode/settings.json`.
- **Scope Discipline**: Never modify unrelated files or invent conventions not substantiated by repository files.

## Skills

Reusable task recipes belong in `.agents/skills/`.
- No skills are defined in the repository today; the `.agents/skills` directory is intentionally omitted until reusable recipes are added.
- When adding reusable recipes, store each recipe as a modular script or markdown recipe under `.agents/skills/<skill-name>/`.

## Workflows

- **Theme Editing**:
  - Modify token and workbench color mappings directly in `themes/cursor-dark.json` and `themes/cursor-light.json`.
- **Local Testing & Development**:
  - Launch an Extension Development Host window in VS Code / Cursor via `F5`.
  - Open Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`), run **Preferences: Color Theme**, and select **Orangesor Dark** or **Orangesor Light** to inspect changes.
- **Packaging**:
  - Build the extension package using `@vscode/vsce`:
    ```bash
    npm install -g @vscode/vsce
    vsce package
    ```
    Outputs `orangesor-<version>.vsix`.
- **Releases & Versioning**:
  - Bump `version` in `package.json`.
  - Record release changes in `CHANGELOG.md`.
  - Keep documentation and preview assets in `README.md` and `images/` aligned with theme updates.

## Memory

- Agent memory and persistent architectural records point to versioned markdown files under `docs/`.
- The repository does not currently maintain a `docs/` directory or existing memory files; do not create them until persistent operational records are explicitly introduced.
- Never rely on vendor-proprietary memory features; all context must reside in versioned repository markdown.
