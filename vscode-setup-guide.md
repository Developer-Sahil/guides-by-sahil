# VSCode Setup Guide

> A complete, opinionated setup guide for Visual Studio Code — from fresh install to domain-specific configuration. Written for beginners setting up their first dev environment, and for experienced developers re-provisioning a new machine.

---

## Table of Contents

1. [Who This Guide Is For](#1-who-this-guide-is-for)
2. [Post-Install Essentials (Everyone)](#2-post-install-essentials-everyone)
3. [Core Settings Configuration](#3-core-settings-configuration)
4. [Must-Have Extensions (Everyone)](#4-must-have-extensions-everyone)
5. [Git & GitHub Integration](#5-git--github-integration)
6. [Terminal Configuration](#6-terminal-configuration)
7. [Keybindings & Productivity](#7-keybindings--productivity)
8. [Domain-Specific Setups](#8-domain-specific-setups)
   - [8.1 Web Development (JS/TS/React/Node)](#81-web-development-jstsreactnode)
   - [8.2 Python / Data Science](#82-python--data-science)
   - [8.3 Machine Learning / Deep Learning](#83-machine-learning--deep-learning)
   - [8.4 AI / LLM Engineering](#84-ai--llm-engineering)
   - [8.5 Cybersecurity](#85-cybersecurity)
   - [8.6 DevOps / Cloud / Infrastructure](#86-devops--cloud--infrastructure)
   - [8.7 Mobile Development](#87-mobile-development)
   - [8.8 C / C++](#88-c--c)
   - [8.9 Java](#89-java)
9. [Remote Development (SSH, WSL, Containers)](#9-remote-development-ssh-wsl-containers)
10. [Settings Sync (Move Between Machines in Minutes)](#10-settings-sync-move-between-machines-in-minutes)
11. [Full Sample `settings.json`](#11-full-sample-settingsjson)
12. [Bonus: Power-User Tricks](#12-bonus-power-user-tricks)
13. [Post-Setup Checklist](#13-post-setup-checklist)

---

## 1. Who This Guide Is For

- **Beginners** installing VS Code for the first time and wanting a sane, non-bloated setup.
- **Experienced developers** reinstalling VS Code on a new machine who want to skip the trial-and-error and get back to full productivity fast.
- **Domain specialists** (ML/DL, Data Science, AI, Cybersecurity, DevOps, Mobile, etc.) who need stack-specific tooling on top of the baseline.

Sections 2–7 apply to **everyone**. Section 8 is a menu — pick what matches your work. Section 9–12 are for anyone who wants to go further.

---

## 2. Post-Install Essentials (Everyone)

After installing VS Code from [code.visualstudio.com](https://code.visualstudio.com/), do these five things before installing a single extension:

### 2.1 Add VS Code to PATH (Windows/macOS)
- **Windows**: Handled automatically by the installer if you checked "Add to PATH" during setup. Verify by opening a terminal and running `code --version`.
- **macOS**: Open VS Code → `Cmd+Shift+P` → run `Shell Command: Install 'code' command in PATH`.
- **Linux**: Already available via the package manager install (`apt`, `dnf`, `snap`, etc.).

### 2.2 Sign in with your Microsoft/GitHub account
This enables **Settings Sync** later (Section 10) — do this early so your setup is portable from day one.

### 2.3 Set your default shell
Windows users should decide now: PowerShell, WSL, or Git Bash. See Section 6.

### 2.4 Disable telemetry (optional but recommended)
`File > Preferences > Settings` → search `telemetry.telemetryLevel` → set to `off` if you prefer a lean, private setup.

### 2.5 Pick a font with ligatures (optional, but worth it)
Recommended: **JetBrains Mono**, **Fira Code**, or **Cascadia Code**. Install the font system-wide, then reference it in `settings.json` (see Section 3).

---

## 3. Core Settings Configuration

Open settings via `Ctrl/Cmd + ,` or edit `settings.json` directly (`Ctrl/Cmd + Shift + P` → `Preferences: Open User Settings (JSON)`).

Key settings every developer should configure:

| Setting | Recommended Value | Why |
|---|---|---|
| `editor.fontSize` | `14`–`16` | Readability over long sessions |
| `editor.fontFamily` | `'JetBrains Mono', Consolas, monospace` | Ligatures + clarity |
| `editor.fontLigatures` | `true` | Cleaner operators (`=>`, `!=`, `>=`) |
| `editor.formatOnSave` | `true` | Consistent formatting without thinking about it |
| `editor.tabSize` | `2` or `4` | Match your team/language convention |
| `editor.minimap.enabled` | `false` | Optional — many devs find it visual noise |
| `editor.cursorBlinking` | `smooth` | Cosmetic, but nice |
| `editor.linkedEditing` | `true` | Auto-renames matching HTML/JSX tags |
| `files.autoSave` | `onFocusChange` | Never lose work switching windows |
| `files.trimTrailingWhitespace` | `true` | Clean diffs |
| `explorer.confirmDelete` | `false` | Speeds up file management (use with care) |
| `workbench.startupEditor` | `none` | Skip the welcome tab every launch |
| `terminal.integrated.fontSize` | `13` | Match terminal readability to editor |
| `breadcrumbs.enabled` | `true` | Easier file/symbol navigation |

Full ready-to-paste config is in [Section 11](#11-full-sample-settingsjson).

---

## 4. Must-Have Extensions (Everyone)

Install these regardless of your domain. Use `Ctrl/Cmd+Shift+X` to open the Extensions panel.

| Extension | Publisher | Purpose |
|---|---|---|
| **Error Lens** | Alexander | Inline error/warning display — no more hunting the Problems tab |
| **GitLens** | GitKraken | Blame annotations, history, and commit context inline |
| **Prettier – Code Formatter** | Prettier | Opinionated, consistent code formatting |
| **ESLint** | Microsoft | JS/TS linting (pairs with Prettier) |
| **Code Spell Checker** | Street Side Software | Catches typos in code and comments |
| **Path Intellisense** | Christian Kohler | Autocompletes file paths |
| **indent-rainbow** | oderwat | Visually distinguishes indentation levels |
| **Todo Tree** | Gruntfuggly | Surfaces all `TODO`/`FIXME` comments in one panel |
| **Better Comments** | Aaron Bond | Color-codes comment types (`!`, `?`, `TODO`, `*`) |
| **Material Icon Theme** | Philipp Kief | File-type icons for faster visual scanning |
| **One Dark Pro** (or theme of choice) | binaryify | Reduces eye strain, improves contrast |
| **Live Server** | Ritwick Dey | Instant local dev server with auto-reload |
| **DotENV** | mikestead | Syntax highlighting for `.env` files |
| **EditorConfig for VS Code** | EditorConfig | Respects `.editorconfig` across teams/editors |

> **Beginner tip:** Don't install 40 extensions on day one. Start with this list, add domain-specific ones as needed. Extension bloat slows startup and creates conflicts.

---

## 5. Git & GitHub Integration

VS Code has Git built in, but a few steps make it seamless:

1. **Install Git** (if not already): [git-scm.com](https://git-scm.com/)
2. **Configure identity globally**:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```
3. **Install GitHub CLI** (`gh`) — enables PR creation, issue management, and auth directly from the terminal:
   ```bash
   gh auth login
   ```
4. **Extensions**:
   - **GitHub Pull Requests and Issues** — manage PRs without leaving VS Code
   - **GitLens** (already listed above) — supercharges the built-in Git panel
5. **SSH keys for GitHub**: Generate and add an SSH key so you never re-enter credentials:
   ```bash
   ssh-keygen -t ed25519 -C "you@example.com"
   ```
   Add the public key to GitHub under `Settings > SSH and GPG keys`.
6. **GitHub Copilot** (optional, paid): If your workflow benefits from AI pair-programming, install **GitHub Copilot** + **GitHub Copilot Chat**.

---

## 6. Terminal Configuration

### Windows
- Install **Windows Terminal** from the Microsoft Store for a better terminal host.
- Decide your default shell in `settings.json`:
  ```json
  "terminal.integrated.defaultProfile.windows": "PowerShell"
  ```
- Consider **WSL2** (Windows Subsystem for Linux) for a Unix-like dev experience — see Section 9.

### macOS / Linux
- Default shell is usually `zsh` or `bash`. Confirm with:
  ```bash
  echo $SHELL
  ```
- Consider **Oh My Zsh** for prompt themes and plugin management.

### Universal
- Set integrated terminal font to match your editor font for visual consistency.
- Recommended: enable `terminal.integrated.enablePersistentSessions` so terminal state survives reloads.

---

## 7. Keybindings & Productivity

A handful of shortcuts eliminate 80% of mouse usage:

| Action | Windows/Linux | macOS |
|---|---|---|
| Command Palette | `Ctrl+Shift+P` | `Cmd+Shift+P` |
| Quick Open File | `Ctrl+P` | `Cmd+P` |
| Toggle Terminal | `` Ctrl+` `` | `` Cmd+` `` |
| Multi-cursor (add cursor below) | `Ctrl+Alt+Down` | `Cmd+Option+Down` |
| Select next occurrence | `Ctrl+D` | `Cmd+D` |
| Rename symbol | `F2` | `F2` |
| Go to definition | `F12` | `F12` |
| Format document | `Shift+Alt+F` | `Shift+Option+F` |
| Toggle sidebar | `Ctrl+B` | `Cmd+B` |
| Split editor | `Ctrl+\` | `Cmd+\` |
| Go to file symbol | `Ctrl+Shift+O` | `Cmd+Shift+O` |

**Bonus workflow tip:** Use **workspaces** (`.code-workspace` files) for multi-repo or multi-folder projects instead of opening folders individually — it preserves per-project settings, extensions, and layout.

---

## 8. Domain-Specific Setups

Install the baseline (Sections 3–7) first, then layer on your domain.

### 8.1 Web Development (JS/TS/React/Node)

**Extensions:**
- ES7+ React/Redux/React-Native snippets
- Tailwind CSS IntelliSense
- Auto Rename Tag
- Auto Close Tag
- npm Intellisense
- Thunder Client (lightweight REST client, alternative to Postman)

**Settings:**
```json
"emmet.includeLanguages": { "javascript": "javascriptreact" },
"typescript.updateImportsOnFileMove.enabled": "always"
```

**Also install:** Node.js (LTS), `nvm` (Node Version Manager) for switching Node versions per project.

---

### 8.2 Python / Data Science

**Extensions:**
- **Python** (Microsoft) — core language support
- **Pylance** — fast, type-aware IntelliSense
- **Jupyter** — run notebooks directly in VS Code
- **Rainbow CSV** — CSV/TSV column highlighting
- **Data Wrangler** (Microsoft) — visual data cleaning for pandas DataFrames

**Setup:**
```bash
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
```
Select the interpreter: `Ctrl/Cmd+Shift+P` → `Python: Select Interpreter` → choose your `venv`.

**Settings:**
```json
"python.terminal.activateEnvironment": true,
"jupyter.askForKernelRestart": false
```

---

### 8.3 Machine Learning / Deep Learning

Builds on Section 8.2. Add:

**Extensions:**
- **Jupyter Keymap** + **Jupyter Notebook Renderers**
- **Tensorboard** (Microsoft) — view training metrics inline
- **Excel Viewer** — inspect result/metrics CSVs quickly

**Environment:**
- Use `conda` or `venv` per project — never install ML libraries globally.
- GPU setup: verify CUDA/cuDNN versions match your framework (PyTorch/TensorFlow) *before* installing — this is the #1 source of environment breakage.
- Recommended: pin dependencies with `requirements.txt` or `environment.yml` from day one.

**Settings:**
```json
"jupyter.interactiveWindow.textEditor.executeSelection": true
```

---

### 8.4 AI / LLM Engineering

**Extensions:**
- **GitHub Copilot Chat** or **Continue** (open-source AI coding assistant, model-agnostic)
- **REST Client** or **Thunder Client** — for testing LLM API endpoints
- **DotENV** (already listed) — critical for managing API keys safely
- **YAML** (Red Hat) — for config-driven pipelines (LangChain, LlamaIndex configs, etc.)

**Best practices:**
- Never commit `.env` files — add to `.gitignore` immediately.
- Use a `.env.example` file to document required keys without exposing values.
- Consider a **secrets manager** (1Password CLI, `direnv`) over plaintext `.env` for production-adjacent work.

---

### 8.5 Cybersecurity

**Extensions:**
- **Hex Editor** (Microsoft) — inspect binary files
- **REST Client** — test API endpoints and auth flows
- **Docker** — isolate testing environments
- **YAML** — for tool configs (nmap scripts, CI security scans)
- **CodeQL** (GitHub) — static analysis for vulnerability detection

**Setup:**
- Use dedicated **VMs or containers** for any offensive-security work — never test tools against your host environment.
- Install **Windows Subsystem for Linux (WSL2)** or a Kali/Parrot VM for penetration-testing toolchains.
- Consider a separate VS Code profile (`Profiles` feature, built-in since v1.75+) to keep security tooling isolated from your main dev extensions.

---

### 8.6 DevOps / Cloud / Infrastructure

**Extensions:**
- **Docker** (Microsoft) — Dockerfile/compose syntax + container management
- **Kubernetes** (Microsoft) — cluster management from the sidebar
- **HashiCorp Terraform** — IaC syntax highlighting and validation
- **YAML** (Red Hat)
- **Remote - Containers** (see Section 9)
- **AWS Toolkit** / **Azure Tools** / **Google Cloud Code** — pick based on your cloud provider

**Settings:**
```json
"yaml.format.enable": true,
"docker.showStartPage": false
```

---

### 8.7 Mobile Development

**Flutter/Dart:**
- **Flutter** + **Dart** extensions (official)
- Run `flutter doctor` after install to verify toolchain

**React Native:**
- **React Native Tools** (Microsoft)
- Ensure Android Studio (Android SDK) and/or Xcode (iOS, macOS only) are installed separately — VS Code handles code, not the native build toolchains.

---

### 8.8 C / C++

**Extensions:**
- **C/C++** (Microsoft) — IntelliSense, debugging
- **C/C++ Extension Pack**
- **CMake Tools** — for CMake-based projects
- **Clang-Format** — enforce consistent style

**Setup:**
- Windows: install **MSYS2** or **MinGW-w64**, or use WSL with `gcc`/`g++`.
- macOS: `xcode-select --install` for Clang.
- Linux: `gcc`/`g++` typically pre-available; confirm with `gcc --version`.

---

### 8.9 Java

**Extensions:**
- **Extension Pack for Java** (Microsoft) — bundles debugger, test runner, Maven/Gradle support, and IntelliSense
- **Spring Boot Extension Pack** (if working with Spring)

**Setup:**
- Install a JDK (17 or 21 LTS recommended) and confirm `JAVA_HOME` is set correctly.
- VS Code auto-detects installed JDKs — verify via `Java: Configure Java Runtime` in the Command Palette.

---

## 9. Remote Development (SSH, WSL, Containers)

Install the **Remote Development extension pack** (Microsoft) — bundles three extensions:

- **Remote - SSH**: Edit code on a remote server as if it were local.
- **Remote - WSL**: Full Linux dev environment on Windows without leaving VS Code.
- **Dev Containers**: Develop inside a Docker container defined by a `.devcontainer/devcontainer.json` — guarantees identical environments across teammates and machines.

This is the single highest-leverage setup for teams: a `devcontainer.json` in your repo means any new machine is "fully configured" the moment someone opens the folder in VS Code.

---

## 10. Settings Sync (Move Between Machines in Minutes)

Built into VS Code — no extension required.

1. `Ctrl/Cmd+Shift+P` → `Settings Sync: Turn On`
2. Sign in with GitHub or Microsoft account.
3. Choose what to sync: Settings, Keybindings, Extensions, UI State, Snippets, Profiles.

On a new machine: sign in, turn on Settings Sync, and your entire setup — extensions included — restores automatically. This is why signing in early (Section 2.2) matters.

---

## 11. Full Sample `settings.json`

Paste this as a starting baseline, then adjust to taste:

```json
{
  "editor.fontSize": 14,
  "editor.fontFamily": "'JetBrains Mono', Consolas, 'Courier New', monospace",
  "editor.fontLigatures": true,
  "editor.formatOnSave": true,
  "editor.tabSize": 2,
  "editor.cursorBlinking": "smooth",
  "editor.minimap.enabled": false,
  "editor.linkedEditing": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.guides.bracketPairs": true,

  "files.autoSave": "onFocusChange",
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,

  "workbench.startupEditor": "none",
  "workbench.iconTheme": "material-icon-theme",
  "workbench.colorTheme": "One Dark Pro",

  "terminal.integrated.fontSize": 13,
  "terminal.integrated.enablePersistentSessions": true,

  "explorer.confirmDelete": false,
  "explorer.compactFolders": false,

  "breadcrumbs.enabled": true,

  "git.autofetch": true,
  "git.confirmSync": false,

  "[javascript]": { "editor.defaultFormatter": "esbenp.prettier-vscode" },
  "[typescript]": { "editor.defaultFormatter": "esbenp.prettier-vscode" },
  "[python]": { "editor.defaultFormatter": "ms-python.python" }
}
```

---

## 12. Bonus: Power-User Tricks

- **Custom snippets**: `Ctrl/Cmd+Shift+P` → `Configure User Snippets` — write your own boilerplate shortcuts (e.g., type `rfc` → expands to a full React functional component).
- **Zen Mode**: `Ctrl/Cmd+K Z` — distraction-free full-screen editing.
- **Multi-root workspaces**: Combine multiple repos in one window when working across a frontend + backend + shared-lib setup.
- **Vim keybindings**: Install the **Vim** extension if you want modal editing without leaving VS Code.
- **Profiles** (built-in): Create separate extension/settings profiles for different contexts (e.g., "Web Dev" vs "Security Testing") so tools don't collide.
- **Task Runner**: Define repeatable build/test/lint commands in `.vscode/tasks.json` so teammates run the same commands you do.
- **Emmet abbreviations**: Type `div.container>ul>li*5` + `Tab` in an HTML file — watch it expand into full markup.
- **Peek Definition** (`Alt+F12` / `Option+F12`): View a function's definition inline without switching files.

---

## 13. Post-Setup Checklist

- [ ] Signed in to Settings Sync
- [ ] Core settings.json applied
- [ ] Baseline extensions installed (Section 4)
- [ ] Git identity configured + SSH key added to GitHub
- [ ] Terminal/shell configured
- [ ] Domain-specific extensions installed
- [ ] `.gitignore` includes `.env`, `venv/`, `node_modules/`, `__pycache__/` as relevant
- [ ] Remote Development pack installed (if working across machines/containers)
- [ ] Verified interpreter/JDK/runtime is correctly selected per project
- [ ] Confirmed `formatOnSave` + linter are actually running (test with a deliberately messy file)

---

*Maintained as a living document — update as tooling evolves. Contributions and domain additions welcome via PR.*
