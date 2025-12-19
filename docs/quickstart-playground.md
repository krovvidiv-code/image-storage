# Quickstart: Exploring the Playground

Step into a live production environment. In this guide, you'll learn how to investigate a complex e-commerce application—debugging across logs, metrics, traces, and code—all within minutes.

---

## The Playground Environment

You're connected to a live e-commerce platform running on **AWS EKS** with 19 microservices. It's a high-fidelity simulation complete with real traffic, real errors, and real telemetry.

> [!NOTE]
> To learn more about the underlying architecture, check out [Understanding the Playground Environment](understanding-playground.md).

---

## Step 1: Data Retrieval Basics

The best way to start is by asking for specific data. This helps you get comfortable with the natural language interface and understand what's available.

Try these prompts:

> **"What services are in this environment?"**
> *Resolve AI lists all 19 services, giving you the vocabulary for deeper questions.*

> **"Show me error logs from the payment service in the last hour"**
> *Pulls logs directly from Loki without you needing to write a single line of query syntax.*

<p align="center">
  <img src="https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image4.png" width="600" alt="Prometheus Metrics in Resolve AI">
</p>

---

## Step 2: Correlated Investigations

Debugging is about connecting the dots. Resolve AI excels at jumping between infrastructure, logs, and code so you don't have to.

Try questions that bridge multiple sources:

> **"Show me pod restarts and the errors that caused them"**
> *Links Kubernetes pod events to the specific log errors that preceded the restart.*

> **"What code changes correspond to the recent payment deployment?"**
> *Connects EKS deployment history with Git commits.*

<p align="center">
  <img src="https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image5.png" width="600" alt="Code and Operational Impact">
</p>

---

## Step 3: Complex Diagnostics

Now, treat Resolve AI as a technical partner. Ask the "Why" questions that usually require hours of manual analysis.

> **"Why is the checkout service slow?"**
> *Instead of simple data retrieval, Resolve AI analyzes latency, errors, and resource constraints to find the bottleneck.*

> **"Compare error rates between now and yesterday for the payment service"**
> *Performs a time-based baseline analysis to determine if current behavior is truly anomalous.*

<p align="center">
  <img src="https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image9.png" width="600" alt="Time-based analysis">
</p>

---

## Step 4: Live Incident Analysis

The Playground is "live," meaning it has real-world issues appearing in the **Recent Investigations** panel. Pick a live alert, such as *"AWS MSK consumer lag is high,"* and explore the findings.

<p align="center">
  <img src="https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image15.png" width="700" alt="MSK consumer lag investigation">
</p>

---

## Pro Tips for the Playground

- **Be Specific:** `“Show me payment errors in the last hour”` is more effective than a generic `“show me errors.”`
- **Ask "Why":** Resolve AI is built for diagnostics, not just search.
- **Iterate:** The best investigations are conversations. Follow up on what you find.
- **Use @ Mentions:** Speed up your workflow by @-mentioning services or dashboards.

---

## Ready for Your Own Data?

Once you've explored the Playground, connect your own production environment to start getting real-time insights.

[**→ Quickstart: Connect Your Environment**](quickstart-connect.md)

---

### Need Help?
- **In-App:** Ask `“What can you help me with?”`
- **Support:** [help@resolveai.com](mailto:help@resolveai.com)
