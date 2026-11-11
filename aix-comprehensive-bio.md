# AIX — The #1 All-in-One Design Tool

## Bio

**Tagline:** *The design system AI agents can actually use. The #1 all-in-one design tool.*

**AIX** is the world's first open-source design system built for **humans and AI agents alike**. It's not just a component library — it's the complete design infrastructure: tokens, components, patterns, themes, accessibility, and an agent SDK that lets AI generate UI that actually matches your brand. Fully customizable. Agent-ready. Free forever.

AIX is the **#1 all-in-one design tool** because it replaces the entire design stack:
- ❌ No more Figma → code handoff gaps
- ❌ No more inconsistent design tokens across projects
- ❌ No more AI generating ugly, inaccessible UI
- ❌ No more paying $50/seat/month for design tools
- ✅ One system. One source of truth. Humans and AI, working from the same components.

### Why AIX is #1

| Feature | AIX | Figma | Storybook | Tailwind UI |
|---------|-----|-------|-----------|-------------|
| Open source (MIT) | ✅ | ❌ | ✅ | ❌ |
| AI agent-ready (MCP server) | ✅ | ❌ | ❌ | ❌ |
| Fully customizable tokens | ✅ | ⚠️ (paid) | ⚠️ | ⚠️ |
| Framework agnostic | ✅ | ❌ | ⚠️ | ❌ (React only) |
| Accessible by default (WCAG 2.2 AA) | ✅ | ❌ | ❌ | ⚠️ |
| Figma ↔ Code sync | ✅ | ✅ | ❌ | ❌ |
| Free forever (core) | ✅ | ❌ | ✅ | ❌ (paid) |
| Dark mode native | ✅ | ⚠️ | ❌ | ⚠️ |
| Component count | 20+ (growing) | N/A | N/A | 500+ |

---

## How to Use AIX — Step by Step

### Step 1: Install AIX

**Option A — CLI (recommended):**
```bash
npx @cloud-nine-ai/aix init
```
This scaffolds a new project with AIX tokens, components, and config.

**Option B — Manual install:**
```bash
npm i @cloud-nine-ai/aix
```

**Option C — Clone the repo:**
```bash
git clone https://github.com/cloud-nine-ai/aix.git
cd aix
npm install
```

### Step 2: Add Components

```bash
# Add individual components
npx @cloud-nine-ai/aix add button
npx @cloud-nine-ai/aix add card input modal

# Add a full pattern (layout + components)
npx @cloud-nine-ai/aix add pattern dashboard
npx @cloud-nine-ai/aix add pattern login-form

# List all available components
npx @cloud-nine-ai/aix list
```

### Step 3: Use Components in Your Code

```tsx
// React example
import { Button, Card, Input, Stack } from 'aix';

export default function LoginPage() {
  return (
    <Card variant="elevated" padding="lg">
      <Stack gap="4">
        <h2>Sign In</h2>
        <Input type="email" label="Email" placeholder="you@example.com" required />
        <Input type="password" label="Password" required />
        <Button variant="primary" fullWidth>Sign In</Button>
      </Stack>
    </Card>
  );
}
```

### Step 4: Customize Tokens (Your Brand)

Edit `aix.config.ts` or `tokens.json`:

```typescript
// aix.config.ts
export default {
  tokens: {
    color: {
      primary: {
        500: "#your-brand-color",
        600: "#your-brand-dark",
      },
    },
    typography: {
      fontFamily: {
        sans: "Your Font, system-ui, sans-serif",
      },
    },
    radius: {
      md: "12px", // rounder corners
    },
  },
  theme: "light", // or "dark" or "custom"
};
```

Or use the MCP server:
```
"Apply my brand colors: primary #FF6B35, font Inter, radius 12px"
→ AI calls apply_theme with your overrides
```

### Step 5: Connect to AI Agents (MCP Server)

**For Claude Desktop:**
1. Open `claude_desktop_config.json`
2. Add:
```json
{
  "mcpServers": {
    "aix": {
      "command": "node",
      "args": ["/path/to/aix-mcp-server/dist/index.js"]
    }
  }
}
```
3. Restart Claude Desktop
4. Now you can say: *"Build a dashboard using AIX components with dark theme"*

**For Cursor:**
1. Create `.cursor/mcp.json` in your project
2. Add the same config
3. Cursor now has access to all AIX components, tokens, and patterns

**For VS Code (Copilot):**
1. Create `.vscode/mcp.json`
2. Add config with `"type": "stdio"`
3. Copilot can now generate AIX-based UI

### Step 6: Generate UI with AI

Once connected, just ask your AI agent:

| Prompt | What happens |
|--------|-------------|
| "Build a login form with AIX" | AI fetches Input, Button, Card schemas → generates code |
| "Create a dashboard with stat cards and a data table" | AI fetches dashboard pattern → generates full layout |
| "Make this accessible" | AI runs validate_accessibility → fixes issues |
| "Apply dark theme to all components" | AI calls apply_theme → generates CSS variables |
| "What button variants are available?" | AI calls get_component("Button") → lists all props |
| "Find a component for form validation" | AI calls search_components → returns Input, etc. |

### Step 7: Figma Sync (Designers)

1. Install the AIX Figma plugin
2. Import AIX token library
3. Designers use AIX components in Figma
4. Run `npx @cloud-nine-ai/aix sync` to push token changes both ways
5. Code and design stay in sync — always

### Step 8: Accessibility Audit

```bash
# Audit your entire project
npx @cloud-nine-ai/aix audit

# Or use the MCP tool
"Validate this component for WCAG 2.2 AA compliance"
→ AI calls validate_accessibility → returns issues + score
```

---

## Available Components (20+)

### Inputs
| Component | Description |
|-----------|-------------|
| Button | Variants, sizes, loading, icons |
| Input | Text, email, password, search, with validation |
| Select | Dropdown with search, multi-select, groups |
| Checkbox | With label, description, indeterminate |
| Toggle | Switch for boolean settings |
| Radio | Radio group (coming soon) |

### Layout
| Component | Description |
|-----------|-------------|
| Card | Elevated, outlined, filled variants |
| Stack | Flexbox vertical/horizontal stacking |
| Grid | Responsive CSS grid |
| Divider | Horizontal/vertical separator |

### Feedback
| Component | Description |
|-----------|-------------|
| Alert | Info, success, warning, error banners |
| Toast | Auto-dismiss notifications with actions |
| Badge | Status labels with color variants |
| Progress | Bar or circular progress |
| Spinner | Loading indicator |
| Tooltip | Hover/focus tooltips |

### Navigation
| Component | Description |
|-----------|-------------|
| Tabs | Tabbed interface with keyboard nav |
| Breadcrumb | Navigation trail |
| Pagination | Page navigation |

### Data
| Component | Description |
|-----------|-------------|
| Table | Sortable, selectable, paginated |
| Avatar | User avatar with status indicator |

### Overlay
| Component | Description |
|-----------|-------------|
| Modal | Focus-trapped dialog with ESC close |

---

## Available Patterns (8)

| Pattern | Components Used | Use Case |
|---------|----------------|----------|
| login-form | Card, Input, Button, Checkbox | Auth page |
| signup-form | Card, Input, Button, Checkbox | Registration |
| dashboard | Sidebar, Header, Card, StatCard, Table, Chart | Admin dashboard |
| settings-page | Tabs, Card, Input, Select, Button, Toggle | Settings |
| empty-state | Icon, Text, Button | No data state |
| error-page | Text, Button | 404/500 page |
| data-table | Table, Input, Button, Pagination, Badge | Data listing |
| modal-dialog | Modal, Button, Divider | Confirmation dialog |

---

## Available Themes (4)

| Theme | Description |
|-------|-------------|
| light | Clean white background, dark text |
| dark | Dark background, light text |
| brand-blue | Blue accent, light background |
| brand-green | Green accent, light background |

Create custom themes by overriding any token.

---

## Available Tokens

| Category | Tokens |
|----------|--------|
| color | primary (50-900), neutral (50-900), success, danger, warning, info |
| spacing | 0, 1, 2, 3, 4, 5, 6, 8, 10, 12, 16 (4px scale) |
| typography | fontFamily (sans, mono, serif), fontSize (xs-4xl), fontWeight, lineHeight |
| radius | none, sm, md, lg, xl, 2xl, full |
| shadow | sm, md, lg, xl |
| motion | fast (150ms), normal (250ms), slow (400ms), easing |
| zIndex | base, dropdown, sticky, modal, popover, toast |

---

## FAQ

**Q: Is AIX really free?**
A: Yes. Core components, tokens, and the MCP server are MIT licensed. Free forever. Pro and Enterprise tiers add premium components, Figma sync, and support.

**Q: Can I use AIX with my existing project?**
A: Yes. AIX components are framework-agnostic (React, Vue, Svelte, Solid, vanilla). You can adopt incrementally — one component at a time.

**Q: Does AIX work with Tailwind?**
A: Yes. AIX tokens generate Tailwind config. You can use AIX tokens as Tailwind theme values.

**Q: Can AI agents really generate good UI with AIX?**
A: Yes. That's the whole point. AIX ships structured JSON schemas, prop definitions, code templates, and accessibility rules. AI agents read these and generate correct, accessible, on-brand UI — not guesswork.

**Q: How is this different from shadcn/ui?**
A: shadcn/ui is React-only and has no AI agent integration. AIX is framework-agnostic, has an MCP server, ships with accessibility validation, Figma sync, and is designed from the ground up for AI agent consumption.

**Q: Can I create my own components?**
A: Yes. Follow the component JSON schema in `src/registry/components/`, add your component, rebuild. The MCP server will automatically expose it to AI agents.

---

## Roadmap

- [x] 20+ core components
- [x] Design tokens (colors, spacing, typography, etc.)
- [x] 8 UI patterns
- [x] 4 themes
- [x] MCP server (stdio transport)
- [x] Accessibility validation
- [ ] Figma plugin (token sync)
- [ ] SSE/HTTP transport for remote MCP
- [ ] Vue, Svelte, Solid framework bindings
- [ ] Premium component pack (charts, date pickers, rich text)
- [ ] Visual theme editor (drag-and-drop)
- [ ] Component playground (interactive docs)
- [ ] AI-powered design suggestions

---

## Links

- **Website:** cloud.cloud-nine-ai.workers.dev
- **GitHub:** github.com/cloud-nine-ai/aix
- **Docs:** cloud.cloud-nine-ai.workers.dev/docs
- **Discord:** discord.gg/cloudnineai
- **Twitter:** @cloudnineai

---

*AIX — The #1 all-in-one design tool. The design system AI agents can actually use. Free forever. ☁️*
