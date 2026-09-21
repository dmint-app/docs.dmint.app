# dmint.app

> **The official documentation platform and public knowledge base for the Dmint ecosystem.**

Live site: **[https://dmint.app](https://dmint.app)**

---

## Tech Stack

- **Documentation Engine**: [Holocron](https://holocron.so), using `docs.json` and MDX
- **Page Format**: MDX (Markdown + JSX Components)
- **Deployment**: Cloudflare Workers with the `docs-dmint-app` Worker and custom domain `docs.dmint.app`

## Local Development & Preview

```bash
npm install
npm run dev
```

Open your browser at **http://localhost:3334** to view the development site.

## Cloudflare Deployment

This project is configured as a Cloudflare Worker in `wrangler.jsonc`. The Holocron build emits the Worker entry point to `dist/rsc/index.js` and browser assets to `dist/client`.

After authenticating Wrangler with the Cloudflare account that owns the Worker, build and deploy with:

```bash
npx wrangler login
npm run deploy
```

The `workers_dev` URL and the configured custom domain are both served by the same deployment. If the Worker returns a root 404, verify that the build completed and that `dist/rsc/index.js` and `dist/client` exist before deploying.

## Repository Structure

```text
docs.dmint.app/
├── docs.json                   # Documentation configuration
├── wrangler.jsonc              # Cloudflare Worker and asset configuration
├── vite.config.ts              # Holocron/Vite build configuration
├── logo/                       # Brand SVG assets
├── favicon.svg                 # Browser favicon
├── index.mdx                   # Documentation home
├── introduction.mdx            # Product introduction
├── quickstart.mdx              # Hands-on tutorial
├── concepts/                   # Architectural concepts
├── guides/                     # Task-oriented guides
├── integrations/               # Agent integration guides
├── architecture/               # Security specifications
└── reference/                  # Technical reference
```

---

## License

Apache-2.0. See [LICENSE](LICENSE) for details.
