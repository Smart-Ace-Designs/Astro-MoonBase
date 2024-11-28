# Astro Template: Moon Base

An opinionated Astro starter template with built-in support for Vue, shadcn-vue, Tailwind CSS, Prettier, view transitions, and import aliases.

## Deployment Methods
> Note:  
> At this time using `bun create` is dependent on `npm` being present in the path.  
> It is recommended to install `Node.js` even if `bun` is used exclusively.
### bun
```sh
bun create astro@latest -- --template smart-ace-designs/astro-moonbase --typescript strict project-name
```
### npm
```sh
npm create astro@latest -- --template smart-ace-designs/astro-moonbase --typescript strict project-name
```
### PowerShell
Add this function to your PowerShell profile or a PowerShell module:
```powershell
function New-AstroMoonbaseProject
{
    [CmdletBinding()]
    Param
    (
        [Parameter(Mandatory = $true)] [string]$ProjectName,
        [Parameter(Mandatory = $true)] [string]$Location,
        [Parameter(Mandatory = $false)] [switch]$StartCode,
        [Parameter(Mandatory = $false)] [switch]$StartApp,
        [Parameter(Mandatory = $false)] [ValidateSet("bun", "npm")] [string]$PackageManager = "bun"
    )

    switch ($PackageManager)
    {
        "bun" {$PackageManagerX = "bunx"}
        "npm" {$PackageManagerX = "npx"}
    }

    Clear-Host
    $Message = "Astro Deployment Tool"
    $Width = $Host.UI.RawUI.WindowSize.Width
    Write-Host
    Write-Host ((" " * ($Width - $Message.Length)) + $Message) -ForegroundColor Green
    Write-Host ("=" * $Width)

    if (Test-Path -Path "$Location\$ProjectName")
    {
        Write-Host "`nProject folder ($ProjectName) already exists."
        Write-Host "Operation cancelled...liftoff failed!"
        return
    }

    Set-Location $Location
    & $PackageManagerX create-astro@latest -- --template smart-ace-designs/astro-moonbase `
        --typescript strict --git --no-install $ProjectName

    if (!(Test-Path -Path $ProjectName))
    {
        Write-Host "`nProject folder ($ProjectName) was not created."
        Write-Host "Operation cancelled...liftoff failed!"
        Write-Host "`nIf using Bun please run `"bun pm cache rm`" to clear the cache and try again."
        return
    }
    
    Write-Host
    Set-Location $ProjectName
    switch ($PackageManager)
    {
        "bun" {& $PackageManager install --no-summary}
        "npm" {& $PackageManager install --silent}
    }

    & $PackageManagerX @astrojs/upgrade
    & $PackageManager update --silent --save

    [void](New-Item -Name "assets" -Path src -ItemType Directory)
    Clear-Content -Path "README.md"

    Write-Host
    & $PackageManagerX prettier . --write --log-level silent
    & $PackageManagerX prettier . --check
    if ($StartCode -and (Get-Command code -ErrorAction SilentlyContinue)) {code .}
    Write-Host
    Write-Host ("=" * $Width)
    if ($StartApp) {& $PackageManager run dev}
}
```

## Add `shadcn-vue` Component
To add a shadcn-vue component to your project (example: [Alert](https://www.shadcn-vue.com/docs/components/alert.html)):
### bun
```sh
bun x shadcn-vue@latest add alert
```
### npm
```sh
npx shadcn-vue@latest add alert
```

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
|   └── env.d.ts
├── .gitignore
├── .prettierrc.mjs
├── astro.config.mjs
├── components.json
├── package.json
├── README.md
├── tailwind.config.mjs
└── tsconfig.json
```

