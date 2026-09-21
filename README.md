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

This project is configured as a Cloudflare Worker in `wrangler.jsonc`. The Holocron build emits the Worker entry point to `dist/.holocron/rsc/index.js` and browser assets to `dist/.holocron/client`.

For Cloudflare's connected Git deployment, use:

- **Build command:** `npm run build`
- **Deploy command:** `npx wrangler deploy`

For a local deployment after authenticating Wrangler:

```bash
npx wrangler login
npm run deploy
```

The `workers_dev` URL and the configured custom domain are both served by the same deployment. If deployment reports that the entry point is missing, confirm that the build step ran first and that `dist/.holocron/rsc/index.js` exists before invoking Wrangler.

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
