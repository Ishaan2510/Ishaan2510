<div align="center">

# Ishaan Goswami

*PDEU (B.Tech CS, CGPA 9.29) + IIT Madras (B.S. Data Science) · Graduating 2027 · Ahmedabad, India*

[![Portfolio](https://img.shields.io/badge/Portfolio-ishaangoswami.vercel.app-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://ishaangoswami.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ishaan-goswami-796814282/)
[![Mail](https://img.shields.io/badge/Mail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ishaangoswami735@gmail.com)
[![LeetCode](https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black)](https://leetcode.com/u/ishaan_102/)
[![HackerRank](https://img.shields.io/badge/HackerRank-00EA64?style=for-the-badge&logo=hackerrank&logoColor=black)](https://www.hackerrank.com/profile/ishaan_16)
[![Codeforces](https://img.shields.io/badge/Codeforces-1F8ACB?style=for-the-badge&logo=codeforces&logoColor=white)](https://codeforces.com/profile/ishaan_102)

</div>

---

## About

I build backend systems and ML pipelines that actually run in production. Not laptop demos, not tutorials — services with Kubernetes manifests, GitOps pipelines, race-condition guards, and the kind of incident I've debugged at 1 AM because Redis went down.

Currently shipping Cortex (distributed task platform on Kubernetes with Argo CD), Pitlane Live (F1 analytics on Render + Supabase), and a RAG system over 589 pages of FIA regulations. GATE 2026 qualified in CSE.
---

## Tech Stack

[![Skills](https://skillicons.dev/icons?i=python,js,ts,cpp,nodejs,express,flask,vue,react,tailwind,mongodb,postgres,redis,docker,kubernetes,nginx,azure,vercel,git,github,linux,bash&perline=11)](https://skillicons.dev)

**ML & GenAI:** PyTorch · scikit-learn · LightGBM · SHAP · LangChain · FAISS · HuggingFace · Sentence Transformers · Groq

---

## Featured Projects

### Cortex — Distributed AI Task Platform
*React 19 · Node.js/Express 5 · Python worker · MongoDB · Redis · Docker · Kubernetes · Argo CD · GitHub Actions*

A production-grade distributed task processing system. Tasks submitted from the React frontend are queued in Redis (`lPush`), picked up by a Python worker via blocking `brpop`, and tracked from `pending → running → success/failed` in real time. Every component containerised, every deployment declared as Kubernetes manifests, every push to `main` triggers a full build-push-deploy pipeline that Argo CD syncs to the cluster automatically.

**The hard part:** GitOps-driven CI/CD. GitHub Actions builds Docker images, pushes to Docker Hub tagged with commit SHA, then updates the companion infra repo's manifests via `sed` and commits. Argo CD watches that repo with auto-sync, prune, and self-heal enabled. Cluster drift gets corrected automatically.

[Repository →](https://github.com/Ishaan2510/cortex)

---

### Pitlane Live — F1 Race Analytics Platform
*Flask · Vue 3 · PostgreSQL (Supabase) · FastF1 · Gunicorn/gthread · Render*

Full-stack F1 platform with race replays, live standings, and user predictions. Originally deployed on Azure VM with Gunicorn + gevent + Nginx; migrated to Render + Supabase when Azure student credits ran out. Switched gevent → gthread workers to fix an SSL monkey-patching recursion error on Render's runtime. Pre-built race JSONs committed to the repo to keep the 512MB server within memory bounds.

[Live →](https://pitlane-live-three.vercel.app) · [Repository →](https://github.com/Ishaan2510)

---

### TechReg Analyst — F1 Regulations RAG System
*LangChain · FAISS · BGE-small · Cross-Encoder Reranker · Groq LLaMA 3.1 8B · Streamlit*

Production RAG over 589 pages of FIA 2026 F1 Regulations. Two-stage retrieval: BGE bi-encoder for recall (top-20 via FAISS), cross-encoder reranking for precision (top-5). **80% Section Match@1 at ~1,000ms retrieval latency, CPU-only, zero cost.** Three-layer hallucination mitigation: prompt grounding, temperature=0, and a numeric verification heuristic.

[Live →](https://f1-regulations-rag-system.streamlit.app/) · [Repository →](https://github.com/Ishaan2510/f1-regulations-rag-system)

---

### F1 Pit Stop Effectiveness Predictor
*LightGBM · SHAP · FastF1 · Streamlit*

End-to-end ML pipeline over 60+ Grand Prix. 19 engineered features (tyre degradation rate, undercut delta, stint length). LightGBM classifier on 3,100+ samples: **ROC-AUC 87.4%, precision 80%, recall 81%.** SHAP TreeExplainer for per-prediction feature attribution — every prediction explains itself.

[Live →](https://f1-pitstop-predictor-ig.streamlit.app/) · [Repository →](https://github.com/Ishaan2510)

---

## GitHub Activity

<div align="center">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=Ishaan2510&show_icons=true&theme=github_dark&include_all_commits=true&count_private=true&hide_border=true"/>
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Ishaan2510&layout=compact&langs_count=8&theme=github_dark&hide_border=true"/>

</div>

<div align="center">

[![GitHub Streak](https://streak-stats.demolab.com?user=Ishaan2510&theme=github-dark-blue&hide_border=true)](https://git.io/streak-stats)

</div>

---

## Dashboard

<div align="center">

[![Dashboard stats of @Ishaan2510](https://next.ossinsight.io/widgets/official/compose-user-dashboard-stats/thumbnail.png?user_id=162294081&image_size=auto&color_scheme=dark)](https://next.ossinsight.io/widgets/official/compose-user-dashboard-stats?user_id=162294081)

</div>

---

## DSA & Competitive Programming

<div align="center">

<a href="https://leetcode.com/u/ishaan_102/">
  <img src="https://leetcard.jacoblin.cool/ishaan_102?theme=dark&font=Source%20Code%20Pro&ext=heatmap" alt="LeetCode Stats" />
</a>

</div>

| Platform | Achievement |
|---|---|
| LeetCode | 150+ problems solved |
| HackerRank | 5-Star in Python & SQL |
| Codeforces | Peak Rating 1100 · 12 contests |
| GATE 2026 | Qualified — Computer Science & Engineering |

---

## Trophies

<div align="center">

[![trophy](https://github-profile-trophy.vercel.app/?username=Ishaan2510&theme=gruvbox&no-frame=true&row=1&column=7&margin-w=15)](https://github.com/ryo-ma/github-profile-trophy)

</div>

---

## Find Me On

[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=flat-square&logo=vercel&logoColor=white)](https://ishaangoswami.vercel.app/)
[![Mail](https://img.shields.io/badge/Mail-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:ishaangoswami735@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ishaan-goswami-796814282/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Ishaan2510)
[![LeetCode](https://img.shields.io/badge/LeetCode-FFA116?style=flat-square&logo=leetcode&logoColor=black)](https://leetcode.com/u/ishaan_102/)
[![HackerRank](https://img.shields.io/badge/HackerRank-00EA64?style=flat-square&logo=hackerrank&logoColor=black)](https://www.hackerrank.com/profile/ishaan_16)
[![Codeforces](https://img.shields.io/badge/Codeforces-1F8ACB?style=flat-square&logo=codeforces&logoColor=white)](https://codeforces.com/profile/ishaan_102)
