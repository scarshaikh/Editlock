# EditLock – Video Delivery & Payment Protection Demo

A professional **frontend demo** of a SaaS platform that helps video editors share watermarked previews and unlock final downloads only after payment is verified.

> **Important:** This is a functional UI demo only.  
> - No real payments are processed  
> - No customer videos are uploaded or stored  
> - Payment verification is simulated with local state  
> - Not production-grade security

---

## Tech Stack

- **React 18** + **TypeScript**
- **Vite**
- **Tailwind CSS**
- **React Router v6**
- **Lucide React** (icons)

All free and open-source.

---

## Project Structure

```
editlock-app/
├── public/
├── src/
│   ├── components/       # Navbar, Footer, Layout, VideoPlayer, StatusBadge, DemoBanner
│   ├── context/          # DemoContext (local state for projects & auth)
│   ├── data/             # Sample projects & helper functions
│   ├── pages/            # All 12+ pages
│   ├── types/            # TypeScript interfaces
│   ├── App.tsx           # Routes
│   ├── index.css         # Tailwind + design system
│   └── main.tsx
├── index.html
├── package.json
├── tailwind.config.js
├── postcss.config.js
├── tsconfig.json
├── vite.config.ts
└── README.md
```

---

## Setup & Run Locally

### Prerequisites
- Node.js 18+ and npm

### Install

```bash
cd editlock-app
npm install
```

### Development server

```bash
npm run dev
```

Open the URL shown (usually `http://localhost:5173`).

### Production build

```bash
npm run build
npm run preview
```

---

## Demo Features (Working)

| Feature | Description |
|---------|-------------|
| Home, How It Works, Features, Pricing | Marketing pages with consistent design |
| Login / Signup | Simulated auth – any credentials enter the demo session |
| Editor Dashboard | List of sample + newly created projects |
| Upload Project | Form creates a new project (sample video attached) |
| Project Details | Full view with video player, badges, private link |
| Client Video Preview | Watermarked player + locked/unlocked state |
| Payment Status Demo | Toggle Pending / Verified / Failed / Refunded |
| Locked Download | Final download available only when status is Verified |
| Help & FAQ | Explains the demo |
| Terms & Privacy | Placeholders stating this is a demo |
| Responsive layout | Mobile, tablet, desktop |
| Design system | Buttons, cards, inputs, badges, alerts |

---

## Features That Still Require a Backend

| Capability | Why backend is needed |
|------------|------------------------|
| Real user accounts & sessions | Auth (JWT / sessions), password hashing |
| Actual video upload & storage | Object storage (S3, R2, GCS) + processing |
| Persistent watermarking | Server-side or edge transcoding / overlay |
| Real payment processing | Stripe / PayPal / etc. + webhooks |
| Secure signed download URLs | Time-limited, permission-checked links |
| Email notifications | Transactional email service |
| Database | Projects, users, payment history |
| Access control | Only the correct client can open a private link |
| Rate limiting & abuse protection | API gateway / WAF |
| Production security | HTTPS, CSP, encryption at rest, audit logs |

---

## Architecture Notes (for future expansion)

- **Frontend** is already structured with clear types, context, and reusable components.
- Replace `DemoContext` with API calls (React Query / SWR) once a backend exists.
- Suggested free/cheap backend options for early development:
  - **Supabase** (auth + Postgres + storage) – free tier available
  - **Firebase** (auth + Firestore + storage) – free tier
  - **Cloudflare R2** + **Workers** + **D1** – generous free tiers
  - **Local:** Express / Fastify + SQLite / Prisma for prototyping
- Payment providers (Stripe, etc.) have free test modes; live mode requires a paid account and compliance.
- Video CDN / encoding services (Mux, Cloudflare Stream, AWS MediaConvert) usually have usage-based pricing after free credits.

---

## Free Deployment Options & Limitations

| Platform | Notes |
|----------|-------|
| **Vercel** | Excellent for Vite/React. Free hobby tier. Custom domain optional. |
| **Netlify** | Similar free tier. Easy drag-and-drop or Git deploy. |
| **Cloudflare Pages** | Fast, free, good for static + SPA. |
| **GitHub Pages** | Free but requires `base` config for client-side routing. |

**Limitations of free static hosting for this demo:**
- Client-side only – no server secrets or real file storage.
- Private links are just routes; anyone with the URL can open them.
- State resets on refresh (except what you create in the same session).

For a real product you will need a backend + storage + payment provider.

---

## Design System

- **Background:** dark navy / charcoal (`#0a0f1c`, `#111827`)
- **Accent:** electric blue (`#3b82f6`)
- **Text:** white / gray-300 / gray-400
- **Components:** `.btn-primary`, `.btn-secondary`, `.card`, `.input`, `.badge-*`
- Typography: Inter
- Consistent spacing, rounded cards, subtle borders

---

## Disclaimer

This project is a **demonstration only**. It does not provide production-grade security, payment processing, or video delivery. Do not use it to handle real client work or payments.

---

Built as a professional SaaS UI/UX and architecture reference for EditLock.
