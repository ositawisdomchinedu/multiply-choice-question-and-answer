# MCQ Generator with Gemini + SentenceTransformer

This project is a **Minimum Viable Product (MVP)** that generates **high-quality multiple-choice questions (MCQs)** from large text documents (PDF).  
It uses **Google Gemini 2.5 Flash** for question generation & scoring, and **Sentence Transformers** for semantic filtering to ensure question quality.

---

## Features

- **Input**: Accepts PDF files (via `PyPDFLoader`).
- **Scalability**: 
  - Chunks documents into manageable pieces.  
  - Async + batching for fast parallel generation.  
  - Early stopping once the desired number of MCQs is reached.  
- **Question Generation**:
  - One correct answer derived from the text.  
  - 3–4 plausible distractors.  
  - Explanation for each question.  
- **Quality Control**:
  - Semantic filtering using `sentence-transformers`.  
  - LLM-based scoring (1–5) for clarity, relevance, and difficulty.  
- **Difficulty Management**:
  - Choose difficulty (`easy`, `medium`, `hard`) via config.  
- **Output**:
  - Saves all MCQs as a **JSON file** with full metadata (choices, answer, explanation, score).  
- **Flexibility**:
  - Skip unwanted pages (e.g., table of contents) via `skip_pages` config.  

---

## Tech Stack

- **Language**: Python 3.11+
- **LLM API**: Google Gemini (via `langchain-google-genai`)
- **Libraries**:  
  - [LangChain](https://www.langchain.com/) (prompt orchestration)  
  - [Google Generative AI](https://ai.google.dev/) (Gemini API)  
  - [Sentence Transformers](https://www.sbert.net/) (local embeddings)  
  - `tqdm` (progress bars)  
  - `pypdf` (PDF parsing)  

---



