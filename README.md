# Astro Template: Moon Base

**Moon Base** is an opinionated Astro 5 starter template with built-in support for Vue, shadcn-vue, Tailwind CSS, Prettier, view transitions, and import aliases and includes a basic starter component.

Using `bunx create-astro@latest` or `npx create-astro@latest` provides everything you need to create a basic Astro application. However, it is missing a few useful items that I found myself manually adding to every Astro project I created.  To address this problem, I created this template to automatically include these items plus support for Vue and shadcn-vue. Additionally, a custom PowerShell function was created to deploy this template and provide some additional functionality that the template cannot.

The template includes:
- [Tailwind CSS v4.1](https://tailwindcss.com/)
- [Prettier](https://prettier.io/)
- [Vue](https://vuejs.org/)
- [shadcn-vue](https://www.shadcn-vue.com/)
- Astro [View Transitions](https://docs.astro.build/en/guides/view-transitions/)
- Astro [Import Aliases](https://docs.astro.build/en/guides/typescript/#import-aliases)
- A default _MainLayout.astro_ layout file
- A default _global.css_ file
- A default _components.json_ file with `neutral` base color (required by shadcn-vue)
- Default _.vscode_ files to properly handle Tailwind CSS, recommended extensions, and default Prettier formatters
- A starter component to showcase Tailwind CSS
- The `dev` script set to `"astro dev --open"`

The PowerShell function:
- Creates an additional empty folder: _assets_
- Blanks out the _README.md_ file
- Runs the `prettier` CLI to provide an intial format of all project files
- Initializes a _Git_ repository
- Automatically navigates to the project folder and peforms an initial install
- Runs `astro update` to update the core Astro packages to the latest versions and runs your preferred package manager (npm or bun) to update the other packages
- Provides an option to launch the site and/or open the project folder with VS Code post deployment

## Deployment Methods
### bun
```sh
bunx create-astro@4.11.1 -- --template smart-ace-designs/astro-moonbase project-name
```
### npm
```sh
npx create-astro@latest -- --template smart-ace-designs/astro-moonbase project-name
```
### PowerShell
A PowerShell module or a standalone function is available here:
[SmartAceDesigns.AstroLiftoff](https://github.com/Smart-Ace-Designs/SmartAceDesigns.AstroLiftoff)

```sh
New-AstroProject -ProjectName project-name -Location parent-folder -Template astro-moonbase
```

https://github.com/user-attachments/assets/8f130bfc-6aab-477d-95cd-7ca8a4a641b8

## Using [shadcn-vue](https://www.shadcn-vue.com/) Components
To add a shadcn-vue component to your Astro project for use with a Vue client island:
[shadcn-vue CLI](https://www.shadcn-vue.com/docs/cli.html#add)

## Project Structure

Inside of your Astro project you will see the following folders and files:

```text
/
├── .vscode/
│       └── extensions.json
│       └── launch.json
│       └── settings.json
├── public/
│       └── favicon.svg
├── src/
|   ├── components/
│       └── AstroWelcome.astro
|   ├── layouts/
│       └── MainLayout.astro
|   ├── lib/
│       └── utils.ts
│   ├── pages/
│       └── index.astro
|   ├── styles/
│       └── global.css
├── .gitignore
├── .prettierrc.mjs
├── astro.config.mjs
├── components.json
├── package.json
├── README.md
└── tsconfig.json
```

When deployed with the custom `New-AstroProject` PowerShell function, you will see the following folders and files:

```text
/
├── .vscode/
│       └── extensions.json
│       └── launch.json
│       └── settings.json
├── public/
│       └── favicon.svg
├── src/
|   ├── assets/
|   ├── components/
│       └── AstroWelcome.astro
|   ├── layouts/
│       └── MainLayout.astro
|   ├── lib/
│       └── utils.ts
│   ├── pages/
│       └── index.astro
|   ├── styles/
│       └── global.css
├── .gitignore
├── .prettierrc.mjs
├── astro.config.mjs
├── components.json
├── package.json
├── README.md
└── tsconfig.json
```
