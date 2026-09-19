<h1 align="center">Shubam Chaudhary</h1>

<p align="center">
  Backend Engineer · Distributed Systems, Microservices, GenAI<br>
  Software Engineer @ Blue Yonder · B.Tech, NIT Warangal · Hyderabad, India
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/shubam-chaudhary-41005a241/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://leetcode.com/u/SHUBAMCHAUDHARY/"><img src="https://img.shields.io/badge/LeetCode-FFA116?style=flat-square&logo=leetcode&logoColor=black" alt="LeetCode"></a>
  <a href="https://codeforces.com/profile/sam17"><img src="https://img.shields.io/badge/Codeforces-1F8ACB?style=flat-square&logo=codeforces&logoColor=white" alt="Codeforces"></a>
  <a href="https://www.codechef.com/users/shubam17sam"><img src="https://img.shields.io/badge/CodeChef-5B4638?style=flat-square&logo=codechef&logoColor=white" alt="CodeChef"></a>
  <a href="mailto:beshubam@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
  <!-- RESUME BUTTON GOES HERE once resume.pdf (phone number removed) is committed:
  <a href="https://github.com/shubamchaudhary/shubamchaudhary/raw/main/resume.pdf"><img src="https://img.shields.io/badge/Résumé-PDF-2F855A?style=flat-square&logo=readthedocs&logoColor=white" alt="Resume"></a>
  -->
</p>

---

### What I've worked on

**Backend — 2.5 years at Blue Yonder.** Java 17 and Spring Boot on a multi-tenant retail platform: allocation ranking that runs in 100% of customer allocations, feature-flag-controlled Snowflake connection routing across 1,000+ tenants, a zero-downtime dual-APIM gateway migration, and sync/async fallback layers. Spring Data JPA, Hibernate, PostgreSQL, Snowflake, Redis, Kafka, Azure, Docker, Kubernetes, OAuth 2.0.

**GenAI — shipped to production, not a weekend demo.** A LangGraph inventory-operations agent that lets planners read and update parameters conversationally: hierarchy-aware Postgres querying, Redis-staged writes with scenario-scoped Base+Overlay persistence, and human-in-the-loop approval through LangGraph interrupts. Turned multi-day ticket cycles into minutes.

**Testing and CI.** JUnit, Mockito, PostgreSQL-Testcontainers regression suites gating every PR merge, GitHub Actions batch-regression frameworks across 7 repositories.

**Frontend, when the project needs one.** React, Vite, Tailwind, Firebase (Auth, Firestore, Cloud Functions) — CodeNITW is mine end to end, UI included.

**Still learning, deliberately.** Right now: JVM internals, concurrency, Spring internals, and agentic RAG — evaluation (RAGAS, LLM-as-judge), guardrails, cost and observability. Picking up an unfamiliar stack is the part of this job I actually enjoy.

---

### Featured

#### [LogLens](https://github.com/shubamchaudhary/LogLens) · [live demo](https://deeploglens.vercel.app)

**LangGraph-based log intelligence RAG pipeline.** Turns a GB-scale log archive into a grounded, cited incident report you can question in plain English. Upload a file → deterministic parsers extract exact metrics → an LLM explains only the anomalous windows → you ask questions and get answers citing exact log lines. All the expensive AI work runs off the request path behind a durable queue.

- **Constant heap at any file size.** One streaming pass splits the archive into window-aligned byte ranges ("virtual parts", the Hadoop input-split idea); parallel consumers do ranged blob GETs. Heap stays flat whether the file is 1 MB or 10 GB.
- **Exactly-once *effects* on at-least-once delivery.** A marker row written in the same transaction as each part's data, plus fingerprint-keyed idempotent upserts, makes every Kafka redelivery a harmless no-op. A crash resumes from the last committed offset.
- **Rate limits modeled as Kafka partitions.** One partition ↔ one API key ↔ one consumer, so each worker self-paces to its quota with zero distributed coordination and a proactive token budget makes 429s a non-event.
- **LLMs never count.** Regex/Java parsers compute every metric on every window; the model touches only flagged windows — ~90% fewer LLM calls — and an LLM-as-judge loop rejects any claim the evidence doesn't support.
- **Retrieval built for recall.** Per-session chunk tables with right-sized HNSW, GIN and B-Tree indexes avoid post-filtered ANN recall collapse; Q&A runs corrective RAG (retrieve → grade → rewrite → re-retrieve) over RRF-fused hybrid vector + full-text search.

`Java 17` `Spring Boot` `Kafka` `PostgreSQL + pgvector` `Python` `FastAPI` `LangGraph` `S3/MinIO` `React` `Docker`

#### [CodeNITW](https://github.com/shubamchaudhary/CodeNITW) · [live](https://codenitw.vercel.app)

**Interview-prep platform for SDE aspirants** — the tool I built for my own preparation and opened up to others.

- **Structured study material** across a Core Stack (HLD, LLD, Java, Spring Boot, databases) and an AI Stack (RAG, agents, LangGraph), with per-topic markdown notes, code highlighting and screenshot attachments.
- **DSA tracker and study planner** — progress per topic, daily targets, and scheduled email nudges via Firebase Cloud Functions.
- **Job tracker** — openings feed, companies, contacts, and an application pipeline board.
- **Auth and route guards** — Firebase Auth with private and owner-only routes, so shared material and personal tracking live in one app.

`React` `Vite` `Tailwind` `MUI` `Firebase Auth` `Firestore` `Cloud Functions` `Vercel`

---

### Tech

**Languages** &nbsp;
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

**Backend** &nbsp;
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=flat-square&logo=spring&logoColor=white)
![Hibernate](https://img.shields.io/badge/Hibernate-59666C?style=flat-square&logo=hibernate&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![JUnit](https://img.shields.io/badge/JUnit_&_Mockito-25A162?style=flat-square&logo=junit5&logoColor=white)

**GenAI** &nbsp;
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=langgraph&logoColor=white)
![RAG](https://img.shields.io/badge/RAG-5A45FF?style=flat-square)
![pgvector](https://img.shields.io/badge/pgvector-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Human in the loop](https://img.shields.io/badge/Human--in--the--Loop-5A45FF?style=flat-square)

**Data** &nbsp;
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=flat-square&logo=snowflake&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)

**Frontend** &nbsp;
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)

**Cloud & DevOps** &nbsp;
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

---

### Problem solving

1,000+ DSA problems across [LeetCode](https://leetcode.com/u/SHUBAMCHAUDHARY/), [CodeChef](https://www.codechef.com/users/shubam17sam) and [Codeforces](https://codeforces.com/profile/sam17).

<div align="center">
  <img height="170" src="https://leetcard.jacoblin.cool/SHUBAMCHAUDHARY?theme=dark&font=baloo&ext=heatmap" alt="LeetCode stats">
</div>

<p align="center"><i>Open to backend / backend + GenAI roles.</i></p>
