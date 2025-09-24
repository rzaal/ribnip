# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

**Local Development (Bun)**:
- `bun dev` - Start development server
- `bun run build` - Build production application  
- `bun run lint` - Run Biome linting (use this to check code quality)
- `bun run format` - Format code with Biome
- `bun run check` - Run Biome lint + format check

**Docker Development**:
- `bun run docker:dev` - Start development server in Docker
- `bun run docker:build` - Build Docker image
- `bun run docker:prod` - Start production server in Docker

## Project Architecture

**Tech Stack**: Next.js 15.1.3 with App Router, React 19, TypeScript, Tailwind CSS, Bun package manager, Biome for linting/formatting

**Key Directories**:
- `src/app/` - Next.js App Router pages and layouts
- `src/lib/` - Utility functions and configurations (including type-safe env config)
- `public/` - Static assets

**Important Files**:
- `src/lib/Env.mjs` - Type-safe environment variables using T3 Env and Zod
- `src/app/layout.tsx` - Root layout component
- `src/app/globals.css` - Global styles with Tailwind CSS
- `biome.json` - Biome configuration for linting and formatting
- `Dockerfile` - Bun-based containerization
- `docker-compose.yml` - Development Docker setup
- `docker-compose.prod.yml` - Production Docker setup

## Code Standards

- **Package Manager**: Always use Bun, never npm or yarn
- **Imports**: Use `@/*` alias for src imports (configured in tsconfig.json)
- **Linting/Formatting**: Biome with single quotes, 2-space indentation, 100 character line width
- **Type Imports**: Use `import type` for TypeScript type-only imports (enforced by Biome)
- **Commits**: Conventional commit format enforced via commitlint

## Quality Controls

- Pre-commit hooks run Biome check (lint + format) on staged files
- Always run `bun run check` after making changes to ensure code quality
- TypeScript strict mode is enabled - address all type errors
- Biome organizes imports automatically

## Environment Configuration

Environment variables are managed through `src/lib/Env.mjs` using T3 Env for type safety. Add new variables to both the Zod schema and the env object in this file.

## Docker Usage

The project supports both development and production Docker workflows:
- Development: Uses volume mounts for hot reloading
- Production: Multi-stage build with optimized Bun runtime
- All Docker commands use Bun as the package manager and runtime