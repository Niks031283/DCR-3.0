# 📋 Daily Call Reporting System

> A production-ready, mobile-first Progressive Web App for pharmaceutical sales representatives to log and track daily doctor/chemist visits.

![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react)
![Vite](https://img.shields.io/badge/Vite-5-646CFF?style=flat-square&logo=vite)
![TailwindCSS](https://img.shields.io/badge/Tailwind-3-38BDF8?style=flat-square&logo=tailwindcss)
![Netlify](https://img.shields.io/badge/Netlify-Functions-00C7B7?style=flat-square&logo=netlify)
![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-3ECF8E?style=flat-square&logo=supabase)
![PWA](https://img.shields.io/badge/PWA-Ready-5A0FC8?style=flat-square&logo=pwa)

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 📱 Mobile-First UI | Optimized for Android Chrome with large touch targets |
| 🔐 JWT Authentication | Secure login with persistent sessions |
| 📝 Call Entry Form | Complete call logging with 13 fields |
| 📊 Dashboard | Real-time stats — calls, doctors, chemists, orders |
| 📅 Call History | Filter by date, doctor, city, product |
| 📈 Reports & Charts | Daily/monthly reports with Chart.js visualizations |
| 👑 Admin Panel | View all users' calls, export Excel & PDF |
| 📴 Offline Support | IndexedDB storage, auto-sync when online |
| ⚡ PWA | Installable on Android like a native app |
| 🚀 Serverless | Netlify Functions — no server management |

---

## 🔑 Default Login

| Field | Value |
|-------|-------|
| Username | `Niks0312` |
| Password | `Admin@123` |
| Role | Admin |

---

## 🛠 Tech Stack

### Frontend
- **React 18** + **Vite 5** — fast HMR development
- **Tailwind CSS 3** — utility-first styling
- **React Router v6** — client-side routing
- **Chart.js + react-chartjs-2** — analytics charts
- **Axios** — HTTP client with interceptors
- **date-fns** — date formatting/manipulation
- **lucide-react** — beautiful icons
- **react-hot-toast** — elegant notifications
- **vite-plugin-pwa** — PWA manifest + service worker

### Backend
- **Netlify Functions** (Node.js) — serverless APIs
- **jsonwebtoken** — JWT authentication
- **bcryptjs** — password hashing
- **ExcelJS** — Excel export
- **PDFKit** — PDF export

### Database
- **Supabase** (PostgreSQL) — managed cloud database
- Row-Level Security enabled
- Indexed for fast queries

---

## 📁 Project Structure

```
daily-call-reporting/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── BottomNav.jsx       # 5-tab sticky navigation
│   │   │   ├── CallCard.jsx        # Call display card with expand
│   │   │   ├── FormField.jsx       # Reusable form inputs + toggle
│   │   │   ├── LoadingScreen.jsx   # Splash loading screen
│   │   │   ├── OnlineStatus.jsx    # Online/offline banner
│   │   │   ├── PageHeader.jsx      # Page title + back button
│   │   │   ├── StatCard.jsx        # Dashboard stat cards
│   │   │   └── EmptyState.jsx      # Empty state UI
│   │   ├── pages/
│   │   │   ├── LoginPage.jsx       # Auth screen
│   │   │   ├── DashboardPage.jsx   # Main dashboard
│   │   │   ├── AddCallPage.jsx     # New call form
│   │   │   ├── EditCallPage.jsx    # Edit existing call
│   │   │   ├── CallListPage.jsx    # Today's calls
│   │   │   ├── CallHistoryPage.jsx # Filtered history
│   │   │   ├── ReportsPage.jsx     # Charts & analytics
│   │   │   ├── ProfilePage.jsx     # User profile + logout
│   │   │   └── AdminPage.jsx       # Admin panel + exports
│   │   ├── services/
│   │   │   ├── api.js              # Axios API client
│   │   │   └── offline.js          # IndexedDB offline storage
│   │   ├── context/
│   │   │   └── AuthContext.jsx     # Auth state + JWT
│   │   ├── hooks/
│   │   │   └── useCallForm.js      # Form state + validation
│   │   └── styles/
│   │       └── globals.css         # Tailwind + custom CSS
│   ├── public/
│   │   └── manifest.json
│   ├── vite.config.js
│   ├── tailwind.config.js
│   └── package.json
│
├── backend/
│   └── netlify/
│       └── functions/
│           ├── _shared/utils.js    # Auth, DB, response helpers
│           ├── auth-login.js
│           ├── auth-verify.js
│           ├── calls-create.js
│           ├── calls-update.js
│           ├── calls-delete.js
│           ├── calls-today.js
│           ├── calls-list.js
│           ├── calls-detail.js
│           ├── calls-dashboard.js
│           ├── reports-daily.js
│           ├── reports-monthly.js
│           ├── admin-calls.js
│           ├── admin-export-excel.js
│           └── admin-export-pdf.js
│
├── database/
│   ├── schema.sql
│   └── setup-guide.md
│
├── docs/
│   ├── installation.md
│   ├── deployment.md
│   └── api-documentation.md
│
├── netlify.toml
├── package.json
└── .env.example
```

---

## 🚀 Quick Start

### 1. Clone
```bash
git clone https://github.com/YOUR_USERNAME/daily-call-reporting.git
cd daily-call-reporting
```

### 2. Install dependencies
```bash
npm install
cd frontend && npm install && cd ..
cd backend && npm install && cd ..
```

### 3. Configure environment
```bash
cp .env.example .env
# Fill in your Supabase credentials and JWT_SECRET
```

### 4. Set up database
- Follow [`/database/setup-guide.md`](./database/setup-guide.md)
- Run `schema.sql` in Supabase SQL Editor

### 5. Run locally
```bash
npm install -g netlify-cli
netlify dev
# Open http://localhost:8888
```

---

## ☁️ Deploy to Netlify

1. Push to GitHub
2. Connect repo in [Netlify Dashboard](https://app.netlify.com)
3. Set build settings:
   - Base: `frontend`
   - Build: `npm run build`
   - Publish: `frontend/dist`
   - Functions: `backend/netlify/functions`
4. Add environment variables (see `.env.example`)
5. Deploy!

Full guide: [`/docs/deployment.md`](./docs/deployment.md)

---

## 📱 Install as Android App (PWA)

1. Open your Netlify URL in **Chrome on Android**
2. Tap the **⋮ menu → Add to Home Screen**
3. Tap **Install**
4. App icon appears on your home screen
5. Works offline with auto-sync!

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/auth-login` | Login |
| GET | `/auth-verify` | Verify token |
| POST | `/calls-create` | New call |
| GET | `/calls-today` | Today's calls |
| GET | `/calls-list` | Paginated history |
| GET | `/calls-detail` | Single call |
| PUT | `/calls-update` | Edit call |
| DELETE | `/calls-delete` | Delete call |
| GET | `/calls-dashboard` | Dashboard stats |
| GET | `/reports-daily` | Daily report |
| GET | `/reports-monthly` | Monthly report |
| GET | `/admin-calls` | All calls (admin) |
| GET | `/admin-export-excel` | Excel export |
| GET | `/admin-export-pdf` | PDF export |

---

## 🔒 Security

- JWT tokens with 7-day expiry
- bcrypt password hashing
- Row-Level Security in Supabase
- Service role key only used server-side
- CORS headers on all functions
- Input sanitization and validation
- Admin-only routes enforced server-side

---

## 📄 License

MIT — Free to use and modify.

---

## 🤝 Contributing

Pull requests welcome! For major changes, open an issue first.

---

*Built with ❤️ for pharmaceutical sales professionals*
