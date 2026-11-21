# skills

Claude Code skills. Most are for a TypeScript monorepo: pnpm + Turborepo, a React + Vite dashboard, a Fastify API, Prisma on Postgres with row-level security, Zod everywhere, Vitest and Playwright. A few are general and work in any project.

## Use them

Copy the skills you want into your project's `.claude/skills/`:

```bash
cp -r skills/* /path/to/your-project/.claude/skills/
```

Then fill in `project-context` for your product, adjust `project` to your layout, and list the skills in your `CLAUDE.md`. The skills assume the `@repo/` package scope and the layout in `project`; rename to match yours.

To use a general skill in every project, copy it into `~/.claude/skills/` instead.

## TypeScript monorepo skills

| Skill | Covers |
|---|---|
| `project-context` | Template: what the product is and the rules the code must enforce |
| `project` | Monorepo layout, package boundaries, commands |
| `coding-style` | Formatting, control flow, imports, naming, TypeScript and React conventions |
| `create-skill`, `refine-skill` | Writing and maintaining skills |
| `adding-components` | React components in `apps/web` |
| `adding-context-providers` | React context providers |
| `creating-pages` | Pages and routes |
| `creating-hooks` | Data-fetching, polling and streaming hooks |
| `creating-forms` | react-hook-form + Zod forms |
| `creating-api-routes` | Fastify routes and their security rules |
| `creating-services` | Wrappers around external SDKs and APIs |
| `prisma-and-migrations` | Prisma schema, migrations, tenancy and row-level security |
| `shared-validation` | Zod schemas and validation copy shared by API and web |
| `testing` | Vitest, Testing Library, route tests, RLS tests, Playwright |
| `utilities` | Pure helper functions |

## General skills

| Skill | Covers |
|---|---|
| `plain-talk` | How Claude explains things and asks questions in chat: answer first, plain words, short |
| `skill-checklist` | Yes/no checks for writing or reviewing any skill, built on ideas from *The Pragmatic Programmer* |
