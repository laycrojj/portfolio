# owenjjackson.com

Source for [www.owenjjackson.com](https://www.owenjjackson.com), currently a holding page while the full portfolio is rebuilt.

Built with Vue 3, Vite and Tailwind CSS.

## Development

Requires Node 20.19 or newer.

```sh
npm install
npm run dev         # local dev server with hot reload
npm run type-check  # TypeScript check
npm run build       # production build into dist/
```

## Deployment

Pushing to `master` runs `.github/workflows/deploy.yml`, which builds the site and publishes `dist/` to the `gh-pages` branch. The custom domain is set by `public/CNAME`, which is copied into every build.

Dependabot (`.github/dependabot.yml`) opens a monthly PR with dependency updates.
