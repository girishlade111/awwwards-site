# Awwwards Site

An Awwwards-caliber creative portfolio site — cinematic dark theme, 3D WebGL scenes, GSAP scroll animations, page transitions, a portfolio gallery, and a built-in blog. Built with Next.js as a fully static site.

## What it does

- **Immersive hero** — WebGL 3D scenes (Three.js / React Three Fiber) with post-processing glow effects.
- **GSAP animations** — scroll-driven reveals, parallax, and animated section transitions via `@gsap/react`.
- **Page transitions** — custom `TransitionProvider` + `TransitionLink` for smooth animated navigation.
- **Portfolio** — project showcase pages (`/portfolio/*`).
- **Blog** — statically generated blog (`/blog` + `/blog/[slug]`), posts defined in `lib/blog-posts.tsx`.
- **Contact page** — with form UI.
- Fully static — no server, no database, no API keys.

## Features

- Three.js 3D hero scenes with bloom/post-processing (`@react-three/fiber`, `@react-three/drei`, `@react-three/postprocessing`)
- GSAP + ScrollTrigger animations
- Dark/light theme support via `next-themes`
- Static blog with `generateStaticParams` (no CMS needed)
- Responsive, mobile-first layout
- shadcn/ui component library (Radix primitives) + Lucide icons

## Tech stack

- [Next.js](https://nextjs.org/) 15 (App Router) with static export (`output: 'export'`)
- [React](https://react.dev/) 19 + [TypeScript](https://www.typescriptlang.org/)
- [Three.js](https://threejs.org/) via React Three Fiber
- [GSAP](https://gsap.com/) (+ `@gsap/react`)
- [Tailwind CSS](https://tailwindcss.com/) 3
- [shadcn/ui](https://ui.shadcn.com/) on [Radix UI](https://www.radix-ui.com/)
- Package manager: [pnpm](https://pnpm.io/)

## Quick start

```bash
# Install dependencies
pnpm install

# Run the dev server
pnpm dev
# open http://localhost:3000

# Build a static export into ./out
pnpm build

# Preview the static export locally
npx serve out
```

## Project structure

```
.
├── app/
│   ├── page.tsx            # Home (hero + portfolio preview + blog preview)
│   ├── blog/               # Blog index
│   ├── blog/[slug]/        # Individual blog posts (generateStaticParams)
│   ├── portfolio/          # Project showcase pages
│   ├── contact/            # Contact page
│   └── layout.tsx          # Root layout (fonts, theme, transition providers)
├── components/
│   ├── hero.tsx            # Hero section
│   ├── scene.tsx glow-scene.tsx   # 3D WebGL scenes
│   ├── gsap-provider.tsx   # GSAP context/setup
│   ├── transition-provider.tsx transition-link.tsx  # Page transitions
│   ├── header.tsx footer.tsx portfolio.tsx blog-preview.tsx
│   └── ui/                 # shadcn/ui primitives
├── context/
│   └── transition-context.tsx
├── lib/
│   ├── blog-posts.tsx      # Blog content (edit posts here)
│   └── utils.ts
├── public/images/          # Site imagery
└── next.config.mjs         # Static export config (output: 'export', unoptimized images)
```

## Adding a blog post

Add an entry to `allPosts` in `lib/blog-posts.tsx` with a unique `slug`, title, and content — the page is generated automatically at build time.

## Environment variables

None required. No backend, no API keys, no database.

## Deployment

This is a fully static site (`output: 'export'` in `next.config.mjs`):

1. `pnpm build` produces a static site in `./out`.
2. Deploy `./out` to any static host — Cloudflare Pages, GitHub Pages, Netlify, Vercel.
3. No server, no environment variables needed.

## License

Free to use and modify.

---

Built by Girish Lade — [ladestack.in](https://ladestack.in)
