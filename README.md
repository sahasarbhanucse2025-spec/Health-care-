# 🩺 HealthCare+ — AI-Powered Personal Health Monitoring

> A modern healthcare web application that combines health monitoring, medication management, symptom tracking, and AI-powered symptom triage in one intuitive dashboard.

![Next.js](https://img.shields.io/badge/Next.js-15.3.8-black?style=for-the-badge&logo=next.js)
![React](https://img.shields.io/badge/React-18.3.1-61DAFB?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4.17-06B6D4?style=for-the-badge&logo=tailwindcss)
![Genkit](https://img.shields.io/badge/Genkit-AI-FF6F00?style=for-the-badge)
![Gemini](https://img.shields.io/badge/Gemini-2.5_Flash-8E75B2?style=for-the-badge)

---

## 🌟 Overview

**HealthCare+** is an AI-assisted personal health monitoring platform designed to provide users with a simple and interactive way to manage everyday health information.

The application brings multiple healthcare utilities together into a single dashboard:

- 🩺 AI-powered symptom triage
- 💊 Medication scheduling and management
- 📋 Symptom logging and history
- 📊 Personal health dashboard
- 💡 Personalized health tips
- 👤 User login and registration interface
- 📱 Responsive and modern UI

The goal is to make health information easier to organize while demonstrating how modern web technologies and generative AI can be combined to build healthcare-focused applications.

---

## ✨ Key Features

### 🤖 AI Symptom Triage

Users can enter a detailed description of their symptoms and receive an AI-generated assessment.

The AI workflow provides:

- **Risk score** from 0 to 1
- Suggested next step:
  - Self-care
  - Consult nurse
  - Urgent care
- A short rationale explaining the assessment

The AI functionality is implemented using **Genkit** with **Google Gemini 2.5 Flash**.

> ⚠️ This feature is intended for educational and demonstration purposes and is not a substitute for professional medical diagnosis or emergency care.

---

### 💊 Medication Management

Users can create medication schedules by entering:

- Medication name
- Dosage
- Frequency
- Time

Users can also remove medications from their current schedule.

---

### 📝 Symptom Tracking

The application allows users to log symptoms and view previously recorded entries.

The symptom history interface displays:

- Date
- Symptoms
- Severity
- AI suggestion
- Risk score

This provides a simple way to review previous health-related entries.

---

### 📊 Health Dashboard

The dashboard provides a centralized overview of the user's health information, including:

- Upcoming medication reminders
- Active medication schedules
- Symptom logging access
- Personalized health information

The interface is designed to keep important health information accessible from one place.

---

### 💡 Personalized Health Tips

The application includes an AI-powered workflow designed to generate personalized health tips based on:

- Logged symptoms
- Risk assessment
- User health context

---

## 🧠 AI Architecture

The AI layer is built using **Genkit** and Google's generative AI integration.

### AI Model

```text
Google Gemini 2.5 Flash
        ↓
      Genkit
        ↓
 ┌─────────────────────────┐
 │ AI Symptom Triage       │
 │ Personalized Tips       │
 └─────────────────────────┘
        ↓
   Next.js Application
````

### AI Workflows

```text
src/ai/
├── genkit.ts
├── dev.ts
└── flows/
    ├── ai-symptom-triage.ts
    └── personalized-health-tips.ts
```

---

## 🛠️ Tech Stack

### Frontend

* **Next.js 15.3.8**
* **React 18**
* **TypeScript**
* **Tailwind CSS**
* **shadcn/ui / Radix UI**
* **Lucide React**
* **Recharts**

### AI

* **Genkit**
* **Google AI**
* **Gemini 2.5 Flash**

### Form & Validation

* **React Hook Form**
* **Zod**

### Utilities

* **date-fns**
* **Firebase**
* **PostCSS**

---

## 📁 Project Structure

```text
Health-care-/
│
├── src/
│   ├── ai/
│   │   ├── dev.ts
│   │   ├── genkit.ts
│   │   └── flows/
│   │       ├── ai-symptom-triage.ts
│   │       └── personalized-health-tips.ts
│   │
│   ├── app/
│   │   ├── dashboard/
│   │   │   ├── medications/
│   │   │   ├── symptoms/
│   │   │   ├── layout.tsx
│   │   │   └── page.tsx
│   │   │
│   │   ├── signup/
│   │   │   └── page.tsx
│   │   │
│   │   ├── globals.css
│   │   ├── layout.tsx
│   │   └── page.tsx
│   │
│   ├── components/
│   │   ├── dashboard-header.tsx
│   │   ├── dashboard-nav.tsx
│   │   ├── logo.tsx
│   │   ├── symptom-logger.tsx
│   │   └── ui/
│   │
│   ├── hooks/
│   └── lib/
│       ├── actions.ts
│       ├── data.ts
│       ├── types.ts
│       └── utils.ts
│
├── package.json
├── package-lock.json
├── next.config.ts
├── tailwind.config.ts
├── tsconfig.json
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/sahasarbhanucse2025-spec/Health-care-.git
```

### 2. Open the project

```bash
cd Health-care-
```

### 3. Install dependencies

```bash
npm install
```

### 4. Run the development server

```bash
npm run dev
```

The application runs on:

```text
http://localhost:9002
```

### 5. Build for production

```bash
npm run build
```

### 6. Start the production server

```bash
npm start
```

---

## 🔐 Environment Variables

The AI functionality uses Google's AI services through Genkit.

Configure the required Google AI credentials in your local environment before using the AI features.

Example:

```env
GOOGLE_GENAI_API_KEY=your_api_key_here
```

> Never commit API keys, credentials, or `.env` files to GitHub.

---

## 🖥️ Application Flow

```text
             ┌──────────────┐
             │ Login / Sign │
             │     Up       │
             └──────┬───────┘
                    │
                    ▼
          ┌────────────────────┐
          │ Health Dashboard   │
          └─────────┬──────────┘
                    │
       ┌────────────┼────────────┐
       ▼            ▼            ▼
  Medications   Symptoms      Health Tips
       │            │
       │            ▼
       │      AI Symptom Triage
       │            │
       │     ┌──────┴──────┐
       │     ▼             ▼
       │  Risk Score   Next Step
       │
       ▼
 Medication Schedule
```

---

## 🎯 Project Goals

This project demonstrates how modern technologies can be used to build a healthcare-focused web application with:

* User-friendly health dashboards
* AI-assisted symptom analysis
* Medication organization
* Symptom history tracking
* Personalized health guidance
* Modern responsive UI design

---

## 🔮 Future Improvements

Planned improvements can include:

* 🔐 Real authentication and secure user accounts
* ☁️ Cloud database integration
* 📈 Persistent health analytics
* 🔔 Real-time medication notifications
* 🧑‍⚕️ Doctor / healthcare-provider integration
* 📱 Mobile application
* 🌐 Multi-language support
* 📊 Advanced health analytics
* 🗂️ Medical record management
* 🔒 Stronger privacy and security controls

---

## ⚠️ Medical Disclaimer

HealthCare+ is a **software project and educational prototype**.

AI-generated symptom assessments and health suggestions should not be treated as medical diagnosis, prescriptions, or professional medical advice.

For medical emergencies or serious symptoms, consult a qualified healthcare professional or appropriate emergency service.

---

## 👨‍💻 Project

**HealthCare+ — AI-Powered Personal Health Monitoring**

Built with:

**Next.js + React + TypeScript + Tailwind CSS + Genkit + Google Gemini**

---

## 📄 License
