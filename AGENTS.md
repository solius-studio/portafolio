## Solius Studio - Agent Workspace Guide

### Active Project Skills
Custom agent skills are installed in `.agents/skills/`. Agents working in this repository must adhere to the conventions defined in:
- [`.agents/skills/astro-tailwind-pro/SKILL.md`](./.agents/skills/astro-tailwind-pro/SKILL.md): Astro v5/v7 & Tailwind v4 standards, zero-JS by default, SSR/SSG.
- [`.agents/skills/ai-automations-agency/SKILL.md`](./.agents/skills/ai-automations-agency/SKILL.md): Commercial AI agents, lead qualification, WhatsApp and n8n webhooks.
- [`.agents/skills/apple-dark-ui/SKILL.md`](./.agents/skills/apple-dark-ui/SKILL.md): Dark mode Apple aesthetic, glassmorphism, bento grids, 60fps microinteractions.
- [`.agents/skills/team-github-workflow/SKILL.md`](./.agents/skills/team-github-workflow/SKILL.md): Branching and commit conventions for 2-person collaboration.

---

## Development

When starting the dev server, use background mode:

```
astro dev --background
```

Manage the background server with `astro dev stop`, `astro dev status`, and `astro dev logs`.

## Documentation

Full documentation: https://docs.astro.build

Consult these guides before working on related tasks:

- [Adding pages, dynamic routes, or middleware](https://docs.astro.build/en/guides/routing/)
- [Working with Astro components](https://docs.astro.build/en/basics/astro-components/)
- [Using React, Vue, Svelte, or other framework components](https://docs.astro.build/en/guides/framework-components/)
- [Adding or managing content](https://docs.astro.build/en/guides/content-collections/)
- [Adding styles or using Tailwind](https://docs.astro.build/en/guides/styling/)
- [Supporting multiple languages](https://docs.astro.build/en/guides/internationalization/)
