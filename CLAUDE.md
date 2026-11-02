# CLAUDE.md

## Project Structure

Excalidraw is a **monorepo** with a clear separation between the core library and the application:

- **`packages/excalidraw/`** - Main React component library published to npm as `@excalidraw/excalidraw`
- **`excalidraw-app/`** - Full-featured web application (excalidraw.com) that uses the library
- **`packages/`** - Core packages: `@excalidraw/common`, `@excalidraw/element`, `@excalidraw/math`, `@excalidraw/utils`
- **`examples/`** - Integration examples (NextJS, browser script)

## Development Workflow

1. **Package Development**: Work in `packages/*` for editor features
2. **App Development**: Work in `excalidraw-app/` for app-specific features
3. **Testing**: Always run `yarn test:update` before committing
4. **Type Safety**: Use `yarn test:typecheck` to verify TypeScript

## Development Commands

```bash
yarn test:typecheck  # TypeScript type checking
yarn test:update     # Run all tests (with snapshot updates)
yarn fix             # Auto-fix formatting and linting issues
```

## Architecture Notes

### Package System

- Uses Yarn workspaces for monorepo management
- Internal packages use path aliases (see `vitest.config.mts`)
- Build system uses esbuild for packages, Vite for the app
- TypeScript throughout with strict configuration

<!-- autoforge:begin (managed by `autoforge integrations`; content inside this block is replaced on reinstall) -->
## Autoforge behavioral contracts

Approved contracts in `.autoforge/contracts/` describe existing behavior that must keep working.

- Before changing code, run `autoforge context --task "<what you are about to do>"` and respect every invariant it lists.
- After changing code, run `autoforge check` and fix every violation before you finish (exit code 2 = violations found).
- Never weaken, skip, or delete protected tests, and never edit files in `.autoforge/` to make a check pass.
- If a requested change conflicts with a contract, stop and ask the user. Intentional behavior changes go through `autoforge contracts propose`, which a human must approve. Never run `contracts approve`, `contracts review --approve`, or `checks trust` yourself.
<!-- autoforge:end -->
