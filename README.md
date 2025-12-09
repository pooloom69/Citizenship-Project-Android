#🇺🇸 Citizenship Coach
 
Citizenship Coach is an AI-powered mobile application designed to help users practice for the U.S. Naturalization Civics Test.
The project consists of two main components:

📱 citizenship-coach — React Native (Expo) mobile application

🌐 citizenship-backend — FastAPI server powered by OpenAI Whisper + GPT models

This is the combined top-level README for the entire project.


##Features
Mobile App (citizenship-coach)

Complete 2008 & 2025 USCIS Civics Test question sets

Practice Mode, Test Mode, Question Bank, and Review Mode

Voice Recording → Whisper STT transcription

AI-powered answer evaluation (semantic comparison, flexible with grammar/pronunciation errors)

Text-to-Speech (TTS) for reading questions aloud

Bookmarking questions & tracking wrong answers

Clean, intuitive UI built with Expo + React Native


Backend API (citizenship-backend)

Provides all AI processing and data services required by the app:

🗣️ Speech-to-Text (STT)

Converts user audio (M4A/WAV) to text using Whisper

Endpoint: /stt

🔊 Text-to-Speech (TTS)

Converts question text to natural English audio (MP3)

Endpoint: /tts

🧠 AI Answer Evaluation

Compares user answers with official answers using GPT-4o-mini

Allows flexible interpretation of partial, paraphrased, or imperfect answers

Endpoint: /evaluate

📚 Question Data

Provides English/Korean question bank (questions_all.json)

Random question generation

Endpoints: /questions, /questions/random


##Project Structure 
```
CITIZENSHIP-PROJECT/
│
├── citizenship-coach/        # Frontend (React Native / Expo)
│   ├── app/
│   │   ├── api/              # STT, TTS, evaluate, questions
│   │   ├── components/       # Reusable UI components
│   │   ├── config/           # Colors / theme config
│   │   ├── screens/          # Home, Practice, Test, Result, Review screens
│   │   ├── utils/            # Audio utilities, bookmarks, wrong answer store
│   │   └── assets/           # Images, icons, splash graphics
│   ├── app.json
│   ├── eas.json              # Expo EAS build config
│   ├── package.json
│   └── README.md
│
├── citizenship-backend/      # Backend (FastAPI)
│   ├── app/
│   │   ├── data/             # Question set JSON files
│   │   ├── models/           # Pydantic schemas
│   │   ├── routers/          # API route definitions
│   │   ├── services/         # Whisper, TTS, Evaluate service logic
│   │   ├── config.py
│   │   └── main.py
│   ├── requirements.txt
│   ├── Dockerfile
│   ├── Procfile
│   └── README.md
│
└── README.md                 # Top-level combined README

```

##🚀 Getting Started

1) Backend Setup (FastAPI)
1. Create virtual environment
```
cd citizenship-backend
python -m venv venv
source venv/bin/activate  # Mac/Linux
# venv\Scripts\activate   # Windows
```
2. Install dependencies
```
pip install -r requirements.txt
```
4. Environment variables

Create a .env file:
```
OPENAI_API_KEY=sk-your-api-key
```
4. Run server
```
uvicorn app.main:app --reload
```

Local API docs:
👉 http://127.0.0.1:8000/docs

2) Frontend Setup (React Native / Expo)
1. Install dependencies
```
cd citizenship-coach
npm install
```
3. Configure backend API URL

Inside app/api/client.js:
```
export const API_URL = "http://127.0.0.1:8000";  // or deployed backend URL
```
3. Run the app
```
npx expo start
```

Open the Android emulator or scan the QR code with the Expo Go app.


🔗 API Endpoints Summary
POST /stt

Input: audio file
Output: transcribed text

POST /tts

Input: question text
Output: MP3 audio

POST /evaluate

Input: user_answer + correct_answer
Output: evaluation result JSON

GET /questions

Returns full question set

GET /questions/random

Returns a random question


##Sola Lhim

Full-stack development (mobile + backend)

UI/UX design for all screens

Audio pipeline (record → STT → evaluation)

FastAPI AI services integration

Deployment & testing

