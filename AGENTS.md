# AGENTS.md

## Project Overview
Vue 3 + TypeScript + Vite SPA using pnpm. Single application, not a monorepo.

## Commands
```bash
pnpm dev          # Start dev server
pnpm build        # Production build
pnpm preview      # Preview build
pnpm lint         # Biome check
pnpm lint:fix     # Biome check --write
pnpm format      # Biome format
npx tsc --noEmit # TypeScript check
pnpm prepare     # Initialize Husky hooks
```

## Verification Order
`pnpm lint:fix` → `npx tsc --noEmit` before committing

## Key Conventions

### Component Auto-Registration
- Components go in `src/components/<ComponentName>/index.vue`
- Folder name becomes component name (PascalCase)
- Auto-registered globally via `src/plugins/autoImportComponents.ts`

### Styling
- SCSS with `<style scoped lang="scss">`
- `@/styles/index.scss` auto-imported in all SCSS (configured in vite.config.ts)
- Use SCSS variables from `src/styles/var.scss`

### Biome Style
- 2-space indent, single quotes, semicolons required
- Vue block order: `['template', 'script', 'style']`

### Commit Messages
Conventional Commits required: `feat:`, `fix:`, `docs:`, `style:`, `refactor:`, `test:`, `chore:`

## Path Alias
`@` → `src/`

## Entry Points
- Dev entry: `src/main.ts`
- HTML entry: `index.html`
- Router: `src/router/index.ts`
- Stores: `src/stores/*.ts` (Pinia)
