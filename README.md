<!-- banner.svg and journey.svg must sit in the repo root, next to README.md. The ?v=1 on their URLs busts the image cache: bump it if you replace a file. -->
<p align="center">
  <img src="https://raw.githubusercontent.com/gnarendra9014-user/gnarendra9014-user/main/banner.svg?v=1" alt="Gutti Narendra: Backend Development, Software Engineering, and SDET" width="100%" />
</p>

<!-- Animated line: edit the lines= part of the URL. Use + for spaces and ; between lines. -->
<p align="center">
  <img src="https://readme-typing-svg.demolab.com/?font=Fira+Code&size=20&pause=1200&color=2EA043&center=true&vCenter=true&width=560&height=40&lines=Building+reliable+backend+systems;Learning+distributed+systems;Solving+DSA+problems;Testing+edge+cases+and+failure+modes" alt="Building reliable backend systems. Learning distributed systems. Solving DSA problems. Testing edge cases and failure modes." />
</p>

<!-- LinkedIn: your portfolio links to linkedin.com/in/gutti-narendra-8b817b357 while this uses linkedin.com/in/gnarendra9100. Keep whichever URL is correct (here and in the footer). -->
<p align="center">
  <a href="https://gutti-narendra-portfolio.vercel.app/"><img src="https://img.shields.io/badge/Portfolio-238636?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio" /></a>
  <a href="https://linkedin.com/in/gnarendra9100"><img src="https://img.shields.io/badge/LinkedIn-30363D?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:gnarendra9100@gmail.com"><img src="https://img.shields.io/badge/Email-30363D?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Open_for-Software_Engineering_Roles-238636?style=flat-square&labelColor=30363D" alt="Open for software engineering roles" />
</p>

## 👨‍💻 About

Backend developer building APIs and event-driven services designed to stay correct under concurrency and failure.

- 🎓 **Education:** B.Tech Computer Science and Engineering (Data Science)
- 🧪 **Quality engineering:** testing, debugging, reliability, and edge cases, with automated test suites in node:test and pytest
- 🧩 **Problem solving:** 300+ problems solved on LeetCode
- 🏆 **Hackathon:** Top 5 at Dev Crafts Hackathon

> I like building things, breaking them on purpose, and figuring out why they broke.

## 🚀 Featured projects

### 💳 Distributed Payment & Wallet System

Payment and wallet backend focused on correctness under concurrency and partial failure, implemented two ways: a single service using the transactional outbox pattern, and event-driven microservices coordinated by a saga.

- 🔒 **Idempotent transfers:** SHA-256 payload fingerprinting with Redis and PostgreSQL checks, so a reused key with different details is rejected
- 🛡️ **Safe concurrency:** ACID transactions with ordered row-level locks to prevent deadlocks
- 📨 **Reliable events:** transactional outbox publishing to Kafka with retries, a dead-letter state, and idempotent consumers
- 🔄 **Distributed transactions:** saga orchestration with compensating actions across wallet, payment, and orchestrator services
- ✅ **Tested:** 27 unit and integration tests covering idempotency, refunds, auth guards, and duplicate event delivery

<img src="https://skillicons.dev/icons?i=nodejs,express,postgres,redis,kafka,docker,aws" height="40" alt="Node.js, Express, PostgreSQL, Redis, Kafka, Docker, AWS" />

<details>
<summary><b>View architecture</b></summary>

```mermaid
flowchart LR
    C["Client"] -->|"POST transfer<br/>+ idempotency key"| A["Express API"]
    A -->|"dedupe check,<br/>distributed lock"| R[("Redis")]
    A -->|"one ACID transaction:<br/>lock wallets, debit, credit,<br/>write outbox event"| P[("PostgreSQL")]
    P -->|"outbox poller<br/>(FOR UPDATE SKIP LOCKED)"| K["Kafka"]
    K -->|"at-least-once<br/>delivery"| E["Consumer"]
    E -->|"INSERT processed_events<br/>ON CONFLICT DO NOTHING"| P
```

</details>

📂 **Source:** [distributed-payment-wallet](https://github.com/gnarendra9014-user/distributed-payment-wallet) (outbox pattern) and [payment-wallet-system](https://github.com/gnarendra9014-user/payment-wallet-system) (saga microservices)

### ⚡ Scalable Job Scheduler

Job scheduling platform built with Node.js and BullMQ that runs asynchronous work through distributed queues and background worker pools.

- 📋 **Job types:** concurrent, delayed, and recurring (cron-style) jobs
- 🔁 **Failure handling:** automated retries with exponential backoff and a dead-letter queue
- 📦 **Deployment:** Docker and Kubernetes for horizontal scaling and fault tolerance

<img src="https://skillicons.dev/icons?i=nodejs,redis,postgres,docker,kubernetes" height="40" alt="Node.js, Redis, PostgreSQL, Docker, Kubernetes" />

<!-- Add the repository link here once the scheduler is public: 📂 **Source:** [repo-name](https://github.com/gnarendra9014-user/repo-name) -->

## 🛠️ Tech stack

<table>
  <tr>
    <td><b>💻 Languages</b></td>
    <td><img src="https://skillicons.dev/icons?i=cpp,py,js,ts,java" alt="C++, Python, JavaScript, TypeScript, Java" /></td>
  </tr>
  <tr>
    <td><b>⚙️ Backend &amp; databases</b></td>
    <td><img src="https://skillicons.dev/icons?i=nodejs,express,fastapi,postgres,mongodb,redis" alt="Node.js, Express, FastAPI, PostgreSQL, MongoDB, Redis" /></td>
  </tr>
  <tr>
    <td><b>☁️ Systems &amp; cloud</b></td>
    <td><img src="https://skillicons.dev/icons?i=kafka,docker,kubernetes,aws" alt="Kafka, Docker, Kubernetes, AWS" /></td>
  </tr>
  <tr>
    <td><b>🌐 Web</b></td>
    <td><img src="https://skillicons.dev/icons?i=nextjs,tailwind,supabase" alt="Next.js, Tailwind CSS, Supabase" /></td>
  </tr>
  <tr>
    <td><b>🧰 Tools &amp; platforms</b></td>
    <td><img src="https://skillicons.dev/icons?i=git,github,githubactions,npm,postman,vscode,vercel" alt="Git, GitHub, GitHub Actions, npm, Postman, VS Code, Vercel" /></td>
  </tr>
</table>

## 📈 Developer journey

<p align="center">
  <img src="https://raw.githubusercontent.com/gnarendra9014-user/gnarendra9014-user/main/journey.svg?v=1" alt="Developer journey: Python and C++, JavaScript and TypeScript, Node.js, Databases, Kafka, Distributed systems, and now system design and reliability" width="100%" />
</p>

<details>
<summary><b>What I built at each stage</b></summary>
<br />

<table>
  <tr>
    <td align="center">1️⃣</td>
    <td><img src="https://skillicons.dev/icons?i=py,cpp,fastapi,opencv" height="40" alt="Python, C++, FastAPI, OpenCV" /></td>
    <td><b>Foundations: Python and C++</b><br />Programming fundamentals, data structures, and algorithms. Built <a href="https://github.com/gnarendra9014-user/PCL">Road Safety AI</a> (YOLOv8 and OpenCV, served with FastAPI, tested with pytest) and <a href="https://github.com/gnarendra9014-user/Map-Routing">Map Router</a>, a pathfinding visualizer comparing Dijkstra, A*, and Contraction Hierarchies.</td>
  </tr>
  <tr>
    <td align="center">2️⃣</td>
    <td><img src="https://skillicons.dev/icons?i=js,ts,nextjs,tailwind,supabase" height="40" alt="JavaScript, TypeScript, Next.js, Tailwind CSS, Supabase" /></td>
    <td><b>The web: JavaScript and TypeScript</b><br />Core JavaScript and TypeScript, applied in <a href="https://github.com/gnarendra9014-user/resume-coach">resume-coach</a>, a Next.js app using Tailwind, Supabase auth, and the Groq API.</td>
  </tr>
  <tr>
    <td align="center">3️⃣</td>
    <td><img src="https://skillicons.dev/icons?i=nodejs,express" height="40" alt="Node.js, Express" /></td>
    <td><b>Backend: Node.js and Express</b><br />Built <a href="https://github.com/gnarendra9014-user/ecommerce-backend">ecommerce-backend</a>, a REST API with JWT authentication, request validation, cart and order flows, Razorpay payments, and Swagger docs.</td>
  </tr>
  <tr>
    <td align="center">4️⃣</td>
    <td><img src="https://skillicons.dev/icons?i=postgres,redis" height="40" alt="PostgreSQL, Redis" /></td>
    <td><b>Databases: PostgreSQL and Redis</b><br />Relational modelling and ACID transactions in PostgreSQL, with Redis for caching and distributed locks.</td>
  </tr>
  <tr>
    <td align="center">5️⃣</td>
    <td><img src="https://skillicons.dev/icons?i=kafka" height="40" alt="Kafka" /></td>
    <td><b>Event streaming: Kafka</b><br />Asynchronous, event-driven design with a transactional outbox, at-least-once delivery, and idempotent consumers in <a href="https://github.com/gnarendra9014-user/distributed-payment-wallet">distributed-payment-wallet</a>.</td>
  </tr>
  <tr>
    <td align="center">6️⃣</td>
    <td><img src="https://skillicons.dev/icons?i=docker,kubernetes" height="40" alt="Docker, Kubernetes" /></td>
    <td><b>Distributed systems</b><br />Saga orchestration with compensating actions across three services in <a href="https://github.com/gnarendra9014-user/payment-wallet-system">payment-wallet-system</a>, plus a BullMQ job scheduler with exponential backoff and dead-letter queues, deployed with Docker and Kubernetes.</td>
  </tr>
  <tr>
    <td align="center">🔭</td>
    <td><img src="https://skillicons.dev/icons?i=aws" height="40" alt="AWS" /></td>
    <td><b>Now: system design and reliability</b><br />Scalable backend architecture, fault tolerance, and cloud deployment.</td>
  </tr>
</table>

</details>

## 📊 GitHub activity

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com/?user=gnarendra9014-user&background=0D1117&border=30363D&stroke=30363D&ring=3FB950&fire=3FB950&currStreakNum=E6EDF3&sideNums=E6EDF3&currStreakLabel=3FB950&sideLabels=8B949E&dates=8B949E&border_radius=6" />
    <img src="https://streak-stats.demolab.com/?user=gnarendra9014-user&background=FFFFFF&border=D0D7DE&stroke=D0D7DE&ring=1A7F37&fire=1A7F37&currStreakNum=1F2328&sideNums=1F2328&currStreakLabel=1A7F37&sideLabels=656D76&dates=656D76&border_radius=6" width="55%" alt="GitHub contribution streak" />
  </picture>
</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/gnarendra9014-user/gnarendra9014-user/output/github-contribution-grid-snake-dark.svg" />
    <img src="https://raw.githubusercontent.com/gnarendra9014-user/gnarendra9014-user/output/github-contribution-grid-snake.svg" alt="Contribution graph" />
  </picture>
</p>

## 📫 Let's connect

<p align="center">
  Open to software engineering, backend, and QA roles.<br />
  Happy to talk backend engineering, testing, and distributed systems.
</p>

<p align="center">
  <a href="https://gutti-narendra-portfolio.vercel.app/"><img src="https://skillicons.dev/icons?i=vercel" height="44" alt="Portfolio" /></a>
  <a href="https://linkedin.com/in/gnarendra9100"><img src="https://skillicons.dev/icons?i=linkedin" height="44" alt="LinkedIn" /></a>
  <a href="mailto:gnarendra9100@gmail.com"><img src="https://skillicons.dev/icons?i=gmail" height="44" alt="Email" /></a>
</p>

<p align="center"><sub>Code. Debug. Learn. Repeat.</sub></p>
