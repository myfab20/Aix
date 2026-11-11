# AIX — All-in-One Package

The #1 all-in-one design tool. Open source. Fully customizable. Agent-ready.

## Contents

```
aix-all-in-one/
├── aix-mcp-server/          # MCP server + CLI + design system
│   ├── bin/aix.js           # CLI entry point
│   ├── src/                 # TypeScript source
│   │   ├── index.ts         # MCP server entry
│   │   ├── registry/        # 21 components, tokens, patterns, themes
│   │   ├── tools/           # 9 MCP tools
│   │   └── resources/       # 6 MCP resources
│   ├── package.json         # @cloud-nine-ai/aix
│   └── README.md
├── website/                 # Landing page (index.html)
│   └── index.html           # Petalyx-themed AIX landing page
├── aix-comprehensive-bio.md # Full bio + usage guide
├── cloud-nine-ai-master-lineup.md  # 10 projects lineup
└── cloud-nine-ai-launch-kit.md     # Launch announcement pack
```

## Quick Start

```bash
# Install
npm i @cloud-nine-ai/aix

# List components
npx @cloud-nine-ai/aix list

# Start MCP server (for AI agents)
npx @cloud-nine-ai/aix mcp

# Connect to Claude Desktop
# Add to claude_desktop_config.json:
# { "mcpServers": { "aix": { "command": "npx", "args": ["@cloud-nine-ai/aix", "mcp"] } } }
```

## Links
- **npm:** https://www.npmjs.com/package/@cloud-nine-ai/aix
- **GitHub:** https://github.com/myfab20/Aix
- **Website:** cloud.cloud-nine-ai.workers.dev
- **Landing page:** open website/index.html in browser

## License
MIT — Free forever. ☁️
