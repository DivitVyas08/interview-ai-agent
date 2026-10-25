# HireNeuron AI - Autonomous Video Interviewer & Intelligent Proctoring Agent

HireNeuron AI is an end-to-end, autonomous video interview platform that automates candidate screening while ensuring strict interview integrity. Powered by Large Language Models (LLMs), Computer Vision, and Speech Technologies, the agent conducts real-time video interviews, dynamically evaluates candidate responses against job descriptions, and monitors sessions using dual-camera intelligent proctoring.

---

## ✨ Key Features & Capabilities

### 📄 1. Onboarding & AI Question Generation
- **Resume & JD Parsing:** Extracts skills, experience, and projects from candidate resumes (PDF/DOCX) and maps them against Job Descriptions.
- **Dynamic Questioning:** Generates technical, behavioral, and scenario-based questions (defaults to 10 configurable questions) tailored to the candidate's profile.
- **Candidate System Checks:** Automated camera, microphone, and permission verification before starting.

### 🎙️ 2. Autonomous AI Interviewer
- **Real-Time Voice Interaction:** Uses Speech-to-Text (STT) and Text-to-Speech (TTS) for natural, conversational back-and-forth communication.
- **Adaptive Follow-up Questions:** Context-aware questioning based on previous candidate answers without violating interview time limits.
- **Video & Audio Logging:** Captures response transcripts, audio timing, and completion status.

### 🛡️ 3. Intelligent Dual-Camera Proctoring
- **Primary Feed Analysis:** Computer vision models monitor face presence, multiple-person entry, and head pose/gaze indicators.
- **Secondary Smartphone Camera:** Candidates scan a QR code to securely pair a mobile browser camera providing a wide-angle workspace view.
- **Audio Monitoring:** Detects additional background voices or unusual audio disruptions.
- **Timestamped Incident Logging:** Records observed events with evidence markers without automatically disqualifying candidates.

### 📊 4. AI Candidate Evaluation & Recruiter Dashboard
- **Rubric-Based Scoring:** Evaluates answers for technical correctness, clarity, and completeness on a 1–5 scale.
- **Comprehensive Assessment:** Generates summaries of strengths, knowledge gaps, and overall suitability.
- **Recruiter Dashboard:** Displays transcripts, proctoring event timelines, and scoring breakdowns with options for recruiter overrides.

---

## 🛠️ Technology Stack
- **AI & LLM Integration:** Google Gemini API / LLMs for question generation, response evaluation, and summarization.
- **Speech Technologies:** Web Speech API / STT & TTS engines for voice interaction.
- **Computer Vision & Audio:** OpenCV / MediaPipe / TensorFlow.js for face, gaze, and multi-person detection.
- **Real-Time Communication:** WebRTC / WebSockets for primary and secondary smartphone video streaming.
- **Frontend & UI:** HTML5, Tailwind CSS, Lucide Icons, and JavaScript.

---

## 🔒 Security & Privacy Notice
- **Zero API Keys Committed:** All secrets and API credentials are kept securely in runtime environment configurations.
- **Explicit Candidate Consent:** Proctoring, video recording, and secondary camera streaming require explicit candidate permission during onboarding.
