# dmint.app

> **The official documentation platform and public knowledge base for the Dmint ecosystem.**

Live site: **[https://dmint.app](https://dmint.app)**

---

## Tech Stack

- **Documentation Engine**: [Mintlify](https://mintlify.com)
- **Configuration**: `docs.json` (and `mint.json` symlink)
- **Page Format**: MDX (Markdown + JSX Components)
- **Deployment**: Mintlify Cloud connected to GitHub with custom domain `dmint.app` via Cloudflare DNS CNAME.

---

## Local Development & Preview

To preview the documentation site locally:

```bash
# Start local Mintlify dev server:
npx mintlify dev
```

Open your browser at **http://localhost:3000** to view live hot-reloading documentation.

---

## Repository Structure

```text
dmint.app/
├── docs.json                   # Mintlify configuration (theme, navigation, colors)
├── mint.json                   # Symlink to docs.json for legacy compatibility
├── logo/                       # Brand SVG assets (light & dark)
├── favicon.svg                 # Browser tab favicon
├── index.mdx                   # Documentation home & hero overview
├── introduction.mdx            # Problem space, deterministic principles, 4 pillars
├── quickstart.mdx              # 5-minute hands-on tutorial
├── concepts/                   # Deep architectural mental models
│   ├── overview.mdx
│   ├── capabilities.mdx
│   ├── request-binding.mdx
│   ├── approvals.mdx
│   └── policies.mdx
├── guides/                     # Task-oriented step-by-step guides
│   ├── protecting-mcp.mdx
│   ├── authoring-policies.mdx
│   ├── agent-skills.mdx
│   ├── python-integration.mdx
│   └── human-approvals.mdx
├── integrations/               # Agent copy-paste setups
│   ├── cursor.mdx
│   ├── claude-code.mdx
│   ├── antigravity.mdx
│   └── custom-agents.mdx
├── architecture/               # Security specifications & threat model
│   ├── deterministic-enforcement.mdx
│   ├── security-invariants.mdx
│   └── threat-model.mdx
└── reference/                  # Technical reference manuals
    ├── cli.mdx
    ├── policy-schema.mdx
    ├── mcp-protection-schema.mdx
    └── core-api.mdx
```

---

## License

Apache-2.0. See [LICENSE](LICENSE) for details.
