# 🇱🇰 Athalaga.lk - Hyper-Local Verified Tradesmen Platform

A zero-commission digital directory and Progressive Web Application (PWA) built specifically for Sri Lanka, connecting local households and businesses with verified tradesmen (plumbers, electricians, repair specialists, and daily helpers) directly via WhatsApp.

---

## 📌 Executive Summary

* **Pilot Region:** Puttalam, Sri Lanka (Region-locked pilot with structured scalability for other districts).
* **Core Philosophy:** Zero middleman fees, 100% direct client-worker coordination via WhatsApp/Direct Call, and identity verification via Government NIC checks.
* **Security Model:** Strict privacy compliance (Personal Data Protection Act - PDPA). NIC data and direct personal numbers are excluded from client bundles; clients authenticate via Firebase Phone OTP.

---

## 🚀 Key Features

* **3-Second Rule UX & Typewriter Hero:** High-contrast value proposition with dynamic local service phrase rotation.
* **Smart Live Autocomplete Search:** Instant floating preview results by tradesman name, category, or keyword with direct navigation.
* **Multi-Channel Contact Flexibility:** Dynamic per-worker communication options (`whatsapp_only`, `call_only`, or `both`) driven by JSON configuration.
* **Verified Client Phone Auth:** Firebase Phone OTP authentication workflow with mandatory legal Terms & Conditions acceptance.
* **Interaction Logging:** Authenticated client clicks on WhatsApp or Direct Call triggers are logged securely to Firebase Firestore (`interactions` collection) for metrics.
* **Full Tri-Lingual (i18n) Support:** Seamless real-time translation switching across English (`en`), Sinhala (`si`), and Tamil (`ta`).
* **Authentic Worker Ratings:** Transparent, authenticated 5-star review submission system preventing spam reviews.
* **PWA & Offline Capability:** Service worker caching, mobile install prompts, and standalone mobile app experience (`/images/webappicon.jpeg`).

---

## 🛠️ Tech Stack & Dependencies

* **Frontend Framework:** React 19 (`react`, `react-dom`)
* **Bundler & Build Tool:** Vite 7
* **CSS Framework:** Tailwind CSS v4 (`@tailwindcss/vite`, `@tailwindcss/node`)
* **Language & Types:** TypeScript 5.9 (`strict` mode enabled)
* **Backend & Auth:** Firebase v12 (Firebase Auth Phone OTP, Cloud Firestore)
* **Icons & UI:** Lucide React (`lucide-react`)
* **Utilities:** `tailwind-merge`, `clsx`, `@emailjs/browser`

---

## 📂 Project Structure

```text
athalaga-landing-page/
├── public/
│   ├── data/
│   │   ├── workers.json         # Main worker repository (JSON backend)
│   │   └── site-config.json      # Platform settings & region configurations
│   ├── images/                  # Static assets & WebApp icons
│   ├── manifest.json            # PWA manifest
│   └── sw.js                    # Service worker
├── src/
│   ├── components/
│   │   ├── Hero.tsx             # Background carousel, typewriter & search
│   │   ├── Categories.tsx       # 5-column category grid
│   │   ├── Services.tsx         # 3-column worker cards & "More" action card
│   │   ├── HowItWorks.tsx       # 3-step process cards
│   │   ├── BecomeWorker.tsx     # Admin onboarding trigger
│   │   ├── Navbar.tsx           # Desktop top bar
│   │   ├── BottomNav.tsx        # Mobile floating navigation & language drawer
│   │   ├── LoginModal.tsx       # Firebase Phone OTP modal
│   │   └── Footer.tsx           # Compact footer & PWA prompt
│   ├── pages/
│   │   ├── FindWorkers.tsx      # Comprehensive directory page
│   │   ├── WorkerProfilePage.tsx# Dedicated profile & 5-star rating view
│   │   ├── HowItWorksPage.tsx   # Detailed process & FAQ
│   │   ├── Contact.tsx          # Support & direct feedback
│   │   ├── AboutUs.tsx          # Platform mission
│   │   └── TermsConditions.tsx  # Legal disclaimers & 10 PDPA clauses
│   ├── i18n/
│   │   ├── translations.ts      # Multi-language dictionary (EN, SI, TA)
│   │   └── termsData.ts         # Terms clauses mapped in 3 languages
│   ├── utils/
│   │   ├── tracking.ts          # Firestore interaction logging
│   │   └── cn.ts                # Class merging utility
│   ├── App.tsx                  # Main application controller & routing
│   ├── firebase.ts              # Firebase client initialization
│   ├── data.ts                  # TypeScript models & data loaders
│   └── main.tsx                 # Root entry point
├── firestore.rules              # Firestore security rules
├── package.json
└── tsconfig.json

```

---

## ⚡ Getting Started (Local Development)

### 1. Prerequisites

* Node.js (v18 or higher recommended)
* npm or pnpm

### 2. Installation

Clone the repository and install dependencies:

```bash
git clone [https://github.com/Sithum628/athalaga-app.git](https://github.com/Sithum628/athalaga-app.git)
cd athalaga-app
npm install

```

### 3. Local Development Server

Start the local Vite development server:

```bash
npm run dev

```

Open your browser at `http://localhost:5173`.

### 4. Production Build & Verification

Check TypeScript types and verify zero errors before committing:

```bash
# Type check
npx tsc --noEmit

# Production bundle
npm run build

```

---

## ⚙️ Administration & Data Management

* **Adding or Updating Workers:** Open `public/data/workers.json` to edit or add worker entries.
* **Phone Formats:** Always use the standard format `+947XXXXXXXX` for WhatsApp and call configurations.
* **Contact Modes:** Choose between `"whatsapp_only"`, `"call_only"`, or `"both"`.

---

## 📄 License & Proprietary Notice

© 2026 Athalaga.lk. All rights reserved.

Proprietary codebase developed for Athalaga hyper-local service deployment in Sri Lanka.