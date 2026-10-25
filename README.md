# InterviewAI - Smarter Hiring & Assessment Platform

InterviewAI is a lightweight, single-page web application designed for structured technical hiring. It leverages client-side document parsing and native media recording APIs to facilitate customizable assessments, resume-aware interview prompts, and full-session video recording—all executed and reviewed within a secure, serverless local browser environment.

---

## 🚀 Key Features

* **Role-Based Workflows:**
  * **Recruiter Dashboard:** Create customizable assessments (job titles, difficulty, time limits, question counts) and generate private room codes.
  * **Candidate Portal:** Join private assessment rooms, upload required documents, and complete timed tests with continuous media recording.
* **Dynamic Assessments & Resume Integration:**
  * **Knowledge Assessment (MCQs):** Timed multiple-choice technical questions based on the selected role and difficulty.
  * **Resume-Aware Prompts:** Upload a `.docx` resume that is parsed locally in the browser to extract text and dynamically personalize spoken interview questions.
* **Full-Session Recording:**
  * Requires explicit candidate consent to access the camera and microphone.
  * Records the entire candidate session continuously (across both MCQ and spoken interview stages) using native browser media APIs.
* **Recruiter Result Portal:**
  * Comprehensive post-assessment reports including MCQ scores and extracted resume text.
  * In-browser video playback of the candidate's full recorded session with options to download the video locally.

---

## 🛠️ Tech Stack & Dependencies

* **Frontend Framework:** Plain HTML5, Modern Vanilla JavaScript (ES6+)
* **Styling:** Custom Vanilla CSS (with CSS Variables for theming)
* **Document Parsing:** [Mammoth.js](https://github.com/mwilliamson/mammoth.js) (via CDN) for local `.docx` extraction
* **Media Capture:** Native WebRTC (`MediaStream`) and `MediaRecorder` APIs
* **Data Storage:** 
  * `localStorage` (User sessions, assessment metadata, test scores)
  * `IndexedDB` (Heavy video blob storage for session recordings)

---

## 🚦 Getting Started

### Prerequisites

No complex build pipeline or package manager (npm/yarn) is required. The application runs directly in any modern web browser.

### Running Locally

1. Download or save `interviewai_2.html`.
2. Open the file directly in any modern web browser (Chrome, Safari, Firefox, Edge).
3. **Note on Camera Permissions & Storage:** 
   * Live streaming video features (`getUserMedia`) require an **HTTPS** connection or `localhost`/`127.0.0.1`. If opened as a local `file://`, ensure your browser allows camera access for local files.
   * **Important:** Data is stored locally. To fully test the workflow, the Recruiter and Candidate flows must be completed in the **same browser profile**.

---

## 📁 Application Architecture

```text
├── Index (HTML Entry)
│   ├── Navigation & Auth Modals
│   ├── Recruiter Dashboard (Assessment Creation & Analytics)
│   ├── Candidate Setup (Room Join, Resume Upload & Media Consent)
│   ├── Active Assessment Loop (MCQ Timer & Spoken Prompts)
│   └── Results Portal (Report Summaries & Video Player)
└── Script Logic
    ├── LocalStorage State & Auth Manager
    ├── Mammoth.js DOCX Parsing Engine
    ├── MediaRecorder & Stream Handler
    └── IndexedDB Video Storage Engine
```

---

## 📜 License

This project is open-source and available under the standard MIT License.