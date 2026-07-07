# sola-svelete-ui

A SvelteKit recreation of the [Sola solar energy template](https://demo.templatesjungle.com/sola/index.html), extended into a full solar commerce platform.

## What it is

Marketing site + e-commerce platform for a solar energy company. Covers:

- Product catalogue and shop
- Solar savings calculator
- Quotation request flow
- Blog
- Customer dashboard (orders, quotes, settings)
- Admin panel

## Stack

| Layer | Tech |
|-------|------|
| Frontend | SvelteKit 2 + Svelte 5 (Runes), TypeScript, TailwindCSS 4 |
| UI | shadcn-svelte, Bits UI, Lucide Icons, Embla Carousel, Motion One |
| Data | TanStack Query, Zod, Superforms |
| Charts | Chart.js / ECharts |
| Backend | Node.js 22, Prisma, PostgreSQL, Redis |
| Auth | Better Auth / Lucia |
| Payments | Stripe + Razorpay |
| Media | Cloudinary, UploadThing |
| Email | Resend |
| Deploy | Vercel + Supabase + Cloudflare |

## Getting started

```bash
npm create svelte@latest solar-platform
cd solar-platform
npm install
npm run dev
```

## Reference

- `reference/index.html` — original Bootstrap 5 Sola template
- `reference/figma/` — Figma design file
- `reference/PLAN.md` — 14-phase build plan
