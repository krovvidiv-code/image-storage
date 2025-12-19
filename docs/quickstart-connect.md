# Quickstart: Connect Your Environment

This guide walks you through connecting Resolve AI to your production systems. By the end, you'll be investigating your real infrastructure, logs, metrics, and code.

---

## Prerequisites

Before you begin, ensure you have:
- A Resolve AI account ([Sign up here](http://app0.resolve.ai))
- Access credentials for your primary tools (Grafana, Datadog, AWS, etc.)
- Permissions to create API tokens or service accounts

---

## Step 1: Name Your Organization

After logging in and selecting **Set up Resolve AI for your environment**, you'll name your organization.

> [!NOTE]
> Colleagues with the same email domain can automatically join this organization once it's created.

<p align="center">
  <img src="https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image10.png" width="450" alt="Name your organization">
</p>

---

## Step 2: Choose Your Integrations

The integration screen is where you give Resolve AI access to your stack. The more you connect, the more powerful the cross-stack correlations become.

<p align="center">
  <img src="https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image11.png" width="600" alt="Integration selection">
</p>

### Supported Domains

| Category | Popular Tools |
|:---|:---|
| **Observability** | Datadog, Grafana, Elasticsearch, Splunk, PagerDuty |
| **Infrastructure** | AWS (CloudWatch, Resource Config), Azure, GCP, Kubernetes |
| **Code** | GitHub, GitLab |
| **Knowledge** | Slack, Jira, Confluence |

---

## Step 3: Configure Your Integration

Each integration follows a simple, guided flow. Let's look at Grafana as an example:

1. **Name**: (e.g., `prod-grafana`) — Helps distinguish between multiple instances.
2. **Environment**: (Optional) Tag as `production`, `staging`, or `dev`.
3. **Connection Details**: Enter your instance URL and relevant credentials (API token or OAuth).

<p align="center">
  <img src="https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image12.png" width="500" alt="Configure integration">
</p>

> [!IMPORTANT]
> **Need deep technical details?** Check our [Integration Reference](https://docs.resolve.ai/setup-and-integrations) for step-by-step permissions and troubleshooting for every tool.

---

## Step 4: Start Investigating

Once your integrations show a green checkmark, you're ready. Click **Ask your first question** to enter the main interface with your live data.

### Recommended First Steps
Try these prompts to see Resolve AI in action with your systems:

- `“What integrations are configured?”`
- `“Show me the most important services and their dependencies”`
- `“What were the most recent deployments?”`

---

## Pro Tips for Success

> [!TIP]
> **Combine for Context:** Connect at least two integrations (e.g., Code + Telemetry) to unlock the strongest insights, such as linking performance spikes directly to recent commits.

- **Descriptive Naming:** Clear names help when you're managing multiple clusters or cloud accounts.
- **Incremental Setup:** You don't need everything at once. Start with your primary logging and monitoring tools, then expand.

---

## Troubleshooting & Support

- **Connection Failures:** Double-check API permissions and URL accessibility.
- **Missing Tools:** Scroll through the full list or reach out to us if you need a custom integration.

---

[**← Back to Getting Started**](getting-started.md) | [**Next: Working with Teams →**](https://docs.resolve.ai/teams)

---

### Need Help?
- **In-App:** Click **Help** in the sidebar.
- **Support:** Email us at [help@resolveai.com](mailto:help@resolveai.com)
