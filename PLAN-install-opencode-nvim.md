# Plan: Install nickjvandyke/opencode.nvim

## Prerequisites
- Install `opencode` CLI tool (via npm or homebrew):
  ```bash
  npm install -g opencode
  # OR
  brew install opencode
  ```
- Run `opencode login` to configure your AI provider (Anthropic, OpenAI, etc.)

## Changes to make

### 1. Edit `lua/custom/plugins/init.lua`
Add the opencode.nvim plugin with lazy.nvim configuration:
- Plugin: `nickjvandyke/opencode.nvim`
- Version: `*` (latest stable release)
- Config: set `vim.g.opencode_opts`, `vim.o.autoread = true`, and recommended keymaps
- Keymaps to add:
  - `<leader>oa` (n, x) — Ask OpenCode
  - `<leader>os` (n, x) — Select OpenCode action
  - `go` (n, x) — Operator to append range to OpenCode
  - `goo` (n) — Operator to append line to OpenCode
  - `<S-C-u>` (n) — Scroll OpenCode up
  - `<S-C-d>` (n) — Scroll OpenCode down

### 2. (Optional) Verify snacks.nvim
The plugin works without snacks.nvim, but snacks provides enhanced input/picker integration. Your config doesn't currently include snacks.nvim — if you want the enhanced experience, we can add it later.

## Verification
- Run `:Lazy` to confirm the plugin installed
- Run `:checkhealth opencode` to verify setup
- Open a file and test `<leader>oa` to ask OpenCode a question
