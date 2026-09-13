# SYSTEM OVERVIEW & ARCHITECTURE

## Project Context
- **Project Name:** GCET Academic Assistant (Full-Stack RAG System)
- **Tech Stack:** React 18, TypeScript, Vite, Tailwind CSS, FastAPI, Python 3.9+, LangChain, ChromaDB, Google Gemini API (1.5 Flash / 2.0 Flash), PyMuPDF, DuckDuckGo Search, Tesseract OCR
- **Goal:** Intelligent, context-grounded academic assistant for GCET Jammu students and faculty, ingesting syllabi, past examination papers, college circulars, and handwritten lecture notes with multi-turn chat, OCR extraction, and branch/semester filtering.

## Code Conventions & Standards
- **Formatting:** Prettier defaults, 2-space indentation for TypeScript/React, PEP 8 / 4-space indentation for Python.
- **State & Data:** Modular components, React Context (`StudentContext`) for global student profiles, strict TypeScript type safety (`noImplicitAny`), immutable state patterns.
- **API Style:** RESTful FastAPI conventions (`/api/chat`, `/api/ingest`, `/api/documents`), Pydantic v2 schemas for strict payload validation, asynchronous endpoint handlers, strict anti-hallucination grounding.

---

# MODES OF OPERATION

Transition between modes only upon explicit command.

- **Default State:** Listen for commands, acknowledge input, and await specific instructions.
- **Explain Mode:** Analyze code or system architecture without creating or modifying files.
- **Plan Mode:** Map out sequential technical steps and file impacts before implementation.
- **Implement Mode:** Execute code modifications ONLY after explicit user confirmation of a plan.
- **Review Mode:** Inspect diffs, run tests, and check for syntax or type errors post-implementation.

---

# CONTROL PROTOCOLS

## PROTOCOL: EXPLAIN
1. Conduct deep static analysis of relevant files.
2. Provide technical explanations without proposing unprompted codebase edits.
3. Identify relevant dependencies, side effects, and edge cases.

## PROTOCOL: PLAN
1. Break down execution into small, numbered, atomic tasks.
2. Explicitly list every file targeted for creation, modification, or deletion.
3. Call out potential breaking changes, environment variables, or schema updates.
4. **Restriction:** DO NOT execute code or write to files during Plan Mode.

## PROTOCOL: IMPLEMENT
1. Strictly follow the step-by-step plan approved by the user.
2. Respect tech-stack choices and established coding conventions.
3. Produce clean, maintainable, and well-commented code blocks.
4. Output a summary table of altered files and key modifications upon completion.

## PROTOCOL: REVIEW
1. Inspect the written code for type safety, lint errors, and logic bugs.
2. Verify that changes match the scope outlined in Plan Mode.
3. Provide instructions or command snippets for running tests locally.
