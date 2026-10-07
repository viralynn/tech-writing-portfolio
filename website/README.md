# Website

Source for the portfolio site at https://viralynn.github.io/tech-writing-portfolio/, built with [Docusaurus](https://docusaurus.io/).

## Install

```bash
npm ci
```

`npm ci` installs exactly the versions pinned in `package-lock.json`.

## Preview locally

```bash
npm run build
npm run serve
```

Then open http://localhost:3000/tech-writing-portfolio/. Press Ctrl+C to stop the server.

## Deployment

Every push to `main` runs the workflow in `.github/workflows/deploy.yml`. It installs dependencies with `npm ci`, builds the site with `npm run build` (Node 22), and publishes `website/build` to GitHub Pages. There is no separate deploy command: pushing to `main` publishes the site.