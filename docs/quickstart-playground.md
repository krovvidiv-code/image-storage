# Quickstart: Playground

This guide will have you investigating a live production environment. By the end, you'll understand how to use Resolve AI to debug across logs, metrics, traces, infrastructure, and code.

## Before You Begin

Make sure you have:

- A Resolve AI account ([sign up here](http://app0.resolve.ai))
- Access to the Playground environment

If you're logged in to a different environment, click your profile in the bottom-left corner, then **Switch to my org → Playground**. If you're already in the playground environment, continue with the steps below.

You're now connected to a live e-commerce application with 19 microservices running on AWS EKS: complete with real traffic, real errors, and real telemetry. Learn more about the application Resolve AI is connected to in [Understanding Playground Environment](understanding-playground.md).

---

## Step 1: Ask Your First Question

The best way to understand what Resolve AI can do is to start with simple questions and build from there. Start by asking Resolve AI to retrieve specific data. These questions help you see what data is available and how to ask for it. Type your first question:

> "What services are in this environment?"

Resolve AI will list the 19 services in the e-commerce platform. This confirms you're connected and gives you the vocabulary for follow-up questions.

Try a few more:

> "Show me error logs from the payment service in the last hour"

> "What's the P95 latency for checkout?"

> "Are there any failing pods?"

This pulls logs from Loki. You'll see the logs filtered by service and time without requiring you to learn specific query or syntax.

![Example: Metrics from Prometheus](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image4.png)

*In this example, Resolve AI pulls metrics from Prometheus. Now you're seeing a different data source in the same natural language interface.*

At this point, you've touched logs, metrics, or infrastructure. You've seen that you can use service names, time ranges, and natural language to get data from the right backend.

---

## Step 2: Run a Simple Investigation

Debugging real production scenarios rarely is restricted to a single domain on a data source. You're constantly jumping between logs, metrics, code, and infrastructure. Explore how Resolve AI retrieves the right information and connects the dots so that you don't have to. Try questions that connect multiple sources:

> "Show me pod restarts and the errors that caused them"

This combines infrastructure state (which pods restarted) with log data (what errors preceded the restart). One question instead of two tabs and manual correlation.

> "What code changes correspond to the recent payment deployment?"

This connects Kubernetes deployment state with Git history. When something breaks after a deployment, this is the question you're actually asking.

> "Look at code and tell me what the latest code change did and its impact."

![Example: Code change and operational impact](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image5.png)

*In this example, Resolve AI goes further. You get the code change and its operational impact in one answer. No more switching between Git and your dashboards.*

> "Show me errors in checkout, the related metrics, and example traces"

This is the observability trifecta: logs tell you what went wrong, metrics tell you how widespread it is, traces tell you where in the request flow it happened. One question, three data sources, correlated.

---

## Step 3: Run a Complex Investigation

Now you're ready to ask harder questions. The kind you ask during actual debugging. These aren't data retrieval requests. They're diagnostic questions that require analyzing patterns, comparing against baselines, and reasoning about root causes.

> "Why is the checkout service slow?"

This isn't a data retrieval question. It's how you actually think during an incident: Is checkout itself slow, or is it waiting on a dependency? Are there errors? Resource constraints? Recent changes? The answer works backward from the symptom.

> "Compare error rates between now and yesterday for the payment service"

![Example: Time-based analysis](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image9.png)

*In this example, you are seeing Resolve AI perform a time-based analysis. You're asking: is this normal, or is something wrong? The answer compares current behavior against a historical baseline.*

> "What changed in the last 6 hours that could affect performance?"

This is open-ended. The kind of question you ask when you don't know where to start. It checks deployments, configuration changes, and infrastructure events, then correlates them with any performance shifts.

> "What services are affected when payment is slow?"

Dependency analysis. When one service degrades, you need to know the blast radius. This maps the impact across the system. Resolve AI maps the impact of a degraded service across the system.

---

## Step 4: Explore How Resolve AI Investigates Incidents

The Playground has real issues to investigate. You might have noticed alerts in the **Recent Investigations** panel, things like "AWS MSK consumer lag is high" or "Frontend error logs above threshold".

These aren't staged. They're actual conditions in the demo environment. Pick one and explore how Resolve AI investigated the incident. Here is an example investigation of the "AWS MSK consumer lag is high" incident.

![MSK consumer lag investigation](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image15.png)

### Other Scenarios to Explore

If you want to simulate common incidents, try:

- **"The payment service is experiencing high error rates. Investigate."**
- **"Customers can't complete checkout. What's wrong?"**
- **"Cart data isn't persisting. Why?"**
- **"Multiple services are experiencing issues. What's the common cause?"**

These are realistic scenarios. Follow the thread wherever it leads.

---

## Pro Tips

- **Be specific:** "Show me payment errors in the last hour" works better than "show me errors."
- **Use service names:** Resolve AI knows all 19 services—use their exact names.
- **Ask "why":** You're not limited to data retrieval. Diagnostic questions work too.
- **Follow up:** The best investigations are conversations. Ask clarifying questions based on what you find.
- **Use @ mentions:** Type @ to reference services or dashboards by name for faster context.

---

## What's Next?

Now that you've learned the basics, connect your own environment:

**→ [Quickstart: Connect Your Environment](quickstart-connect.md):** Set up Resolve AI for your own production systems

---

## Getting Help

- **In Resolve AI**: Check the prompt suggestions or ask "what can you help me with?"
- **Support**: help@resolveai.com or click Help in the sidebar
