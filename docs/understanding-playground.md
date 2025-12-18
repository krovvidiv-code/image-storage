# Understanding Playground Environment

## About the Playground

When you open Resolve AI, you're connected to a live e-commerce platform. This is the Playground—a real application with real traffic, errors, and telemetry where you can learn how Resolve AI works before connecting your own systems.

## Why Do I Need This Playground?

The playground is designed to mirror the complexity of real production systems: microservices talking to each other, message queues, caches, databases, intermittent failures, and the kind of distributed behavior that makes troubleshooting hard in the first place.

Production systems are high-stakes. Whether you are debugging an issue at 3 AM or making changes to any system, you don't want to be learning a new tool simultaneously. The playground environment lets you build intuition for how Resolve AI works *(what questions it can answer, what data it pulls, how it reasons)* before you bring those skills to mission critical workloads.

---

## Architecture of the Playground Environment

The playground is connected to an online store. Customers browse products, add items to carts, check out, pay, and receive confirmation emails. Behind that simple experience are 19 services working together.

![Playground architecture diagram](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image14.jpg)

### Backend Services

**Shopping Flow:**

- **product-catalog** → Shows available products
- **recommendation** → "You might also like..."
- **cart** → Manages shopping cart
- **checkout** → Processes orders

**Supporting Services:**

- **payment** → Processes credit cards
- **fraud-detection** → Catches suspicious orders
- **accounting** → Tracks financials
- **currency** → Converts prices (USD → EUR, etc.)
- **shipping** → Calculates shipping costs
- **email** → Sends order confirmations
- **quote** → Generates price quotes
- **ad** → Displays advertisements
- **image-provider** → Serves product images
- **savedsearches** → Remembers customer searches

### Infrastructure

**Data Storage:**

- **valkey-cart** → Fast cache for cart data (Redis)
- **AWS RDS** → Main database (PostgreSQL)

**Messaging:**

- **kafka + AWS MSK** → Services talk to each other
- **msk-bridge** → Connects to AWS managed Kafka

**Operations:**

- **flagd** → Feature flags (turn features on/off)
- **otel-collector** → Collects all telemetry data
- **load-generator** → Simulates customer traffic

All of this runs on Kubernetes (AWS EKS in us-east-2), with 72 pods distributed across multiple nodes.

### Telemetry

Every service is instrumented with OpenTelemetry, feeding into:

| Data Type | What It Shows | Example Question |
|-----------|---------------|------------------|
| **Logs** (Loki) | What services are doing, errors, debug output | "Show me errors from the payment service in the last hour" |
| **Metrics** (Prometheus) | CPU, memory, request rates, latency percentiles | "What's the p99 latency for checkout?" |
| **Traces** (Tempo) | The path a single request takes across services | "Why did this specific order take 8 seconds?" |
| **Infrastructure** | Pod status, resource usage, deployment state | "Are there any pods crash-looping?" |
| **Code** (Git) | What's deployed and recent changes | "What changed in the last 24 hours?" |

When you ask Resolve AI a question, it can query all of this simultaneously, correlate across data types, and reason about what it finds.

---

## How Traffic Flows Through Playground

Understanding the architecture helps you form the right mental model for troubleshooting. Here's what happens when someone is using the Playground environment:

1. Customer visits website → Request hits frontend-proxy → Routes to frontend
2. Browses products → frontend → product-catalog to show product data
3. Gets recommendations → recommendation suggests related products
4. Adds to cart → cart stores items (cached in valkey-cart)
5. Checks out → checkout coordinates the purchase
6. Processes payment → payment charges card, fraud-detection checks for fraud
7. Calculates shipping → shipping gets delivery cost, currency converts if needed
8. Confirms order → email sends confirmation, accounting records transaction

Services communicate via gRPC and Kafka. When something goes wrong, the failure can cascade. A slow payment service backs up checkout. A crashed recommendation pod might not break purchases but will degrade the experience.

---

## What to Expect

- **Most services run 2 replicas.** Single pod failures shouldn't cause outages—but might cause latency spikes.
- **There's always traffic.** The load generator ensures real request patterns, not empty dashboards.
- **Failures happen.** Services occasionally throw errors, latency varies, and you'll find genuine issues to investigate.

---

## Before You Continue

Take a moment to understand what you're working with:

- This is a microservices architecture with 19 services
- Full observability: logs, metrics, traces, and infrastructure data
- Running on AWS EKS with real Kubernetes resources
- Instrumented with OpenTelemetry

When you ask Resolve AI a question, it has access to all of this. It can query logs, check metrics, trace requests, and examine infrastructure state, then synthesize what it finds into an answer.

Next, you'll learn how to ask your first question.

---

**Next:** [Ask your first question →](quickstart-playground.md)
