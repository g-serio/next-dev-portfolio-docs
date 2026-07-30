# next-dev-portfolio

A schema-driven developer portfolio template built with Next.js 15 and OlonJS. Deploy to Vercel in one click — get a fully editable site with a built-in Studio CMS, blog, case studies, and AI-ready MCP manifests.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Folonjs%2Fnext-dev-portfolio&integration-ids=oac_1AZc2aypKrBOmV0Ce0BBYLRu&external-id=save2repo&teamSlug=gfscloud)

---

## Features

- **One-click Vercel deploy** with the Save2Repo integration pre-configured
- **Built-in Studio CMS** at `/admin` — edit any section of your site visually, no code needed
- **Save2Repo** — Studio edits commit directly back to your GitHub repo, triggering a new deployment
- **Schema-driven content** — every page section validated by Zod schemas; build fails on invalid content
- **Blog** with full Markdown support (remark-gfm)
- **Case study portfolio** — structured project entries with context, problem, architecture, and results
- **MCP manifests** — every page exposes a machine-readable manifest for AI agents and LLM tools
- **SEO pipeline** — JSON-LD structured data, sitemap.xml, robots.txt, and Open Graph meta generated at build time
- **No database required** — all content lives in flat JSON files in `src/data/`
- **TypeScript end-to-end** with Zod, Next.js 15 App Router, and Tailwind CSS v4

---

## Quick Start

### Deploy to Vercel

Click the button above, or use this URL:

```
https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Folonjs%2Fnext-dev-portfolio&integration-ids=oac_1AZc2aypKrBOmV0Ce0BBYLRu&external-id=save2repo&teamSlug=gfscloud
```

Vercel will:
1. Fork this repo to your GitHub account
2. Install the OlonJS Save2Repo integration
3. Run the prebuild pipeline (bake JSON, generate sitemap, llms.txt)
4. Deploy to a `.vercel.app` domain

### Local Development

```bash
git clone https://github.com/your-username/next-dev-portfolio
cd next-dev-portfolio
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to see your site.
Open [http://localhost:3000/admin](http://localhost:3000/admin) for Studio (local edits write to `src/data/` directly).

---

## Content Structure

All content lives in `src/data/`:

```
src/data/
├── config/
│   ├── site.json       # Site identity, header, footer, social links
│   ├── menu.json       # Header and footer navigation menus
│   └── theme.json      # Design tokens: colors, typography, spacing
├── pages/
│   ├── home.json
│   ├── about.json
│   ├── blog.json
│   ├── work.json
│   ├── contact.json
│   ├── blog/[slug].json
│   └── work/[slug].json
└── collections/
    ├── posts/posts.json      # Blog posts
    └── projects/projects.json  # Case studies
```

Edit any JSON file and redeploy (or save via Studio) to update your site.

---

## Pages

| Page | Route | JSON file |
|------|-------|-----------|
| Home | `/` | `src/data/pages/home.json` |
| About | `/about` | `src/data/pages/about.json` |
| Work | `/work` | `src/data/pages/work.json` |
| Blog | `/blog` | `src/data/pages/blog.json` |
| Contact | `/contact` | `src/data/pages/contact.json` |
| Blog post | `/blog/[slug]` | `src/data/collections/posts/posts.json` |
| Case study | `/work/[slug]` | `src/data/collections/projects/projects.json` |

---

## Studio CMS

Navigate to `/admin` on your site to open Studio. You can:

- Edit page sections inline (hero, bio, skills, philosophy, CTAs)
- Add and edit blog posts (Markdown body support)
- Add and edit case study projects
- Upload images and media assets

In **Save2Repo mode** (enabled by the Vercel integration), Studio saves commit the updated JSON back to your GitHub repo. The new commit triggers a Vercel redeployment automatically.

---

## Environment Variables

| Variable | Description |
|----------|-------------|
| `NEXT_PUBLIC_OLONJS_SAVE2REPO` | Set to `true` to enable Save2Repo (set automatically by the Vercel integration) |
| `NEXT_PUBLIC_OLONJS_CLOUD_URL` | OlonJS Cloud API base URL (optional, for live editing mode) |
| `NEXT_PUBLIC_OLONJS_API_KEY` | OlonJS Cloud API key (optional) |
| `ADMIN_PUBLIC_KEY` | Public key to protect `/admin` on Vercel deployments |

---

## Tech Stack

- [Next.js 15](https://nextjs.org/) — App Router, RSC
- [@olonjs/core](https://npmjs.com/package/@olonjs/core) — schema runtime and page resolution
- [@olonjs/next](https://npmjs.com/package/@olonjs/next) — Next.js server utilities and admin middleware
- [@olonjs/react](https://npmjs.com/package/@olonjs/react) — React rendering utilities
- [@olonjs/studio](https://npmjs.com/package/@olonjs/studio) — visual CMS studio component
- [Zod](https://zod.dev/) — schema validation
- [Tailwind CSS v4](https://tailwindcss.com/) — styling
- [shadcn/ui](https://ui.shadcn.com/) — UI primitives
- [Framer Motion](https://www.framer.com/motion/) — animations

---

## Documentation

Full documentation is available at the project's docs site. Topics include:

- Getting started and Vercel deployment
- Editing pages, blog posts, and projects
- Using Studio CMS
- Customizing theme, navigation, and sections
- MCP manifests and AI discoverability
- Schema validation and advanced configuration

---

## License

See [LICENSE](./LICENSE).
