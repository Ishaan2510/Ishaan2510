<div align="center">

# Ishaan Goswami

**Backend Engineer & ML Builder** · Flask · PostgreSQL · Redis · Azure · LightGBM · RAG

*PDEU (B.Tech CS, CGPA 9.29) + IIT Madras (B.S. Data Science) · Graduating 2027 · Ahmedabad, India*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ishaan-goswami-796814282/)
[![LeetCode](https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black)](https://leetcode.com/u/ishaan_102/)
[![HackerRank](https://img.shields.io/badge/HackerRank-00EA64?style=for-the-badge&logo=hackerrank&logoColor=black)](https://www.hackerrank.com/profile/ishaan_16)
[![Codeforces](https://img.shields.io/badge/Codeforces-1F8ACB?style=for-the-badge&logo=codeforces&logoColor=white)](https://codeforces.com/profile/ishaan_102)

</div>

---

## About

I build backend systems and ML pipelines that actually run in production — not just on my laptop.

Currently shipping a live F1 analytics platform (Azure VM, Gunicorn/gevent, Nginx, Vue.js frontend on Vercel) and have gone deep on the kinds of problems most undergrads only read about: race conditions under concurrent booking load, async task decoupling with Celery, real-time SSE feeds, and SHAP-based model interpretability for non-technical users.

I'm a 3rd-year CS undergrad at PDEU with a parallel B.S. in Data Science from IIT Madras. I've qualified GATE CSE 2026. What I care about most is engineering decisions that have real consequences — not toy projects.

---

## Tech Stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)

**Backend & APIs**

![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Celery](https://img.shields.io/badge/Celery-37814A?style=flat-square&logo=celery&logoColor=white)

**Frontend**

![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)

**Databases**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)

**Cloud & DevOps**

![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![Gunicorn](https://img.shields.io/badge/Gunicorn-499848?style=flat-square&logo=gunicorn&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

**ML & GenAI**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-9ACD32?style=flat-square&logo=lightgbm&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)

---

## Projects

### Pitlane Live — F1 Race Analytics Platform
*Flask · Vue.js · FastF1 · PostgreSQL · Gunicorn/gevent · Nginx · Azure VM · Vercel*

A full-stack F1 analytics platform I designed, built, and deployed end-to-end. Covers 23 circuits with animated race replay, a live SSE race feed with polling fallback, and a prediction scoring engine.

The production backend runs on Azure VM behind Nginx with gevent workers — chosen specifically to handle long-lived SSE connections without blocking the thread pool. Data ingestion and client serving are architected as independent concurrent processes so a stalled pipeline never kills API responsiveness.

- Live telemetry pipeline: positional stream parsing + piecewise linear interpolation for sub-second trajectory reconstruction
- JWT auth (HS256, 30-day expiry) with custom implementation — no library abstraction
- Atomic JSON write pattern to prevent clients from reading a half-written data file mid-update
- Season-wide prediction scoring with a ±2 lap window and confidence multiplier

[View Project →](https://github.com/Ishaan2510)

---

### VePark — Vehicle Parking Management System
*Flask-RESTful · Vue.js · PostgreSQL · Redis · Celery · Flask-Security*

A parking management system built for the IIT Madras B.S. project — but engineered with the concurrency problems of a real production system.

The hard problem here was double-booking: two users booking the same spot at the same millisecond. Fixed it with `SELECT FOR UPDATE` inside an explicit transaction — the database row is locked for the duration of the check-and-write, making the operation atomic. Redis caches availability lookups with a 30-second TTL and gets invalidated on every write, so stale data never leaks to clients.

- RBAC via Flask-Security with reusable `@admin_required` decorators
- Celery async task layer: daily summary emails, monthly usage reports, CSV exports — all decoupled from the request lifecycle
- Normalised schema across 5 entities with atomic state transitions on check-in/check-out

[View Project →](https://github.com/Ishaan2510)

---

### TechReg Analyst — F1 Regulation RAG System
*Python · LangChain · FAISS · sentence-transformers · Groq (LLaMA 3.1 8B) · Streamlit*

A production-grade RAG pipeline over 589 pages of FIA Formula 1 2026 Regulations. Built a two-stage retrieval architecture: BGE-small-en-v1.5 bi-encoder for recall (top-20 via FAISS ANN), then cross-encoder reranking for precision (top-5). Hits 80% Section Match@1 at ~1,000ms average retrieval latency on CPU with no GPU.

Hallucination mitigation via prompt grounding (temperature=0, context-only generation) and a numeric verification heuristic. Deployed on Streamlit with per-stage latency metrics and source expanders for citation verification.

[Live Demo →](https://github.com/Ishaan2510) · [GitHub →](https://github.com/Ishaan2510)

---

### F1 Pit Stop Effectiveness Predictor
*Python · FastF1 · LightGBM · SHAP · Streamlit*

End-to-end ML pipeline over 60+ F1 races. Engineered 19 domain features (tyre degradation rate, undercut delta, stint length) with class balancing. LightGBM classifier: precision 80%, recall 81%, **ROC-AUC 87.4%** on a 3,100+ sample holdout. Deployed as a Streamlit app with SHAP force plot integration for per-prediction feature attribution.

[View Project →](https://github.com/Ishaan2510)

---

## Currently Building

- Deepening system design skills: designing for scale, distributed consistency, and real-world tradeoffs
- Strengthening DSA on LeetCode (target: Medium fluency across trees, graphs, DP, sliding window)
- Interview preparation across CS fundamentals: OS, DBMS internals, networking, and frontend breadth

---

## Stats

<div align="center">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=Ishaan2510&show_icons=true&theme=github_dark&include_all_commits=true&count_private=true&hide_border=true"/>
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ishaan2510&layout=compact&langs_count=7&theme=github_dark&hide_border=true"/>

</div>

<div align="center">

[![GitHub Streak](https://streak-stats.demolab.com?user=Ishaan2510&theme=github-dark-blue&hide_border=true)](https://git.io/streak-stats)

</div>

---

## Competitive Programming

| Platform | Achievement |
|---|---|
| LeetCode | 100+ problems solved |
| HackerRank | 5-Star in Python & SQL |
| Codeforces | Peak Rating 1100 · 11 contests |
| GATE 2026 | Qualified — Computer Science & Engineering |

---

## Contact

- Email: [ishaangoswami735@gmail.com](mailto:ishaangoswami735@gmail.com)
- LinkedIn: [ishaan-goswami](https://www.linkedin.com/in/ishaan-goswami-796814282/)
- GitHub: [Ishaan2510](https://github.com/Ishaan2510)

Open to backend engineering roles, ML system internships, and interesting problems. If you're building something with real concurrency or data at scale, I want to hear about it.
