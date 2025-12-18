# Understanding the Playground Environment

The Playground is a high-fidelity, live e-commerce platform designed to mirror the challenges of modern production systems. It’s where you can build intuition for Resolve AI’s reasoning and data correlation capabilities without high-stakes pressure.

---

## Why Use the Playground?

Production environments are complex and high-stakes. Whether it’s 3 AM during an on-call rotation or a mid-day deployment, you don’t want to be learning a new tool in the heat of an incident. 

The Playground allows you to practice:
- **Natural Language Querying:** Learn what questions Resolve AI can answer.
- **Data Correlation:** See how it links logs, metrics, and code.
- **Root Cause Analysis:** Observe how the AI reasons through distributed system failures.

---

## System Architecture

Behind the storefront is a sophisticated microservices architecture. Customers browse, add to carts, and checkout, while 19 backend services coordinate the experience.

<p align="center">
  <img src="https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image14.jpg" width="800" alt="Playground architecture diagram">
</p>

### Key Service Groups

- **The Shopping Flow:** `product-catalog`, `recommendation`, `cart`, and `checkout`.
- **Business Logic:** `payment`, `fraud-detection`, `accounting`, and `shipping`.
- **Foundational Services:** `currency`, `email`, `quote`, and `ad`.
- **Infrastructure:** `kafka` (via AWS MSK), `valkey-cart` (Redis), and `AWS RDS` (PostgreSQL).

> [!NOTE]
> All services run on **AWS EKS** (us-east-2), with dozens of pods instrumented with **OpenTelemetry**.

---

## The Observability Stack

Resolve AI has deep visibility into the Playground's telemetry. When you ask a question, it queries these backends simultaneously to build a complete picture.

| Telemetry Type | Backend | What Resolve AI Sees |
|:--- | :--- | :--- |
| **Logs** | Loki | Errors, stack traces, and debug events. |
| **Metrics** | Prometheus | CPU/RAM usage, request rates, and P99 latency. |
| **Traces** | Tempo | The full path of a single request across services. |
| **Infrastructure** | K8s API | Pod health, restart counts, and deployment state. |
| **Code** | GitHub | Commit history and specific code changes. |

---

## Life of a Request

Understanding how traffic flows helps you investigate more effectively. Here is the typical path:

1. **Visit:** Request hits the `frontend`.
2. **Browse:** `frontend` → `product-catalog` for data.
3. **Cart:** Items are stored in `cart` (backed by `valkey-cart`).
4. **Checkout:** `checkout` coordinates with `shipping`, `payment`, and `fraud-detection`.
5. **Fulfillment:** `email` confirms the order while `accounting` logs the transaction.

> [!TIP]
> **Cascading Failures:** In the Playground, a slow `payment` service might cause a backup in `checkout`, just like in the real world. Resolve AI is designed to find these causal links.

---

## What to Expect

- **Continuous Traffic:** A load generator ensures there is always data to analyze.
- **Genuine Issues:** Failures aren't scripted; they're the result of real service interactions and occasional simulated chaos.
- **High Availability:** Most services run with multiple replicas to ensure the system stays up even during localized failures.

---

[**Next: Ask Your First Question →**](quickstart-playground.md)
