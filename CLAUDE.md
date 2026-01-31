# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Technical documentation site for the Defiesta Execution Kernel, built with Docusaurus 3.9.2. The Execution Kernel is a consensus-critical, deterministic agent execution framework for RISC Zero zkVM.

Live site: https://docs.defiesta.xyz

## Commands

```bash
npm run start    # Dev server at localhost:3000
npm run build    # Build static site to ./build
npm run serve    # Preview built site locally
npm run typecheck  # TypeScript type checking
```

## Architecture

### Content Structure

Documentation lives in `docs/` with this hierarchy:
- `intro.md` - Landing page (served at root `/`)
- `architecture/` - System architecture docs
- `getting-started/` - Setup and quick start guides
- `kernel/` - Kernel core documentation (input/journal formats, versioning)
- `sdk/` - Agent SDK documentation
- `guest-program/` - zkVM guest program docs
- `agent-pack/` - Agent packaging format
- `onchain/` - Smart contract integration
- `reference/` - Glossary, repo map, changelog

### Key Configuration Files

- `docusaurus.config.ts` - Site config, navbar, footer, theme settings
- `sidebars.ts` - Sidebar navigation structure (edit here to add/reorder pages)
- `src/css/custom.css` - Custom styling

### Documentation Features

- **Mermaid diagrams**: Enabled via `@docusaurus/theme-mermaid`
- **Code highlighting**: Rust, TypeScript, Solidity, TOML, JSON, Bash
- **Admonitions**: `:::note`, `:::warning`, `:::tip`, `:::danger`
- **Dark mode**: Default with toggle, respects system preference

### Page Format

Every doc page requires frontmatter:
```yaml
---
title: Page Title
sidebar_position: 1
---
```

## Deployment

Auto-deploys to GitHub Pages on push to `main` via `.github/workflows/deploy-docs.yml`.

The docs are served at root (`/`) with `routeBasePath: '/'` - there is no `/docs` prefix.
