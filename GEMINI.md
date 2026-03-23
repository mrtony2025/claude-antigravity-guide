# GEMINI.md

This file provides instructional context for Gemini CLI when working with this repository.

## Project Overview

This is a **Non-Code Project** consisting of interactive setup guides for using **Claude Code** (Anthropic's CLI) and **Antigravity IDE** (Google's agent-first IDE) on macOS. The content is primarily written in Vietnamese to support the local developer community.

The project is built as a set of self-contained static HTML files with no external dependencies, build tools, or bundlers.

## Key Files

- `index.html`: The main, high-fidelity interactive landing page. Features a modern dark UI with animations, progress tracking, and collapsible steps.
- `claude_code_antigravity_macos_guide.html`: A compact version of the setup guide, specifically designed to be rendered within an AI assistant's artifact viewer (like Claude Code's renderer). It uses CSS variables provided by the host environment.
- `CLAUDE.md`: Contains specific guidance for Claude Code, detailing the architecture and editing notes for the guides.

## Technologies

- **Frontend**: Vanilla HTML5, Vanilla CSS3 (with CSS Custom Properties), Vanilla JavaScript.
- **Fonts**: Inter and JetBrains Mono (loaded via Google Fonts).
- **Target Platform**: macOS (specifically Apple Silicon M1/M2/M3).

## Usage & Development

### Viewing the Guides
Simply open `index.html` in any modern web browser to view the full interactive guide.

### Editing Guidelines
- **Language**: All user-facing content should be maintained in Vietnamese.
- **Styling**: 
    - In `index.html`, use the defined `:root` CSS variables for consistency.
    - In `claude_code_antigravity_macos_guide.html`, avoid hardcoding colors; rely on environment-injected variables like `--color-background-info` or `--color-text-primary`.
- **Interactive State**: The guides use simple JavaScript objects (e.g., `stepChecks`) to track progress. Ensure these remain in sync with any added or removed checkbox IDs (`cb1a`, `cb1b`, etc.).

## Setup Workflow Covered in Guides
1. **Antigravity IDE**: Installation via Homebrew or DMG.
2. **Claude Code CLI**: Installation via `curl` and PATH configuration.
3. **Anthropic Auth**: Getting API keys or Pro/Max accounts.
4. **Extension**: Installing the Claude Code extension in Antigravity.
5. **Project Init**: Running `claude` and `/init` in a local repository.
6. **Slash Commands**: Training on commands like `/compact`, `/model`, and `/mcp`.
