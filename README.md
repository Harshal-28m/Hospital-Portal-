# PulseCare — Modern Smart Hospital Portal

A comprehensive, production-grade Hospital Management Web Application built with **React JS**, **Vite**, **Tailwind CSS v4**, **React Router DOM**, **Recharts**, and **Lucide React**.

PulseCare delivers an integrated healthcare experience with dedicated public workflows and three role-specific portals: **Hospital Administrator**, **Attending Doctors**, and **Registered Patients**.

---

## 🌟 Key Portals & Features

### 1. Public Healthcare Website
- **Hero Section**: High-impact medical headline, live ward capacity telemetry badge, trust indicators, quick appointment booking CTA.
- **24/7 Emergency Trauma Banner**: Real-time ambulance dispatch contact, hotline direct dialing (`555-911-0000`), and quick bed tracker link.
- **Medical Departments**: 8 specialized clinical wings (Cardiology, Neurology, Orthopedics, Pediatrics, Emergency, Oncology, Dermatology, Radiology) with floor location, staff count, and direct booking links.
- **Specialist Directory**: Board-certified physician cards with ratings, consultation fees, specialties, and next available appointment slots.
- **Clinical Facilities**: Robotic surgery, certified pathology labs, intensive care units, and executive wellness packages.
- **Live Bed Availability**: Ward-by-ward breakdown (ICU, CCU, General Ward, Pediatric, Executive Suites) with real-time status badges (Available, Occupied, Maintenance).
- **Patient Testimonials & Reviews**: Verified patient healing stories with star ratings.
- **Hospital Contact & Extensions**: Department direct lines, campus directions, and interactive message dispatch.

### 2. Multi-Role Authentication
- **1-Click Quick Demo Login**:
  - 👑 **Admin**: Dr. Arvind Deshmukh (Hospital Director & Medical Superintendent)
  - 🩺 **Doctor**: Dr. Priya Sharma (Senior Interventional Cardiologist)
  - 👤 **Patient**: Aarav Patel (Registered Patient)
- **Role-Based Protected Navigation**: Guards `/admin/*`, `/doctor/*`, and `/patient/*` routes.
- **Patient Self-Registration**: Collects name, email, phone, DOB, biological gender, blood group, drug allergies, pre-existing conditions, emergency contacts, and HIPAA consent.

### 3. Admin Operations Center (`/admin`)
- **Executive KPIs**: Total Patients, Specialist Faculty, Scheduled Appointments, Bed Occupancy Percentage.
- **Visual Analytics (Recharts)**:
  - Weekly Consultation & Trauma Intake Trends (Area chart with smooth gradients)
  - Bed Allocation Distribution (Interactive Donut chart)
  - Departmental staffing & bed capacity (Bar chart)
- **Recent Appointments Table**: Real-time status update dropdowns (`Confirmed`, `In-Progress`, `Completed`, `Cancelled`).
- **Doctor Directory Management (`/admin/doctors`)**: Full CRUD (Add Doctor, Edit Doctor Profile, Remove Doctor with confirmation modal, toggle Active / On Leave).
- **Patient Health Records (`/admin/patients`)**: Searchable registry, blood group filters, and comprehensive **Patient Chart Modal** (allergies, chronic conditions, appointment history, prescriptions).
- **Master Appointment Schedule (`/admin/appointments`)**: Multi-filter controls, pagination, clinical note viewing, and cancellation with reason logging.
- **Department Infrastructure (`/admin/departments`)**: Add and manage hospital clinical departments.
- **Bed & Ward Monitor (`/admin/beds`)**: Allocate inpatient beds, discharge patients, and toggle bio-sanitization states.
- **Pharmacy Inventory (`/admin/inventory`)**: Stock level tracking, reorder thresholds, low-stock warning banners, quick `+50 / -10` unit adjustments, and new batch entry.
- **Billing & Revenue Management (`/admin/billing`)**: Gross revenue metrics, itemized invoices, settlement reconciliation, and official receipt printing.

### 4. Doctor Clinical Workstation (`/doctor`)
- **Physician Profile Card**: Credentials, clinic room suite, patient rating, and daily consult queue.
- **Today's Queue**: Call In (`Start Consultation`), Finish (`Mark Completed`), and inspect symptoms.
- **Clinical Notes**: Add physician observations, vitals, and findings directly to patient records.
- **Electronic Prescriptions (e-Rx) (`/doctor/prescriptions`)**: Multi-drug prescription builder (name, dosage, frequency, duration, instructions, general advice) with official printable prescription slips.
- **Consultation Schedule (`/doctor/schedule`)**: Toggle weekly consultation days, customize morning/afternoon slots, and set consultation fees.

### 5. Patient Health Portal (`/patient`)
- **Health Overview**: Patient profile, next appointment countdown banner, recent lab test results, and outstanding balances.
- **My Appointments (`/patient/appointments`)**: Tabbed breakdown (Upcoming, Past Encounters, Cancelled), cancel visits with zero penalty, and read doctor clinical notes.
- **Digital Prescriptions (`/patient/prescriptions`)**: View e-Rx orders with dosage timings and print official slips.
- **Diagnostic Reports (`/patient/reports`)**: Lab findings (ECG, Lipid Panel, Radiography) with physician interpretation.
- **Medical Bills & Statements (`/patient/billing`)**: Itemized billing breakdown, insurance benefit deductions, and 256-bit encrypted **Pay Online** modal.
- **Health Profile Settings (`/patient/profile`)**: Manage demographics, update allergies and chronic conditions, change password, and toggle Dark Mode.

### 6. Robust Appointment Booking (`/book-appointment`)
- Step-by-step specialist selection and auto-filling from query params (e.g. `?doctor=doc-1`).
- Date picker with past date restrictions.
- Live slot selector showing doctor's consultation windows.
- **Duplicate Booking Prevention**: Verifies if the selected doctor already has an active appointment at that date and time; rejects conflicts with clear feedback.
- **Confirmed Appointment Slip**: Reference Token ID, details, patient instructions, and print capability.

---

## 🛠️ Technology Stack

| Layer | Technology |
|---|---|
| **Framework** | React 19 + Vite 8 |
| **Routing** | React Router DOM v7 |
| **Styling** | Tailwind CSS v4 + Plus Jakarta Sans & Outfit Fonts |
| **Icons** | Lucide React |
| **Charts** | Recharts (Area, Bar, Pie charts) |
| **Animation** | Smooth CSS transitions & pulse indicators |
| **State & Storage** | React Context (`AuthContext`, `HospitalContext`, `ToastContext`, `ThemeContext`) + LocalStorage persistence |
| **Backend Integration Layer** | Centralized Service Layer (`src/services/api.js`) prepared for Spring Boot 3 + MySQL 8 |

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v18 or higher recommended)
- npm or yarn

### 1. Install Dependencies
```bash
npm install
```

### 2. Run the Development Server
```bash
npm run dev
```
The application will launch locally at **`http://localhost:5173/`**.

### 3. Build for Production
```bash
npm run build
```

---

## 🔑 Demo Access Accounts

Use the **1-Click Demo Buttons** on the Login Page (`/login`) or inside the dashboard sidebar for instant access:

| Role | Name | Email | Password |
|---|---|---|---|
| **Admin** | Dr. Arvind Deshmukh | `admin@pulsecare.health` | `AdminPulse#2026` |
| **Doctor** | Dr. Priya Sharma | `priya.sharma@pulsecare.health` | `DoctorPulse#2026` |
| **Patient** | Aarav Patel | `aarav.patel@example.com` | `PatientPulse#2026` |

---

## 📂 Project Structure

```
Hospital Portal/
├── docs/
│   └── BACKEND_SPRING_BOOT_INTEGRATION.md  # Spring Boot & MySQL DDL integration guide
├── src/
│   ├── assets/                             # SVG icons & static assets
│   ├── components/
│   │   ├── common/                         # Navbar, Footer, Sidebar, Topbar, Modal, Badge, Toast, StatCard
│   │   └── public/                         # Hero, DepartmentCard, DoctorCard, Services, Testimonials, EmergencyBanner
│   ├── context/
│   │   ├── AuthContext.jsx                 # Role auth, demo quick logins, patient registration
│   │   ├── HospitalContext.jsx             # Appointments, doctors, beds, inventory, billing reactive store
│   │   ├── ThemeContext.jsx                # Light / Dark mode switcher
│   │   └── ToastContext.jsx                # Toast alerts (success, error, warning, info)
│   ├── data/
│   │   └── mockData.js                     # Realistic medical dataset (doctors, beds, inventory, reports)
│   ├── hooks/                              # useAuth, useHospital, useToast, useTheme
│   ├── layouts/
│   │   ├── PublicLayout.jsx                # Sticky navbar + outlet + footer
│   │   └── DashboardLayout.jsx             # Role protection + sidebar + topbar
│   ├── pages/
│   │   ├── public/                         # Home, Doctors, Departments, Bed Tracker, Contact, Booking
│   │   ├── auth/                           # Login, Patient Registration
│   │   ├── admin/                          # Admin Dashboard, Doctors CRUD, Patients, Appointments, Inventory, Beds, Billing
│   │   ├── doctor/                         # Doctor Dashboard, Queue, Patients, Prescriptions, Schedule
│   │   ├── patient/                        # Patient Dashboard, Appointments, Prescriptions, Reports, Billing, Profile
│   │   └── NotFoundPage.jsx                # 404 handler
│   ├── services/
│   │   └── api.js                          # Centralized API service layer
│   ├── App.jsx                             # Complete router configuration
│   ├── index.css                           # Tailwind CSS v4 & custom healthcare design tokens
│   └── main.jsx
├── package.json
└── vite.config.js
```
