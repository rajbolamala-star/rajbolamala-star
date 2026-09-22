<div align="center">

# Hey, I'm Dheeraj 👋

### Backend Software Engineer · Go · Distributed Systems · Cloud-Native Engineering

**I build backend systems designed for the things that eventually go wrong —
traffic spikes, duplicate events, slow queries, retries, partial failures, and production incidents.**

[![GitHub](https://img.shields.io/badge/GitHub-rajbolamala--star-181717?style=for-the-badge\&logo=github)](https://github.com/rajbolamala-star)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Dheeraj_B-0A66C2?style=for-the-badge\&logo=linkedin)](https://linkedin.com/in/dheeraj-b)
[![Email](https://img.shields.io/badge/Email-Let's_Talk-EA4335?style=for-the-badge\&logo=gmail\&logoColor=white)](mailto:dheeraj.backend@yahoo.com)

</div>

---

## `whoami`

```go
package main

import "fmt"

type Engineer struct {
    Name       string
    Focus      []string
    Languages  []string
    Building   string
    Philosophy string
}

func main() {
    me := Engineer{
        Name:      "Dheeraj B",
        Languages: []string{"Go", "Java", "SQL"},
        Focus: []string{
            "Distributed Systems",
            "Backend Architecture",
            "Event-Driven Systems",
            "Performance & Reliability",
        },
        Building:   "systems that stay boring in production",
        Philosophy: "Measure → Understand → Simplify → Scale",
    }

    fmt.Println(me)
}
```

---

## ⚡ What I Do

I’m a backend engineer with **5 years of software engineering experience** building and operating systems across healthcare, aviation, and supply-chain environments.

My work usually lives somewhere between:

```text
API request
    ↓
Go / Java service
    ↓
Kafka event
    ↓
Concurrent processing
    ↓
Redis / PostgreSQL
    ↓
Observability
    ↓
Kubernetes
    ↓
Production
```

I care about what happens **after the happy path ends**:

* What happens when Kafka delivers the same event twice?
* What happens when a worker crashes before committing an offset?
* What happens when PostgreSQL becomes the bottleneck?
* What happens when an API suddenly handles 3× the traffic?
* What happens when a deployment fails halfway through?
* Can we trace a request across multiple services?
* Can the engineer on call understand the failure quickly?

That is the kind of backend engineering I enjoy.

---

## 📈 Engineering Impact

| Challenge               | Result                                                                          |
| ----------------------- | ------------------------------------------------------------------------------- |
| Java → Go modernization | Migrated **3 core backend services**, reducing infrastructure costs by **~20%** |
| API performance         | Reduced average response latency from **~280 ms → <150 ms** under peak load     |
| High-volume services    | Worked on systems processing **100K+ daily transactions**                       |
| Throughput optimization | Improved API throughput by **up to 30%**                                        |
| Database performance    | Reduced query execution time from **~420 ms → ~290 ms**                         |
| Production reliability  | Resolved **5+ high-priority production incidents** through RCA                  |
| Security                | Implemented OAuth2 + RBAC supporting **200+ operators across 50+ warehouses**   |

---

# 🧠 Featured Engineering Projects

These are not tutorial projects. I use them to explore the same problems that appear in real production systems.

## ⚙️ EventMesh

### Distributed Event Processing Platform

[![Repo](https://img.shields.io/badge/View_Repository-EventMesh-181717?style=flat-square\&logo=github)](https://github.com/rajbolamala-star/eventmesh-go)

A production-style distributed event-processing system built around **Go + Kafka**.

```text
                    ┌─────────────┐
                    │   Client    │
                    └──────┬──────┘
                           │
                     POST /v1/events
                           │
                    ┌──────▼──────┐
                    │   Go API    │
                    └──────┬──────┘
                           │
                     Apache Kafka
                           │
                    ┌──────▼──────┐
                    │ Go Workers  │
                    └───┬─────┬───┘
                        │     │
                 ┌──────▼┐   └──────► Redis
                 │Postgres│          Idempotency
                 └────────┘
```

**Engineering problems explored:**

`Consumer Groups` · `At-Least-Once Delivery` · `Idempotency` · `Retries` · `DLQ` · `Replay` · `Offset Management` · `Distributed Tracing`

The platform includes:

* Kafka consumer groups and explicit offset management
* Redis-backed idempotency protection
* PostgreSQL event lifecycle persistence
* Multi-stage retry topics
* Dead-letter queue handling
* DLQ inspection and replay
* OpenTelemetry distributed tracing
* Prometheus metrics
* Structured logs with trace correlation
* Docker + Kubernetes deployment
* k6 performance/load testing

> **Design principle:** duplicates are acceptable; silent event loss is not.

---

## 🧪 LLM Evaluation Service

### Testing AI systems like production software

[![Repo](https://img.shields.io/badge/View_Repository-LLM_Eval_Go-181717?style=flat-square\&logo=github)](https://github.com/rajbolamala-star/llm-eval-go)

LLMs are software dependencies too — and they need tests.

This Go service runs repeatable evaluation suites against LLMs to detect:

```text
Hallucinations
      +
Regressions
      +
Quality Drift
      +
Latency Problems
      +
Unexpected Output
```

### Architecture

```text
Test Suite
    │
    ▼
Concurrent Eval Runner
    │
    ├──────────────► LLM Provider
    │
    ▼
Scoring Pipeline
    │
    ▼
PostgreSQL
    │
    ├── Run History
    ├── Regression Detection
    └── Drift Analysis
```

Supports multiple evaluation strategies including:

`Exact Match` · `Contains` · `Regex` · `Keywords` · `JSON Schema` · `Length` · `Latency`

**Built with:** Go · Gin · PostgreSQL · Prometheus · Docker · Kubernetes

---

## 🚗 RouteBite

### Route-aware backend recommendation engine

[![Repo](https://img.shields.io/badge/View_Repository-RouteBite-181717?style=flat-square\&logo=github)](https://github.com/rajbolamala-star/routebite)

A backend system built around a simple question:

> **“What food can I pick up along my route without adding a huge detour?”**

Instead of simply finding restaurants near a location, RouteBite evaluates restaurants relative to an **active journey**.

```text
Origin ───────────────────────────────► Destination
                 │
                 │ route
                 ▼
        Candidate Restaurants
                 │
                 ▼
        RouteBite Ranking Engine
                 │
        ┌────────┼─────────┐
        ▼        ▼         ▼
      Detour   Rating    Open Now
        │        │         │
        └────────┼─────────┘
                 ▼
            Best Pick
```

The system ranks results using factors such as:

* Detour time
* User preference
* Rating
* Open/closed status
* Convenience
* Route proximity

It also produces **driver-safe voice summaries** so results can be consumed without staring at a screen.

**Built with:** Go · Gin · PostgreSQL · Redis · External APIs

---

# 🛠️ Backend Toolbox

### Languages

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square\&logo=go\&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square\&logo=openjdk\&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-336791?style=flat-square\&logo=postgresql\&logoColor=white)

### Backend & Architecture

![Gin](https://img.shields.io/badge/Gin-008ECF?style=flat-square\&logo=go\&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square\&logo=springboot\&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square\&logo=apachekafka\&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-244C5A?style=flat-square)
![REST](https://img.shields.io/badge/REST-005571?style=flat-square)

### Data

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square\&logo=postgresql\&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square\&logo=mysql\&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square\&logo=redis\&logoColor=white)
![pgvector](https://img.shields.io/badge/pgvector-336791?style=flat-square\&logo=postgresql\&logoColor=white)

### Cloud & Infrastructure

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square\&logo=amazonaws\&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square\&logo=docker\&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square\&logo=kubernetes\&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square\&logo=git\&logoColor=white)

### Observability

![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square\&logo=prometheus\&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square\&logo=grafana\&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-000000?style=flat-square\&logo=opentelemetry\&logoColor=white)

---

# 🧩 How I Think About Backend Systems

```text
Correctness
    ↓
Reliability
    ↓
Observability
    ↓
Performance
    ↓
Scalability
```

Optimizing a service that is not correct is useless.

Scaling a system that cannot be observed is dangerous.

And adding infrastructure before understanding the bottleneck usually makes the system more complicated — not better.

So my usual approach is:

**Measure → Find the bottleneck → Fix the simplest thing → Measure again.**

---

## 🔬 Topics I'm Currently Exploring

```text
├── Advanced Go concurrency
├── Distributed event processing
├── Kafka delivery semantics
├── Idempotent system design
├── High-throughput APIs
├── PostgreSQL performance
├── Kubernetes reliability
├── OpenTelemetry
├── AI-assisted incident response
└── Production LLM evaluation
```

---

## 💼 Experience Snapshot

```text
Optum
└── Software Developer II
    └── Go · Java · Kubernetes · PostgreSQL · Redis

United Airlines
└── Full-Stack Engineer
    └── Java · Spring Boot · Kafka · Angular

PepsiCo
└── Software Engineer
    └── Backend APIs · Go · Java · OAuth2 · SQL
```

My career has progressively moved closer to the problems I enjoy most:

**backend architecture → distributed systems → reliability → performance.**

---

## 🤝 Let's Build Something Reliable

I enjoy conversations about:

**Go** · **Backend Engineering** · **Distributed Systems** · **Kafka** · **System Design** · **Cloud Infrastructure** · **Production Reliability**

If you're building systems where **latency, reliability, scalability, or correctness actually matter**, I'd love to connect.

<div align="center">

### `ship → observe → learn → improve → repeat`

[![LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge\&logo=linkedin)](https://linkedin.com/in/dheeraj-b)
[![Email](https://img.shields.io/badge/Email_Me-EA4335?style=for-the-badge\&logo=gmail\&logoColor=white)](mailto:dheeraj.backend@yahoo.com)

</div>
