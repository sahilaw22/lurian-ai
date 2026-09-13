<div align="center"> <h1>Lurian AI - A Personal Academic Assistant </h1></div>

> **A personalized, context-grounded AI academic companion and retrieval system for university & college students.**

---

## What is this Project About?

The **Lurian AI** is an intelligent, full-stack **Retrieval-Augmented Generation (RAG)** platform engineered to solve the everyday academic information discovery challenges faced by college students.

Instead of relying on generic public AI tools (which often hallucinate, fabricate outdated academic regulations, or don't know college-specific syllabus), this system connects directly to **Official College Database**:

- **University Syllabus & Course Outlines** (Branch-wise: CSE, ECE, EE, Civil, Mechanical)
- **Previous Years' Examination Papers & Answer Keys**
- **Official College Circulars, Academic Calendars & Datesheets**
- **Handwritten Faculty Lecture Notes & Lab Manuals**

By combining a **React 18 + Vite** frontend, a high-performance **Python FastAPI** backend, a **ChromaDB** vector database, and **Google Gemini AI**, the assistant provides instant, verified, and cited academic answers in seconds.

---

## Why Are We Building This? (The Problem Statement)

In like many colleges, academic information is fragmented across multiple non-searchable sources:

1. **Scattered & Siloed Documents:** Syllabus, circulars, and notifications are distributed across notice boards, unindexed PDFs on websites, and informal WhatsApp groups.
2. **Unsearchable Scanned Notes & Exam Papers:** Handwritten classroom notes and past exam papers are shared as image scans or photo PDFs that cannot be searched via standard text search.
3. **Generic AI Hallucinations:** Commercial AI models (like baseline ChatGPT or Copilot) do not have access to GCET Jammu's specific university guidelines or grading schemes, leading to inaccurate exam guidance.
4. **Repetitive Administrative Overhead for Faculty:** Professors and department heads repeatedly answer identical questions regarding exam patterns, passing marks, lab dates, and syllabus topics.

**Our Mission:** Provide a single, centralized, intelligent academic assistant that acts as a 24/7 personal tutor and college guide with **100% grounded, zero-hallucination accuracy**.

---

## Key Capabilities & Deep Technical Highlights

### A. Semantic Context Grounding (RAG Pipeline)
- Every user inquiry triggers a semantic similarity search across embedded vector collections in **ChromaDB**.
- The assistant is bound by strict system guardrails: it answers **only** using verified context retrieved from college files, eliminating fabricated policies or hallucinated exam dates.

### B. Multi-Modal OCR for Notes & Question Papers
- Students often study from photos of handwritten notes or printed exam sheets.
- Built-in **Tesseract OCR** and **PyMuPDF** pipelines automatically extract and index text from uploaded snapshots, making handwritten notes instantly searchable and interactive.

### C. Branch & Semester Personalization
- Students select their branch (e.g., Computer Science Engineering) and current semester (e.g., Semester 6).
- The retrieval engine automatically filters queries, ensuring a 2nd-year Mechanical student doesn't receive 4th-year Computer Science syllabus answers.

### D. Dual-Search Fallback
- If a query cannot be answered using existing local college records, the system seamlessly triggers a **DuckDuckGo Web Search Fallback** to retrieve fresh, verified information with citations.

### E. Voice Interaction & Accessibility
- Includes real-time speech recognition (mic input) and text-to-speech voice playback, making studying accessible and hands-free on mobile and desktop.

---

## Real-World Benefits & Impact

### For Students:
- **Instant Exam Preparation:** Quickly find past exam questions, topic weightages, and solved step-by-step explanations.
- **Clarified Syllabus Doubts:** Understand complex engineering concepts broken down into structured markdown with formulas and code blocks.
- **24/7 Availability:** Get immediate answers during late-night exam prep when professors and peers are unavailable.
- **Mobile & Desktop Friendly:** Clean, responsive UI with dark/light mode and accessible font sizing.

### For Faculty & Administration:
- **Reduced Query Fatigue:** Automates answers to repetitive questions regarding exam formats, syllabus changes, and attendance rules.
- **Effortless Resource Ingestion:** Teachers can upload PDFs, Word files, or notices through the Admin Dashboard, which are immediately processed and indexed.
- **Guaranteed Compliance:** Anti-hallucination guardrails ensure that college regulations and policies are quoted accurately.

---

## How It Works (At a Glance)

```text
  [ Student Types or Speaks Query ]
                 │
                 ▼
     [ Frontend: React 18 UI ]
                 │ (Axios REST API)
                 ▼
    [ Backend: FastAPI Gateway ]
                 │
      ┌──────────┴──────────┐
      ▼                     ▼
[ Local Query ]     [ Upload New PDF/Photo ]
      │                     │
      ▼                     ▼
[ ChromaDB Vector    [ OCR & Text Splitter ]
   Similarity ]             │
      │                     ▼
      │              [ Vector Embeddings ]
      │                     │
      │                     ▼
      │             [ Store in ChromaDB ]
      ▼
[ Context Retrieval + Grounding Prompt ]
      │
      ▼
[ Google Gemini Flash 1.5 / 2.0 ]
      │
      ▼
[ Verified Answer with Source Citations ]
```

---

## Future Vision & Extensibility

- **Automated Quiz & Flashcard Generator:** Dynamically generate practice multiple-choice questions from uploaded lecture notes.
- **AI Academic Planner:** Personalized study schedule generator aligned with GCET Jammu examination datesheets.
- **Multi-lingual Support:** Hindi and Dogri regional language translations for diverse student communities.

---

## License

[MIT](LICENSE) © 2026 Sahil