# 🧠 LifeStack AI
> **VietSpark Break Into Tech RAG Competition 2026**

LifeStack AI is a RAG-powered lifestyle and productivity assistant that helps users break the cycle of procrastination and build sustainable daily routines grounded in behavioral science, nutrition research, and evidence-based productivity frameworks.

Drawing from 20 peer-reviewed sources across procrastination psychology, sleep science, supplement research, and habit-building literature — it generates a **personalized daily plan** based on the user's goals, energy levels, and schedule, and delivers **science-backed rescue strategies** when procrastination or low energy derails their day.

---

## 📸 Demo

### Onboarding — Tell LifeStack About Your Day
![Onboarding Screen](assets/onboarding.png)

### 📅 Plan My Day
![Plan My Day](assets/plan_my_day.png)

### 🚨 Rescue Mode — I Need Help Right Now
![Rescue Mode](assets/rescue_mode.png)

---

## ✨ Features

- **Personalized Onboarding** — 4-question profile (goals, day type, sleep quality, main struggles)
- **Plan My Day Mode** — Full daily plan with morning routine, deep work blocks, nutrition timing, movement, and wind-down
- **Rescue Mode** — Immediate, actionable science-backed strategies when you're stuck mid-day
- **Citation-Grounded Answers** — Every response cites its source documents — no hallucinations
- **20-Document Knowledge Base** — Peer-reviewed research across 7 topic areas
- **Embedding Visualization** — t-SNE chart showing document clusters by topic
- **Query Logging** — All interactions logged to Google Drive for analysis

---

## 🏗️ Architecture

```
User Query + Onboarding Profile
        │
        ▼
Dense Retriever (ChromaDB + all-MiniLM-L6-v2)
        │
        ▼
Top-5 Relevant Chunks with Citations
        │
        ▼
RAG Chain (LangChain + GPT-4o-mini)
        │
        ▼
Personalized, Cited Response → Gradio UI
```

---

## 📚 Knowledge Base (20 Documents)

| Topic | Sources |
|-------|---------|
| 🧠 Procrastination | Emotion Regulation (PMC), CBT Strategies (APA), Self-Compassion (Neff), Implementation Intentions (Gollwitzer) |
| 😴 Sleep | Cognitive Performance (NIH), Circadian Rhythms (NIH), Sleep Hygiene (Sleep Foundation) |
| 🍽️ Nutrition | Protein & Nutrient Timing (ISSN), Cortisol & Stress (NIH), Body Recomposition (ISSN) |
| 💊 Supplements | Rhodiola Rosea (Examine), Magnesium, Creatine & Omega-3 (Examine) |
| ⚡ Productivity | Atomic Habits (James Clear), Deep Work (Cal Newport), Pomodoro Technique, GTD (David Allen), Time Blocking (HBR) |
| 💪 Training | Resistance Training & Mental Health (PMC) |
| 🔥 Motivation | Flow State Research, Self-Determination Theory Meta-Analysis |

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| LLM | GPT-4o-mini (OpenAI) |
| Embeddings | all-MiniLM-L6-v2 (Sentence Transformers) |
| Vector DB | ChromaDB (persistent) |
| RAG Framework | LangChain |
| Document Loaders | PyPDFLoader, UnstructuredHTMLLoader |
| UI | Gradio |
| Evaluation | RAGAS (Faithfulness + Answer Relevancy) |
| Visualization | t-SNE (scikit-learn) + matplotlib |
| Runtime | Google Colab |

---

## ⚡ Quickstart

### 1. Open in Google Colab
Upload `LifeStack_AI.ipynb` to Google Colab.

### 2. Add your OpenAI API Key
In Cell 3, replace:
```python
OPENAI_API_KEY = "sk-your-key-here"
```
With your real key. Or use Colab Secrets (recommended).

### 3. Upload your documents
Run Cell 1 — it opens a file picker. Select all 20 files from the `data/` folder.

### 4. Run cells in order
```
Cell 1 → 2 → 3 → 4 → 5 → 6 → 7 → 9 → 10 → 11 → 13 → 16 → 17
```

### 5. Open the Gradio UI
Cell 17 outputs a public URL. Open it in your browser and start using LifeStack AI!

---

## 📁 Project Structure

```
lifestack-ai/
├── LifeStack_AI.ipynb        # Main notebook (Cells 1–17)
├── README.md                 
├── requirements.txt          
├── .gitignore                
├── assets/                   # Screenshots for README
└── data/                     # 20 research documents (PDF + HTML)
```

---

## 🔬 Evaluation

RAGAS metrics (run Cell 15 to evaluate):

| Metric | Target |
|--------|--------|
| Faithfulness | ≥ 0.75 |
| Answer Relevancy | ≥ 0.80 |

---

## 🙏 Credits

Built for the **VietSpark Break Into Tech RAG Competition 2026**.

Research sources: PMC, APA, NIH, ISSN, Examine.com, Sleep Foundation, and published works by James Clear and Cal Newport.
