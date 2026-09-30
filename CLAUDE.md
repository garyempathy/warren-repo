# warren-repo

Angular 22 web application.

## Tech stack

- **Framework**: Angular 22 (standalone components, signals)
- **Router**: `@angular/router`
- **Styles**: SCSS
- **Tests**: Vitest via `@angular/build:unit-test` (no browser required)
- **Lint**: ESLint + `angular-eslint` + `typescript-eslint`
- **Formatter**: Prettier (`.prettierrc`)

## Key commands

| Command | Purpose |
|---|---|
| `npm start` | Dev server at http://localhost:4200 |
| `npm run build` | Production build |
| `npm test` | Run unit tests (vitest, watch mode) |
| `npm run lint` | ESLint all `.ts` and `.html` |
| `npm run typecheck` | TypeScript type-check (no emit) |
| `npm run check:all` | Lint + typecheck + tests (CI gate) |

## Quality gate

```
npm run check:all
```

All three steps must exit zero before committing.

## Project structure

```
src/
  app/
    app.ts          Root component
    app.html        Root template
    app.scss        Root styles
    app.config.ts   Application config (providers)
    app.routes.ts   Route definitions
    app.spec.ts     Root component tests
  main.ts           Bootstrap
  styles.scss       Global styles
public/             Static assets
```

## Conventions

- Standalone components only (no `NgModule`).
- Selector prefix: `app-` for components, `app` for directives.
- Component styles in `.scss` file alongside component.
- New routes go in `app.routes.ts`; lazy-load feature modules.
- Use Angular signals (`signal`, `computed`, `effect`) for local state.
