# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This project is a single self-contained HTML file (`claude_code_antigravity_macos_guide.html`) — an interactive step-by-step setup guide for using Claude Code with the Antigravity IDE on macOS (M1/Apple Silicon).

## Architecture

The entire app lives in one HTML file with no external dependencies, build tools, or bundlers:

- **Styles**: Inline `<style>` block using CSS custom properties (`var(--color-*)`, `var(--font-mono)`, etc.) that are expected to be injected by the host environment (Claude Code's artifact renderer).
- **Markup**: A `.guide` div containing a progress bar, and a list of collapsible `.step` cards (Steps 1–6).
- **Behavior**: Inline `<script>` handles accordion toggling, checkbox state tracking, progress bar updates, and clipboard copy. No frameworks.

## Content

The guide covers: installing Antigravity IDE, installing Claude Code CLI, getting an Anthropic API key, installing the Claude Code extension in Antigravity, initializing a first project, and common slash commands. Content is written in Vietnamese.

## Editing Notes

- CSS variables like `--color-background-info`, `--color-text-success`, etc. are not defined in this file — they rely on the host environment's theme. Do not add fallback values unless targeting standalone browser use.
- Step IDs follow the pattern `s1`–`s6`; checkbox IDs follow `cb1a`, `cb1b`, `cb2a`, etc. The `stepChecks` object in the script must stay in sync with any added/removed checkboxes.
