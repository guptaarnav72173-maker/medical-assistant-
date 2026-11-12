# 🏥 Healthcare Appointment Scheduling Portal & Chatbot

An AI-powered appointment scheduling assistant with a dedicated **Patient Portal**, built with **React**, **Node.js/Express**, and the **Google Gemini API** (`gemini-3.1-flash-lite`).

---

## ✨ Features

### 1. 🔐 Patient Authentication
- Secure Login & Registration for patients.
- **⚡ 1-Click Demo Login** buttons on the login screen for instant testing:
  - **John Doe** (`john@example.com` / `password123`)
  - **Ayesha Khan** (`ayesha@example.com` / `password123`)

### 2. 📋 Patient Health Portal
- **Major Profile Details**: Full Name, Email, Primary Phone, Age, Date of Birth, Gender, Blood Group, Residential Address, Emergency Contact.
- **🩺 Common Symptoms / Current Concerns**: Live interactive list of frequent or ongoing symptoms. Patients can dynamically add or remove symptoms.
- **📋 Past Medical History & Surgeries**: Chronological conditions, previous surgeries, and hospitalizations (with on-the-fly additions).
- **⚠️ Known Allergies & Active Medications**: Safety warnings, active prescriptions, and drug sensitivities.

### 3. 💬 AI Healthcare Assistant
- Adheres to medical compliance guidelines (never diagnoses or prescribes; advises emergency care for life-threatening symptoms).
- Routes concerns to 8 exact medical specialties:
  - `orthopedic`, `gynecologist`, `general physician`, `dentist`, `dermatologist`, `cardiologist`, `therapist`, `pediatrician`
- Automatically loads the logged-in patient's profile into context.

### 4. 📅 My Appointments
- Overview of all confirmed bookings.
- Doctor details, specialty, date, and appointment time in `Asia/Karachi` timezone (`+05:00`).
- Direct **Add to Google Calendar** link generation.

---

## 📁 Project Structure

```
hack/
├── README.md
├── package.json
├── client/                               # React + Vite Frontend
│   └── src/
│       ├── App.jsx / App.css             # Main view switcher (Portal, Chat, Appointments)
│       ├── components/
│       │   ├── LoginPage.jsx / .css      # Sign in, register & 1-click demo accounts
│       │   ├── PatientPortal.jsx / .css  # Patient details, symptoms & medical history
│       │   ├── AppointmentsList.jsx / .css # Scheduled doctor appointments
│       │   ├── Header.jsx / .css         # Navigation bar & user logout
│       │   ├── ChatWindow.jsx / .css     # Auto-scrolling chat history
│       │   ├── MessageBubble.jsx / .css  # Markdown bubbles with calendar links
│       │   └── InputBar.jsx / .css       # Text input with Enter to send
│       └── services/
│           └── api.js                    # Auth, patient data & chat API service
└── server/                               # Node.js + Express Backend
    ├── index.js                          # Express routes (auth, patient, chat, health)
    ├── data/
    │   ├── patients.js                   # Patient database (demographics, history, symptoms)
    │   ├── doctors.js                    # 16 doctors across 8 specialties + slot schedules
    │   └── bookings.js                   # Appointments database
    ├── services/
    │   └── geminiService.js              # Gemini 3.1 Flash Lite function-calling loop
    ├── tools/
    │   └── schedulingTools.js            # 4 scheduling tools (find, check, book, cancel)
    └── prompts/
        └── systemPrompt.js               # Clinical safety & specialty routing prompt
```

---

## 🚀 Running the App

### 1. Backend Server
```powershell
cd c:\Users\Arnav\Downloads\hack\server
npm start
```
*Listens on `http://localhost:3001`.*

### 2. Frontend Client
```powershell
cd c:\Users\Arnav\Downloads\hack\client
npm run dev
```
*Open `http://localhost:5173/` in your browser.*
