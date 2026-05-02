# 🇺🇸 Citizenship Coach: AI-Powered Interview Prep

**Citizenship Coach** is an AI-driven mobile platform designed to help users master the U.S. Naturalization Civics Test. Beyond simple flashcards, it leverages **OpenAI Whisper (STT)** and **GPT-4o-mini** to provide an interactive experience where users can practice speaking and receive semantic feedback on their answers.

---

## 📱 Store Links & Demo
The application is available for testing and use on both major platforms:

* **Google Play Store:** https://play.google.com/store/apps/details?id=com.yourname.citizenshipcoach
* **Apple App Store:** https://apps.apple.com/us/app/us-citizenship-interview-prep/id6759361143

---

## ✨ Key Features

### 1. Mobile Application (React Native / Expo)
* **Comprehensive Question Bank:** Includes full 2008 & 2025 USCIS Civics Test sets.
* **Intelligent Learning Modes:**
    * **Practice Mode:** Instant AI feedback on speech and accuracy.
    * **Mock Test Mode:** Simulates the actual interview environment.
    * **Review Mode:** Focused study on bookmarks and frequently missed questions.
* **Voice-First Interface:** Hands-free practice using high-quality voice recording and transcription.
* **Integrated TTS:** Native English Text-to-Speech for all questions to improve listening comprehension.

### 2. Backend Services (FastAPI + AI)
* **Semantic Evaluation Engine:** Unlike keyword matching, our AI evaluates the *meaning* of an answer, allowing for natural variations, paraphrasing, and minor grammatical or pronunciation slips.
* **Advanced Audio Pipeline:** * **Whisper STT:** High-accuracy transcription of user voice recordings.
    * **OpenAI TTS:** Natural voice synthesis for an immersive interview experience.
* **Multilingual Data Support:** Serves dynamic English and Korean question sets via a robust REST API.

---

## 🏗️ System Architecture

```text
CITIZENSHIP-PROJECT/
├── citizenship-coach/         # Frontend: React Native (Expo)
│   ├── app/
│   │   ├── api/               # API clients (Axios, Client-side logic)
│   │   ├── screens/           # Dashboard, Practice, Test, Result, Review
│   │   └── utils/             # Audio utilities, Async storage for tracking
│   └── app.json               # iOS/Android Build & EAS Config
└── citizenship-backend/       # Backend: FastAPI (Python)
    ├── app/
    │   ├── routers/           # /stt, /tts, /evaluate, /questions
    │   ├── services/          # OpenAI API wrappers & logic
    │   └── data/              # Multilingual JSON question banks
    └── Dockerfile             # Containerization for deployment

---

## 🛠 Tech Stack

### **Frontend**
* **Framework:** `React Native` (Expo)
* **UI/UX:** Custom design with native components for accessibility.
* **Audio:** `Expo-Audio` for seamless recording.
* **Build Tool:** `EAS` (Expo Application Services).

### **Backend**
* **Framework:** `FastAPI` (Asynchronous Python).
* **AI Integration:** `OpenAI Whisper-1` (STT), `GPT-4o-mini` (Evaluation).
* **Deployment:** `Docker`, Cloud Hosting (Heroku/AWS).

---

## 🚀 Getting Started

### 1. Backend Setup (FastAPI)
First, navigate to the backend directory and set up your environment:
```bash
cd citizenship-backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
# Set your OPENAI_API_KEY in a .env file
uvicorn app.main:app --reload


---

## 👨‍💻 Developer: Sola Lhim
**Full-stack Software Engineer & AI Researcher**

* **End-to-End AI Architecture:** Designed and implemented the complete audio processing pipeline—integrating mobile recording, asynchronous STT (Whisper), and LLM-based semantic evaluation (GPT-4o-mini).
* **User-Centered UI/UX:** Developed a high-fidelity mobile interface using React Native, specifically optimized for high-stakes testing environments with focus on accessibility and data visualization.
* **Scalable Backend Engineering:** Engineered a robust FastAPI server to handle concurrent AI processing requests, dynamic question serving, and secure API integration.
* **Full Lifecycle Management:** Successfully managed the entire deployment cycle, from initial beta testing to public release on both the **Google Play Store** and **Apple App Store**.

---

