---
description: Repository Information Overview
alwaysApply: true
---

# Claude Code Plugins Monorepo Information

## Summary
A comprehensive monorepo for Claude Code plugins, featuring a marketplace website, CLI management tools, and hundreds of plugins including Model Context Protocol (MCP) servers and instruction-based plugins. It provides a centralized hub for discovering, validating, and installing AI-enhanced capabilities.

## Structure
- `marketplace/`: Astro-based website (claudecodeplugins.io) for plugin discovery.
- `plugins/`: Organized by category (e.g., `mcp/`, `saas-packs/`, `ai-ml/`, `devops/`).
  - `mcp/`: TypeScript and Python-based Model Context Protocol servers.
  - Category folders (e.g., `security/`, `database/`): Markdown-based instruction plugins.
- `packages/`:
  - `cli/`: `@intentsolutionsio/ccpi` - CLI tool for plugin management.
  - `plugin-validator/`: Utility for validating plugin structure and schema.
  - `analytics-daemon/` & `analytics-dashboard/`: Backend and frontend for usage analytics.
- `scripts/`: Extensive automation suite for auditing, fixing, and synchronizing the marketplace.

## Language & Runtime
**Languages**: TypeScript (Primary), Node.js, Python (Scripts & some MCPs), Markdown (Instructions)  
**Node.js Version**: >= 20.0.0  
**Build System**: pnpm workspaces (v9+)  
**Package Manager**: pnpm at root, npm for marketplace component.

## Dependencies
**Main Dependencies**:
- **Marketplace**: `astro`, `tailwindcss`, `fuse.js`.
- **MCP SDK**: `@modelcontextprotocol/sdk` (TS), `mcp` (Python).
- **CLI**: `commander`, `chalk`, `axios`, `ora`.
- **Validation**: `zod`, `typescript-eslint`.

## Build & Installation
```bash
# Install all dependencies
pnpm install

# Build all workspace projects
pnpm run build

# Synchronize marketplace metadata
pnpm run sync-marketplace
```

## Docker
**Configuration**: Root `docker-compose.yml` provides a **Qdrant** vector database service.
- **Image**: `qdrant/qdrant`
- **Ports**: `6333:6333`

## Testing & Validation
**Frameworks**: Vitest (TS), Pytest (Python), Playwright (Marketplace E2E).
**Locations**: `tests/`, `packages/*/tests/`, `plugins/mcp/*/tests/`.
**Validation Tools**: 
- `scripts/validate-all-plugins.sh`: Full plugin suite validation.
- `scripts/quick-test.sh`: Fast validation path.
- `python3 scripts/validate-skills-schema.py`: Schema enforcement.

**Run Commands**:
```bash
# Run all tests
pnpm test

# Run type checks
pnpm typecheck

# Quick validation
./scripts/quick-test.sh
```

## Main Files & Resources
- **Marketplace Source of Truth**: `.claude-plugin/marketplace.extended.json`.
- **Generated Catalog**: `.claude-plugin/marketplace.json` (Do not edit directly).
- **Plugin Manifests**: `.claude-plugin/plugin.json` in each plugin directory.
- **Skill Definitions**: `skills/*/SKILL.md` (2025 spec).
- **CLI Entry Point**: `packages/cli/src/index.ts`.
