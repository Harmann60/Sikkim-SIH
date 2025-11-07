# SIH 2025 – Sikkim [Monastry 360]


[![Built with React](https://img.shields.io/badge/React-18-61DAFB)](#) [![Vite](https://img.shields.io/badge/Vite-5-646CFF)](#) [![TailwindCSS](https://img.shields.io/badge/Tailwind-3-38B2AC)](#) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](#license)

---
## ✨ Key Features

* **Role-based portal:** Admin / Officer / Citizen / NGO / Tourist
* **Multilingual UI:** English + Nepali / Lepcha / Bhutia (i18n-ready)
* **Offline-first touches:** Caching for low-connectivity regions
* **Geo-aware modules:** Maps, ward-wise filters, route hints
* **Accessible by design:** Keyboard nav, high contrast, screen-reader labels (WCAG 2.1 AA)
* **Analytics dashboard:** KPIs relevant to the PS (e.g., ticket resolution time, requests by block)
* **Secure data handling:** JWT auth, input validation, rate limiting

## 🏗️ Architecture (High Level)

```
[Client: React+Vite+Tailwind]  <—>  [API Gateway / Backend (Node/Express or Flask)]  <—>  [DB (PostgreSQL/Firestore)]
                                   \—>  [Object Storage for files/images]
                                   \—>  [Map/Geo API (e.g., MapLibre/Leaflet)]
```

## 🛠️ Tech Stack

**Frontend:** React 18, Vite 5, Tailwind CSS, React Router, Zustand/Redux (choose one), Axios
**Backend (optional this repo or separate):** Node.js + Express (or Python Flask/FastAPI)
**Database:** PostgreSQL / Supabase / Firestore (pick one)
**Maps:** Leaflet / MapLibre + OpenStreetMap tiles
**CI/CD:** GitHub Actions
**Hosting:** Vercel / Netlify (FE), Render / Railway / Fly.io (BE)

---

## 📦 Getting Started

### Prerequisites

* Node.js ≥ 18
* pnpm (recommended) or npm/yarn
* (If using backend) PostgreSQL or your chosen DB running

### Setup (Frontend)

```bash
# 1) Clone
git clone https://github.com/<you>/<repo>.git
cd <repo>

# 2) Install
pnpm install

# 3) Configure environment
cp .env.example .env
# Fill values

# 4) Run dev
pnpm dev

# 5) Build & preview
pnpm build
pnpm preview
```

**.env.example**

```
VITE_API_BASE_URL=http://localhost:4000
VITE_MAP_TILES_URL=https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png
VITE_DEFAULT_LOCALE=en
```

### Optional Backend (Express skeleton)

```bash
# in /server
pnpm install
cp .env.example .env
pnpm dev
```

`.env.example`

```
PORT=4000
DATABASE_URL=postgres://user:pass@localhost:5432/sih_sikkim
JWT_SECRET=change_this
```

---

## 🧭 Core User Flows

1. **Citizen submits request/feedback** → Geo-tag + category → Track status
2. **Officer triage** → Assign → SLA-based reminders → Resolution
3. **Tourist info** → Points of interest, permits, emergency contacts, offline map hints
4. **Admin dashboard** → KPIs, heatmaps, export reports (CSV)

---

## 🔐 Security & Compliance

* Input validation on both FE/BE
* HTTPS everywhere, secure cookies, CSRF guards (if SSR)
* Role/permission matrix documented under `/docs/permissions.md`
* PII minimization; follow applicable Indian data protection guidelines

---

## 🌐 i18n & Accessibility

* i18next with locale JSON packs (`/src/locales`)
* Landmarks, ARIA labels, focus states, color contrast ≥ 4.5:1
* Keyboard-only and screen-reader tested components

---

## 📊 Analytics & Logging

* Lightweight privacy-friendly analytics (e.g., Plausible/Umami)
* Server logs with request IDs; error tracking (Sentry/Better Stack)

---

## 🧪 Testing

```bash
pnpm test           # unit tests (Vitest)
pnpm test:ui        # component tests (Testing Library)
pnpm lint           # ESLint
pnpm typecheck      # TS types
```

---

## 🚀 Deployment

* **Frontend:** Vercel/Netlify → set `VITE_*` env vars
* **Backend:** Render/Railway/Fly.io → set `DATABASE_URL`, `JWT_SECRET`
* **DB Migrations:** Prisma/Knex/Alembic (document commands here)

---

## 📁 Project Structure

```
/src
  /assets
  /components
  /features
  /hooks
  /layouts
  /pages
  /routes
  /store
  /styles
  /utils
---

## 📚 API (Sample)

```
GET  /api/v1/health
POST /api/v1/auth/login
POST /api/v1/requests
GET  /api/v1/requests?block=<id>&status=<open|closed>
PUT  /api/v1/requests/:id/assign
PUT  /api/v1/requests/:id/resolve
```

---

## 🗂️ Documentation

* `/docs/architecture.md`
* `/docs/api.md`
* `/docs/permissions.md`
* `/docs/deployment.md`

---

## 🧭 Roadmap (SIH-ready)

* [ ] MVP: Core flows + i18n + a11y pass
* [ ] Officer workflow + export
* [ ] Offline caching & PWA install
* [ ] Heatmap analytics
* [ ] SMS/WhatsApp notifications (DND-compliant)


---
---

## 🧩 Evaluation Mapping (Quick View)

* **Innovation:** `[how you’re novel]`
* **Feasibility:** `[infra, costs, maintainability]`
* **Scalability:** `[state rollout plan]`
* **Impact:** `[KPIs, beneficiaries in Sikkim]`
* **UI/UX & Accessibility:** `[WCAG steps taken]`
* **Security & Privacy:** `[controls in place]`

---

## 📝 License

MIT © 

