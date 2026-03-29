# Voice-AI: Automated Patient Outreach System

An intelligent healthcare automation system built with **FastAPI**, **Twilio**, and **Supabase**.  
This system monitors patient records and automatically decides whether to initiate a **voice call** or send an **SMS reminder** based on patient age and symptom severity.

---

## 🚀 Features

### 🧠 Intelligent Triaging
- Detects critical symptoms like **chest pain**, **breathlessness**, and **dizziness**
- Automatically triggers **emergency voice calls** for high-risk patients

### 🌐 Multilingual IVR System
- Interactive Voice Response (IVR) in **Hindi (hi-IN)**
- Conversational voice flow for patient interaction

### 🎤 Speech-to-Text Integration
- Captures patient responses during calls
- Processes and logs speech data automatically

### 🗄️ Database Driven
- Uses **Supabase (PostgreSQL)** for patient records
- Logs all interactions and responses

### 📩 Automated SMS System
- Sends **medication reminders** for non-critical cases

---

## 🛠️ Tech Stack

- **Backend Framework:** FastAPI (Python)
- **Communication:** Twilio API (Voice & SMS)
- **Database:** Supabase (PostgreSQL)
- **Environment Management:** python-dotenv
- **Tunneling:** ngrok

---

## 📂 Project Structure
Voice-AI/
├── main.py # FastAPI routes and core business logic
├── call.py # Twilio voice call configuration
├── sms.py # Twilio SMS messaging configuration
├── .env # API keys and environment variables
└── README.md


---

## ⚙️ Setup & Installation

### 1. Prerequisites
- Python 3.8+
- Twilio account (SID, Auth Token, Phone Number)
- Supabase project (URL and API Key)
- ngrok installed

---

### 2. Installation

```bash
git clone https://github.com/your-username/Voice-AI.git
cd Voice-AI
pip install fastapi uvicorn requests twilio python-dotenv
