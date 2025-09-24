# Ribnip

A modern Next.js application built with cutting-edge technologies for fast development and optimal performance.

## 🚀 Tech Stack

- **[Next.js 15](https://nextjs.org/)** - React framework with App Router
- **[React 19](https://react.dev/)** - Latest React with enhanced features
- **[TypeScript](https://www.typescriptlang.org/)** - Type-safe development
- **[Tailwind CSS](https://tailwindcss.com/)** - Utility-first CSS framework
- **[Bun](https://bun.sh/)** - Ultra-fast JavaScript runtime and package manager
- **[Biome](https://biomejs.dev/)** - Fast formatter and linter
- **[Docker](https://www.docker.com/)** - Containerized deployment

## 🛠️ Prerequisites

Before you begin, ensure you have the following installed:

- [Bun](https://bun.sh/) (latest version)
- [Docker](https://www.docker.com/) (optional, for containerized development)

## ⚡ Quick Start

### Local Development

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd ribnip
   ```

2. **Install dependencies**
   ```bash
   bun install
   ```

3. **Start the development server**
   ```bash
   bun dev
   ```

4. **Open your browser**
   
   Navigate to [http://localhost:3000](http://localhost:3000) to see your application running.

### Docker Development

For a containerized development experience:

```bash
# Start development server in Docker
docker compose up

```
Navigate to [http://localhost:3000](http://localhost:3000) to see your application running.

## 📋 Available Scripts

| Command | Description |
|---------|-------------|
| `bun dev` | Start development server |
| `bun run start` | Start production server |
| `bun run lint` | Run Biome linting |
| `bun run format` | Format code with Biome |
| `bun run check` | Run lint and format checks |

## 🔧 Development Workflow

### Code Quality

This project maintains high code quality through automated tools:

- **Pre-commit hooks** automatically format and lint your code
- **Biome** provides fast, unified linting and formatting
- **TypeScript** ensures type safety
- **Conventional commits** for consistent commit messages

### Environment Variables

Environment variables are managed with type safety using T3 Env:

1. Add your variables to `src/lib/Env.mjs`
2. Define the schema with Zod validation
3. Access them through the typed `env` object

## 🐳 Docker Support

The application supports both development and production Docker workflows:

- **Development**: Hot reloading with volume mounts
- **Production**: Multi-stage build with optimized Bun runtime
- **Consistent environment** across all deployment targets

---

Built with modern tools for exceptional developer experience and performance.
