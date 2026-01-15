# ✨ Design to Code: Sketch → HTML/CSS

> Transform your Sketch designs into HTML and CSS with the Sketch MCP server and AI coding assistants.

### It works like this

1. Designer selects a frame in Sketch.
2. Coding assistant calls the Sketch API through the MCP (Model Context Protocol) server.
3. Our agent extracts real design data — colors, typography, layout, effects, everything.
4. CSS is generated using BEM methodology — a structured, maintainable approach to class naming.
5. Output: As close to the original design as possible, with zero guessing.

---

## Features

### Design Fidelity First
- Extracts **real design values** from Sketch (colors, spacing, typography, shadows)
- Builds HTML and CSS from real Sketch data, without visual guessing.
- Respects your design system and component hierarchy

### Modern Tooling
- **MCP (Model Context Protocol)** integration with Sketch
- Works with popular AI coding assistants (Claude Desktop, VS Code, Cursor, Codex)
- Seamless workflow within your design and development environment

### What You Get
- Clean, semantic HTML structure
- CSS generated from real Sketch values
- Support for complex layouts, rounded corners, shadows, and more
- Icon integration (Phosphor Icons or custom)

---

## Getting Started

### Prerequisites

Before you begin, make sure you have:
- ✅ [Sketch](https://www.sketch.com/) (version 2025.2.4 or later)
- ✅ An AI coding assistant (Claude Desktop, VS Code with GitHub Copilot, Cursor, or Codex)
- ✅ This repository cloned locally

---

## Setup Instructions

### Step 1️⃣: Enable the MCP Server in Sketch

The Sketch MCP server allows AI assistants to communicate directly with your Sketch documents.

1. **Open Sketch** and go to **Settings > General > MCP Server**
2. Click the checkbox: **MCP Server:**
3. The server will start automatically when Sketch is running

![alt text](images/mcp-server-sketch-settings.png)

> 💡 **Note:** The MCP server only works while Sketch is open and a document is active.

---

### Step 2️⃣: Connect Your AI Client

Connect your preferred AI coding assistant to the Sketch MCP server. Each client has specific configuration requirements.

**Official Documentation:**  

[Sketch MCP Server - How to Connect Your AI Client](https://www.sketch.com/docs/mcp-server/#how-to-connect-your-ai-client)

The documentation includes step-by-step instructions for:
- 🤖 **Claude Desktop** - Add server to Claude's configuration file
- 💻 **VS Code** - Configure GitHub Copilot settings
- 🎯 **Cursor** - Add to MCP settings
- 📝 **Codex CLI** - Configure MCP connections

---

### Step 3️⃣: Add the Custom Agent

The custom agent provides specialized prompts and instructions optimized for design-to-code workflows.

#### Official Agent Documentation

- **VS Code (GitHub Copilot)**
  - [Custom Agents](https://code.visualstudio.com/docs/copilot/customization/custom-agents)
- **Cursor**
  - [Custom Rules](https://cursor.com/docs/context/rules)
- **Claude Desktop**
  - [Custom Subagents](https://code.claude.com/docs/en/sub-agents#quickstart:-create-your-first-subagent)
- **Codex**
  - [Custom instructions with AGENTS.md](https://developers.openai.com/codex/guides/agents-md)
  - [Custom Prompts](https://developers.openai.com/codex/custom-prompts)

---

## Usage

### Recommended Workflow 🎯

For best results, follow this two-step workflow:

#### Step 1: Analyze and Improve Layer Names

Start with the **Sketch Layer Names** prompt: [.github/prompts/Sketch Layer Names.prompt.md](.github/prompts/Sketch%20Layer%20Names.prompt.md) 
- Analyzes all layer names in your selected frame
- Checks for semantic quality and HTML/CSS compatibility
- Evaluates against BEM methodology best practices
- Automatically renames layers for better code generation

This step ensures layer names translate seamlessly into semantic HTML elements and maintainable CSS class names, which significantly improves the accuracy of the generated code.

#### Step 2: Generate Code

After layer names are optimized, choose the appropriate prompt:

**For simple components or symbols:**
- Use **Design to Code** prompt [.github/prompts/Design to Code.prompt.md](.github/prompts/design%20to%20code.prompt.md)
- Best for: buttons, icons, single UI elements, simple layouts

**For complex or full-page designs:**
- Use **Responsive Design to Code** prompt [.github/prompts/Responsive Design to Code.prompt.md](.github/prompts/Responsive%20Design%20to%20Code.prompt.md)
- Best for: cards, forms, navigation, dashboard layouts, full pages
- Automatically generates responsive CSS with proper breakpoints

---

#### Use the prompt files ⚡️

This repo includes reusable prompt files in:

[.github/prompts](.github/prompts)

In the VS Code Copilot chat window just type `/` to bring up the prompt menu, then select the prompt you want to use.

That's it! The AI will:
1. 🔍 Extract design data from your selected Sketch frame
2. 🏗️ Generate semantic HTML structure
3. 🎨 Generate CSS based on the extracted values, then you can refine where needed
4. 📦 Output HTML/CSS files you can iterate on and improve

### Example Workflow

1. **Design in Sketch:** Create or select your UI component
2. **Select the frame** you want to convert
3. **Open your AI assistant** (VS Code Copilot, Claude Desktop, etc.)
4. **Run the Sketch Layer Names prompt:** Analyze and optimize layer names for better semantic quality
5. **Run the appropriate code generation prompt:**
   - For simple components: Use [.github/prompts/Design to Code.prompt.md](.github/prompts/Design%20to%20Code.prompt.md)
   - For complex layouts: Use [.github/prompts/Responsive Design to Code.prompt.md](.github/prompts/Responsive%20Design%20to%20Code.prompt.md)
6. **Review and refine:** The AI generates your HTML/CSS, which you can iterate on

---

## Project Structure

```
design-to-code-sketch/
├── .github/
│   └── agents/
│       └── Design to Code.agent.md     # Custom agent instructions
│   └── prompts/                        # Example prompts
├── images/                             # Image assets
├── *.html                              # Generated HTML files
├── *.css                               # Generated CSS files
└── README.md                           # This file
```

---

## Examples

Check out the included example files (`*.html`, `*.css`) in this repository to see the workflow in action. Each example demonstrates how Sketch designs are transformed into semantic HTML and CSS using this workflow.

See the original design exports from Sketch in the [images/designs](images/designs) folder.

See the Sketch document [design-to-code.sketch](design-to-code.sketch) I used for this project.

---

## Tips for Best Results

### In Sketch:
- ✅ Use **named layers** for better semantic HTML
- ✅ Organize with **Groups and Frames** for clear structure
- ✅ Apply **consistent naming** (button-primary, card-header, etc.)
- ✅ Use **Symbols/Components** for reusable elements

### With the AI:
- 💬 Be specific about what you want (e.g., "use Phosphor icons" or "add hover states")
- 🔄 Iterate on the results - ask for refinements
- 📦 Request specific features like "make it responsive" or "add animations"

### Version Control
- 🔄 Use Git or another version control system to track changes
- 📝 Commit often with clear messages
- 🔀 Use branches for new features or experiments
- 📂 Keep your design and code files organized

---

## 🛠️ Troubleshooting

### MCP Server Not Working
- ✅ Ensure Sketch is **open** and a document is **active**
- ✅ Check that MCP Server is **enabled** in Sketch settings
- ✅ Restart both Sketch and your AI client

### AI Can't See My Selection
- ✅ Make sure a frame or layer is **selected** in Sketch
- ✅ Try selecting a top-level frame rather than nested layers
- ✅ Verify the MCP connection is established

### Generated Code Doesn't Match Design
- 🔍 Check that you selected the correct frame
- 📏 Ensure your design uses consistent values
- 💬 Provide more specific instructions to the AI

---

## 📝 Notes

- For testing I used VS Code with Copilot and selected Claude Sonnet 4.5 for the model.
- Fonts used in the examples:
  - Space Grotesk (https://fonts.google.com/specimen/Space+Grotesk)
  - Inter (https://fonts.google.com/specimen/Inter)
  - Poppins (https://fonts.google.com/specimen/Poppins)
  - SF Pro (https://developer.apple.com/fonts/)

---

## 🧪 Testing with other AI clients

This project has mainly been tested with **VS Code + GitHub Copilot** and the **Codex CLI**.

If you use **Cursor** or **Claude Desktop**, I’d really appreciate you giving it a quick try and sharing any feedback — especially around setup, rough edges, or anything unclear in the instructions. Even “it worked as expected” is a useful signal.

If something doesn’t work, feel free to open an issue rather than trying to fix it yourself.

---

## 🤝 Contributing

Found a bug or have a suggestion? Feel free to:
- 🐛 Open an issue
- 🔀 Submit a pull request
- 💡 Share your improvements to the custom agent

---

## 📚 Resources

- [Key Technical Decisions](key-technical-decisions.md)
- [Sketch MCP Server Documentation](https://www.sketch.com/docs/mcp-server/)
- [Sketch Developer API](https://developer.sketch.com/reference/api)
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io/)
- [Phosphor Icons](https://phosphoricons.com/)
- [BEM Methodology](http://getbem.com/)