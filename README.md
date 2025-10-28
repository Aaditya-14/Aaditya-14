# 🕹️ Generate Pac-Man Animation

This repository automatically generates a **Pac-Man contribution graph animation** using a GitHub Action workflow. The animation updates every **12 hours** and pushes the latest SVG files to the `output` branch.

---

## ⚙️ Workflow Configuration

```yaml
name: Generate pacman animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
      - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate pacman-contribution-graph.svg
        uses: abozanona/pacman-contribution-graph@main
        with:
          github_user_name: ${{ github.repository_owner }}

      - name: push pacman-contribution-graph.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

---

## 👋 Hey, What's Up?

<div align="center">
  <img src="https://skillicons.dev/icons?i=ts" height="60" alt="typescript logo" />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=nextjs" height="60" alt="nextjs logo" />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=tailwind" height="60" alt="tailwindcss logo" />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/storybook/storybook-original.svg" height="60" alt="storybook logo" />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=graphql" height="60" alt="graphql logo" />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=go" height="60" alt="go logo" />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=rust" height="60" alt="rust logo" />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=nestjs" height="60" alt="nestjs logo" />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=py" height="60" alt="python logo" />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=aws" height="60" alt="aws logo" />
</div>

---

<div align="center">
  <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&style=for-the-badge" height="25" alt="linkedin logo" />
  <img src="https://img.shields.io/static/v1?message=Twitter&logo=twitter&label=&color=1DA1F2&logoColor=white&style=for-the-badge" height="25" alt="twitter logo" />
  <img src="https://img.shields.io/static/v1?message=Discord&logo=discord&label=&color=7289DA&logoColor=white&style=for-the-badge" height="25" alt="discord logo" />
  <img src="https://img.shields.io/static/v1?message=Twitch&logo=twitch&label=&color=9146FF&logoColor=white&style=for-the-badge" height="25" alt="twitch logo" />
  <img src="https://img.shields.io/static/v1?message=dev.to&logo=dev.to&label=&color=0A0A0A&logoColor=white&style=for-the-badge" height="25" alt="devto logo" />
</div>

---

<div align="center">
  <img src="https://streak-stats.demolab.com?user=Aaditya-14&locale=en&mode=daily&theme=dracula&hide_border=false&border_radius=5&order=3" height="150" alt="streak graph" />
  <img src="https://github-profile-trophy.vercel.app?username=Aaditya-14&theme=dracula&column=-1&row=1&margin-w=8&margin-h=8&no-bg=false&no-frame=false&order=4" height="150" alt="trophy graph" />
</div>

---

## 🟡 Pac-Man Contribution Graph

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Aaditya-14/Aaditya-14/output/pacman-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Aaditya-14/Aaditya-14/output/pacman-contribution-graph.svg">
  <img alt="pacman contribution graph" src="https://raw.githubusercontent.com/Aaditya-14/Aaditya-14/output/pacman-contribution-graph.svg">
</picture>

---

## 📄 How It Works

1. The workflow runs every 12 hours or on every push to `main`.
2. It generates a new Pac-Man contribution graph SVG.
3. The SVG is pushed to the `output` branch.
4. The README automatically displays the updated animation using `<picture>` tags.

---

� **Tip:** Make sure to create the workflow file at `.github/workflows/pacman.yml` with the configuration above to enable the automation!
