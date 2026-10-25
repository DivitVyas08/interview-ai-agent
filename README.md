# InterviewAI — Smarter Hiring

InterviewAI is a completely browser-based prototype of an AI-assisted hiring platform. It allows recruiters to create structured technical assessments and candidates to complete timed multiple-choice questions (MCQs) alongside a recorded spoken interview.

All data, including user accounts, assessment configurations, resume text, and full-session video recordings, are handled directly within the browser using LocalStorage and IndexedDB. 

## 🚀 Features

* **Role-Based Workflows:** Distinct dashboards for **Recruiters** (creating assessments, reviewing candidates) and **Candidates** (taking tests, recording interviews).
* **Customizable Assessments:** Configure job titles, domains, difficulty levels, question counts, and time limits.
* **Resume-Aware Prompts:** Candidates upload a `.docx` resume, which is parsed locally in the browser to personalize interview questions.
* **Full-Session Recording:** Continuous camera and microphone recording captures the candidate's screen time during both the MCQ and spoken interview stages.
* **Recruiter Result Portal:** View MCQ scores, read the extracted resume text, and play back the candidate's recorded video session directly in the browser.

## 🛠️ How to Run

Because this is a serverless prototype, there are no backend dependencies or build steps required.

1. Download the `interviewai_2.html` file to your local machine.
2. Open `interviewai_2.html` in a modern web browser (Google Chrome, Mozilla Firefox, Microsoft Edge, or Safari).
   * *Note: For camera and microphone access to function properly, the file must be opened in a secure context (like `localhost` during development, or simply served via a basic local HTTP server, though modern browsers usually allow `file://` protocol access for local testing).*

## 📖 Usage Guide

### For Recruiters
1. Click **Create account** and select the **Recruiter** role.
2. From the dashboard, fill out the **Create an assessment** form with the job details, question counts, and time limits.
3. Click **Create assessment** to generate a unique 6-character **Room Code**.
4. Share this room code with your candidates.
5. Once a candidate completes the assessment, refresh the dashboard and click **View results** to review their MCQ answers and video recording.

### For Candidates
1. Click **Create account** and select the **Candidate** role.
2. Enter the **Room Code** provided by the recruiter.
3. Upload a `.docx` format resume (required).
4. Grant camera and microphone permissions and agree to the recording consent.
5. Complete the timed Multiple Choice Questions.
6. Answer the spoken interview prompts aloud while being recorded.
7. Wait for the submission to finalize and the recording to save locally.

## 💻 Technical Details

This application is built entirely in a single file using vanilla web technologies:
* **UI & Styling:** Vanilla HTML5 and CSS3 (with CSS Variables for theming).
* **Scripting:** Vanilla JavaScript (ES6+).
* **Document Parsing:** Uses [Mammoth.js](https://github.com/mwilliamson/mammoth.js) (via CDN) to extract raw text from `.docx` files entirely client-side.
* **Media Recording:** Utilizes the native `MediaStream` and `MediaRecorder` APIs to capture webcam and microphone input.
* **Data Storage:**
  * `localStorage`: Stores user credentials, assessment metadata, and submission results (MCQ scores, JSON data).
  * `IndexedDB`: Used to store the heavy video blobs (WebM/MP4) from candidate recordings via a custom database named `InterviewAIRecordings`.

## ⚠️ Important Limitations (Prototype Status)

* **Local Storage Only:** Data is **not** sent to a cloud server. If a candidate completes an assessment on their computer, the recruiter *cannot* see the result on a different computer. To fully test the workflow, the Recruiter and Candidate flows must be completed in the **same browser profile**.
* **Security:** Passwords are saved in plain text in the browser's local storage. **Do not use real passwords** when testing this prototype.
* **Video Size:** Long recordings may consume significant local storage space in your browser's IndexedDB. Use the "Download full recording" feature to back up videos if needed.