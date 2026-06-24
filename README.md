<!-- ASTRO:REMOVE:START -->

# Astro Template: Moon Base

Astro **Moon Base** is an opinionated [Astro 7](https://astro.build/) starter template with built-in support for Vue, shadcn-vue, Tailwind CSS, Prettier, view transitions, and aliases.

Using `create astro@latest` provides everything you need to create a basic Astro 7 application. However, it is missing a few useful items that you might find yourself manually adding to every new Astro 7 project. The **Moon Base** template was created to automatically include these items and the [Vue integration](https://docs.astro.build/en/guides/integrations-guide/vue/) plus a starter `AstroWelcome` component to showcase Tailwind and shadcn-vue. This provides a great starting point with sample code for a new Astro 7 project with Vue client islands, Tailwind and shadcn-vue.

The template includes:

- An initial Astro 7 project structure
- Astro [View Transitions](https://docs.astro.build/en/guides/view-transitions/)
- Astro [Aliases](https://docs.astro.build/en/guides/imports/#aliases)
- [Tailwind CSS](https://tailwindcss.com/)
- [Prettier](https://prettier.io/)
- [Vue](https://vuejs.org/)
- [shadcn-vue](https://www.shadcn-vue.com/)
- A default _MainLayout.astro_ layout file
- A default _global.css_ file
- A default _components.json_ file with `neutral` base color
- Default _.vscode_ files to properly handle Tailwind CSS, recommended extensions, and default Prettier formatters
- A starter component to showcase Tailwind CSS
- The `dev` script set to `"astro dev --open"`

## Deployment Methods

### npm

```sh
npm create astro@latest -- --template smart-ace-designs/astro-moonbase project-name
```

### bun

```sh
bun create astro@latest -- --template smart-ace-designs/astro-moonbase project-name
```

### pnpm

```sh
pnpm create astro@latest --template smart-ace-designs/astro-moonbase project-name
```

### yarn

```sh
yarn create astro@latest --template smart-ace-designs/astro-moonbase project-name
```

## Using [shadcn-vue](https://www.shadcn-vue.com/) Components

To add a shadcn-vue component to your Astro project for use with a Vue client island:
[shadcn-vue CLI](https://www.shadcn-vue.com/docs/cli.html#add)

## Project Structure

After deploying the Astro **Moon Base** template you will see the following files and directories in your project root:

```text
/
├── .vscode/
│   ├── extensions.json
│   ├── launch.json
│   └── settings.json
├── public/
│   └── favicon.svg
├── src/
│   ├── components/
│   │   └── AstroWelcome.astro
│   ├── layouts/
│   │   └── MainLayout.astro
│   ├── lib/
│   │   └── utils.ts
│   ├── pages/
│   │   └── index.astro
│   └── styles/
│       └── global.css
├── .gitignore
├── .prettierignore
├── .prettierrc.mjs
├── AGENTS.md
├── astro.config.mjs
├── CLAUDE.md
├── components.json
├── package.json
├── README.md
└── tsconfig.json
```

<!-- ASTRO:REMOVE:END -->
