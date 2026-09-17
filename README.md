# NutriNexa (CERTAN-KEL-15)

**NutriNexa** (*Nutrisi Navigasi Enterprise & Ekstrasi X-Platform Agen*) adalah sistem informasi cerdas enterprise berbasis Agentic RAG, Diagnostic Gizi Visual, dan Optimasi Resep Zero-Waste.

## 👥 Tim Pengembang
- **AI Architect & Model Lead:** Choqy Pananda Sirait (12S24012)
- **Data & Knowledge Engineer:** Yesika Nadia Saragih (12S24024)
- **Integration & Interface Engineer:** Josua Sianturi (12S24035)
- **QA, Evaluation & Ethics Lead:** Jaya Bestina Simbolon (12S24023)

## 🚀 Setup & Instalasi Proyek
Proyek ini mengadopsi manajer paket modern **Astral `uv`**.

1. **Clone repositori:**
   ```bash
   git clone [https://github.com/CERTAN-KEL-15/CERTAN-KEL-15.git](https://github.com/CERTAN-KEL-15/CERTAN-KEL-15.git)
   cd CERTAN-KEL-15
   ```

## 📐 Arsitektur Sistem (System Architecture)

Diagram arsitektur sistem NutriNexa menunjukkan integrasi antara antarmuka pengguna, Agentic RAG, modul Diagnostik Gizi Visual, serta mesin Optimasi Resep Zero-Waste berbasis A* Search (`src/search_solver.py`):

```mermaid
graph TD
    User([Pengguna / Enterprise Client]) -->|Request / Konsultasi| UI[X-Platform Interface / API Gateway]
    
    subgraph NutriNexa Core Enterprise AI Engine
        UI --> Agent[Agentic RAG Orchestrator]
        Agent --> Knowledge[Knowledge Base / Vector DB]
        Agent --> Vision[Diagnostik Gizi Visual]
        Agent --> Optimizer[Optimasi Resep Zero-Waste & A* Search]
    end

    Optimizer -->|"Algoritma A* (Cost & Heuristic)"| Solver["src/search_solver.py"]
    Solver --> Output[Rute Substitusi Pangan & Rekomendasi Gizi]
    
    Output -->  UI
```