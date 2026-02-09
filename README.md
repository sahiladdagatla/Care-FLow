# CareFlow HMS

A role-based Hospital Management System frontend with animated UI, hard-coded login, role-restricted routing, advanced billing with keypad and invoice modals. Built with React and Vite.

## Hackathon Context

This project was built as a frontend-only prototype for a 2-hour hackathon. It demonstrates role-based access control, polished interaction design, and hospital-grade UI architecture — all without a backend.

## Problem Statement

Hospitals require efficient, role-separated interfaces for patients, doctors, nurses, and administrators. CareFlow HMS delivers a demo-ready frontend that showcases how each role interacts with a hospital system through clean, purpose-built dashboards.

## Features

### Login & Access Control
- Hard-coded role-based login (no passwords required)
- Role selector with user dropdown (Patient, Doctor, Nurse, Admin)
- Route guards — each role can only access its own dashboard
- Admin-exclusive billing access
- Animated login page with glassmorphism card

### Patient Portal
- Patient selector dropdown (switch between 7 patients)
- Profile card with avatar and detailed info
- Color-coded vitals (green/amber/red based on medical thresholds)
- Upcoming appointments table
- Prescribed medicines list
- Visit history timeline with dot connectors
- Staggered entrance animations

### Doctor Dashboard
- Doctor selector with 4 doctors
- Today's appointment schedule
- Clickable patient cards with active highlight
- Slide-in patient detail panel (vitals + prescription + history)
- Clinical notes — add and view with timestamps (local state)
- Active prescriptions overview

### Nurse Dashboard
- Stat cards (assigned patients, task progress, pending meds)
- Interactive task checklist with checkbox toggling
- Patient vitals monitoring with color-coded indicators
- Medication schedule with administered/pending status
- Ward assignments and shift overview tables

### Admin Dashboard
- Animated count-up KPI numbers (patients, doctors, nurses, revenue)
- Bed occupancy with animated progress bar
- Department directory table
- Full staff directory (doctors + nurses)
- Patient registry with status badges
- System status monitoring cards
- Direct link to billing module

### Billing & Cash Counter (Admin Only)
- Animated summary cards (total billed, paid, pending)
- Invoice list with search/filter and row selection
- Itemized bill with add/remove items
- Bill item catalog dropdown with 18 predefined items
- Physical POS-style numeric keypad for custom amounts
- Payment status toggle (mark as paid/unpaid)
- Beautiful invoice modal with print-ready layout
- Payment summary with grand totals

## UI/UX Highlights

- Calm teal/blue/neutral hospital color palette
- Smooth page transitions and staggered section entrance
- Floating background shapes with grain overlay
- Skeleton loaders and loading spinners
- Card hover micro-interactions with shadow transitions
- Scroll-based reveal animations
- POS-style keypad with press animations
- Invoice modal with scale-in/out animation
- Print-friendly invoice layout
- Role-colored badges and indicators throughout
- No flashy effects — premium, professional feel

## Tech Stack

- **React 19** — UI library (hooks only, no Redux)
- **Vite** — Build tool and dev server
- **React Router v7** — Client-side routing with route guards
- **Lucide React** — Icon library
- **JavaScript (ES6+)** — No TypeScript, no CSS-in-JS libraries
- **CSS** — Global styles + animations (no Tailwind, no frameworks)

## Folder Structure

```
src/
 ├─ components/
 │   ├─ Navbar.jsx       — Role-aware top navigation with logout
 │   ├─ Sidebar.jsx      — Section nav with role header
 │   ├─ Card.jsx         — Card + StatCard with hover animations
 │   ├─ Table.jsx        — Data table with row hover
 │   ├─ Badge.jsx        — Status badge (5 variants)
 │   ├─ Button.jsx       — Button with hover/press effects
 │   ├─ Modal.jsx        — Animated modal with overlay
 │   ├─ Invoice.jsx      — Print-ready invoice layout
 │   ├─ Keypad.jsx       — POS-style numeric keypad
 │   └─ Loader.jsx       — Skeleton / spinner loader
 ├─ pages/
 │   ├─ Login.jsx        — Role-based login with glassmorphism
 │   ├─ Patient.jsx      — Patient portal
 │   ├─ Doctor.jsx       — Doctor dashboard
 │   ├─ Nurse.jsx        — Nurse dashboard
 │   ├─ Admin.jsx        — Admin dashboard
 │   └─ Billing.jsx      — Billing with keypad + invoice modal
 ├─ data/
 │   └─ mockData.js      — 7 patients, 4 doctors, 3 nurses, billing
 ├─ styles/
 │   ├─ global.css       — Global styles and CSS variables
 │   └─ animations.css   — All keyframes and animation classes
 ├─ App.jsx              — Route guards and role-based routing
 └─ main.jsx             — Entry point
```

## How to Run

```bash
# Install dependencies
npm install

# Start development server
npm run dev
```

The app will be available at `http://localhost:5173`.

## Routes & Access

| Path       | Page                  | Access          |
|------------|-----------------------|-----------------|
| `/`        | Login                 | Public          |
| `/patient` | Patient Portal        | Patient only    |
| `/doctor`  | Doctor Dashboard      | Doctor only     |
| `/nurse`   | Nurse Dashboard       | Nurse only      |
| `/admin`   | Admin Dashboard       | Admin only      |
| `/billing` | Billing & Cash Counter| Admin only      |

Unauthorized route access redirects to the user's own dashboard.

## Mock Data

- **7 patients** with full profiles, vitals, medicines, appointments, and history
- **4 doctors** across Endocrinology, Orthopedics, Cardiology, and Pulmonology
- **3 nurses** with ward assignments and shift schedules
- **7 billing records** with itemized bills and payment status
- **18 billing catalog items** for dynamic bill creation

## Disclaimer

This is a **frontend-only demo** built for a hackathon. It uses mock data stored in JavaScript objects and does not connect to any backend, database, or external API. No real patient data is used. It is not intended for production healthcare use.
