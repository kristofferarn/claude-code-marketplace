# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Claude Code marketplace repository for distributing custom plugins. The repository follows the Claude Code marketplace structure with:

- `.claude-plugin/marketplace.json` - Marketplace manifest defining available plugins
- `microsoft-dev/` - A plugin directory containing Microsoft 365 development resources

## Repository Structure

```
.
├── .claude-plugin/
│   └── marketplace.json     # Marketplace manifest listing all plugins
└── microsoft-dev/           # Plugin for Microsoft 365 development
    ├── .claude-plugin/
    │   └── plugin.json      # Plugin metadata
    └── .mcp.json           # MCP server configurations
```

## Plugin Architecture

### Marketplace Manifest

The root `.claude-plugin/marketplace.json` file:
- Defines the marketplace name, version, and owner
- Lists all available plugins with their name, description, and source path
- Each plugin entry points to a subdirectory containing the plugin implementation

### Plugin Structure

Each plugin (e.g., `microsoft-dev/`) contains:
- `.claude-plugin/plugin.json` - Plugin metadata (name, description, version, author)
- `.mcp.json` - MCP (Model Context Protocol) server configurations for the plugin

### MCP Server Configuration

The `.mcp.json` file defines MCP servers that provide tools and resources:
- HTTP-based servers are specified with `type: "http"` and a URL
- The microsoft-dev plugin includes:
  - `microsoft-learn` - Microsoft Learn documentation API
  - `context7` - Context7 library documentation API

## Adding New Plugins

To add a new plugin:
1. Create a new directory in the repository root
2. Add `.claude-plugin/plugin.json` with plugin metadata
3. Optionally add `.mcp.json` if the plugin uses MCP servers
4. Update the root `.claude-plugin/marketplace.json` to include the new plugin

## Git Workflow

- Main branch: `main`
- Keep commits focused on plugin additions/updates
- No build process required - this is a distribution repository
