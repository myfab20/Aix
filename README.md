# ☁️ AIX — All-in-One Design System Package

### One package. One design system. AI-agent ready.

**AIX ** is an open-source, customizable design system and MCP server built to help developers and AI agents work with consistent UI components, design tokens, themes, and reusable patterns.

Designed for modern development workflows, AIX brings design resources and AI-agent integration together in one package.

---

## ✨ What's Included?

AIX combines multiple development tools into one organized package.

| Package | Description |
|---|---|
| **MCP Server** | Connect compatible AI agents to AIX resources and tools. |
| **CLI** | Manage and explore AIX directly from your terminal. |
| **Component Registry** | 21 reusable UI components. |
| **Design Tokens** | Centralized design values and styling foundations. |
| **Patterns** | Reusable interface patterns. |
| **Themes** | Customizable visual themes. |
| **MCP Tools** | 9 tools for agent interaction. |
| **MCP Resources** | 6 resources for accessing design-system information. |

---

## 📦 Project Structure

```text
aix-all-in-one/
│
├── aix-mcp-server/
│   ├── bin/
│   │   └── aix.js
│   │
│   ├── src/
│   │   ├── index.ts
│   │   ├── registry/
│   │   ├── tools/
│   │   └── resources/
│   │
│   ├── package.json
│   └── README.md
│
├── website/
│   └── index.html
│
├── aix-comprehensive-bio.md
├── cloud-nine-ai-master-lineup.md
└── cloud-nine-ai-launch-kit.md
```

### Inside the package

- `bin/aix.js` — CLI entry point.
- `src/index.ts` — MCP server entry point.
- `src/registry/` — Components, tokens, patterns, and themes.
- `src/tools/` — MCP tool implementations.
- `src/resources/` — MCP resource definitions.
- `website/` — AIX landing page.

---

## 🚀 Quick Start

### 1. Install AIX

Make sure Node.js and npm are installed.

```bash
npm install @cloud-nine-ai/aix
```

### 2. Explore available components

```bash
npx @cloud-nine-ai/aix list
```

### 3. Start the MCP server

```bash
npx @cloud-nine-ai/aix mcp
```

That's it! You're ready to configure AIX with a compatible MCP client.

---

## 🤖 Connect AIX to Claude Desktop

Add the following configuration to your Claude Desktop MCP configuration file:

```json
{
  "mcpServers": {
    "aix": {
      "command": "npx",
      "args": [
        "-y",
        "@cloud-nine-ai/aix",
        "mcp"
      ]
    }
  }
}
```

Restart Claude Desktop after saving the configuration.

**Note:** Other MCP-compatible clients may also support AIX, depending on their MCP configuration capabilities.

---

## 🛠️ Built for Customization

AIX is designed to provide a flexible foundation for developers.

- Explore reusable UI components.
- Work with centralized design tokens.
- Access reusable design patterns.
- Customize themes and styling.
- Integrate design-system resources into AI workflows.
- Connect compatible AI agents through MCP.

---

## 🌐 Official Links

| Resource | Link |
|---|---|
| **NPM Package** | https://www.npmjs.com/package/@cloud-nine-ai/aix |
| **GitHub Repository** | https://github.com/myfab20/Aix |
| **Official Website** | cloud.cloud-deo.workers.dev| 
| **Landing Page** | aix.cloud-deo.workers.dev|

---

## 📜 License

AIX is released under the **MIT License**.

Free to use, modify, and customize under the terms of the license.

---

## ⚠️ Important Notice

AIX is a newly released project. Some features may contain bugs, unexpected errors, or incomplete functionality. Compatibility may vary between MCP clients and development environments.

If you encounter an issue, please report it through the GitHub repository so it can be investigated and addressed.

---

## ☁️ Built by Cloud Nine AI

We're building tools that make AI development more accessible, flexible, and powerful.

**AIX — Give your AI agents a design system they can understand.**

*Open source. Customizable. Agent-ready.*
