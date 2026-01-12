# Using Design to Code with Codex CLI

This folder contains files for using the Design to Code agent with the [Codex CLI](https://developers.openai.com/codex/cli).

## Setup

### Step 1: Install AGENTS.md

Copy the `AGENTS.md` file to your project root (where you'll run Codex):

```bash
cp codex/AGENTS.md /path/to/your/project/
```

> **Note:** `AGENTS.md` must be in the project root directory where you run the Codex CLI.

### Step 2: Install the Custom Prompt

Copy `sketch.md` to your Codex prompts directory:

```bash
mkdir -p ~/.codex/prompts
cp codex/sketch.md ~/.codex/prompts/
```

## Usage

1. **Open Sketch** and select a frame or component
2. **Navigate to your project directory** (where `AGENTS.md` is located)
3. **Run Codex CLI** and use the custom prompt:

```bash
codex
> /prompts:sketch
```

## What's Included

- **AGENTS.md** - Custom agent instructions for Codex CLI
- **sketch.md** - Reusable prompt for design-to-code conversion

## Files

| File | Purpose | Location |
|------|---------|----------|
| `AGENTS.md` | Agent configuration | Project root (copy here) |
| `sketch.md` | Custom prompt | `~/.codex/prompts/` |

## Example Workflow

1. **Copy AGENTS.md to your project:**
   ```bash
   cp codex/AGENTS.md /path/to/your/project/
   ```

2. **Install the custom prompt:**
   ```bash
   cp codex/sketch.md ~/.codex/prompts/
   ```

3. **Select a frame in Sketch**

4. **Run Codex and use the custom prompt:**
   ```bash
   codex
   ```
   Then type:
   ```
   /prompts:sketch
   ```

The agent will:
- 🔍 Extract design data from your selected Sketch frame
- 🏗️ Generate semantic HTML structure  
- 🎨 Generate CSS using BEM methodology
- 📦 Output files ready for iteration

## Troubleshooting

**Agent not loading?**
- Ensure `AGENTS.md` is in the project root where you run `codex`
- Check that the file is named exactly `AGENTS.md` (case-sensitive)

**Custom prompt not found?**
- Verify `sketch.md` is in `~/.codex/prompts/`
- Restart Codex CLI to reload prompts

**MCP connection issues?**
- Ensure Sketch is open with an active document
- Verify MCP Server is enabled in Sketch Settings

## Resources

- [Codex CLI Documentation](https://developers.openai.com/codex/cli)
- [Custom Instructions with AGENTS.md](https://developers.openai.com/codex/guides/agents-md)
- [Custom Prompts](https://developers.openai.com/codex/custom-prompts)
- [Sketch MCP Server](https://www.sketch.com/docs/mcp-server/)