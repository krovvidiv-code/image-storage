# Quickstart: Connect Resolve to Your Environment

This guide walks you through connecting Resolve AI to your own production systems. By the end, you'll be investigating your real infrastructure, logs, metrics, and code.

## Before You Begin

Make sure you have:

- A Resolve AI account ([sign up here](http://app0.resolve.ai))
- Access credentials for at least one of your tools (Grafana, Datadog, AWS, etc.)
- Appropriate permissions to create API tokens or service accounts

---

## Step 1: Name Your Organization

After logging in and selecting **Set up Resolve AI for your environment**, you'll be asked to name your organization.

Enter a name that makes sense for your team. Colleagues with the same email domain can join this organization.

![Name your organization](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image10.png)

Click **Continue**.

---

## Step 2: Choose Your Integrations

You'll see the integration screen: **"Give Resolve AI access to your tools."**

Connect at least one tool to start investigating. The more you connect, the more Resolve AI can correlate across your stack.

![Integration selection](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image11.png)

Common integrations include:

### Observability & Alerts

- **Datadog**: logs, metrics, traces, dashboards
- **Grafana**: logs, metrics, alerts, dashboards
- **Elasticsearch**: logs, search
- **Splunk**: logs, metrics, alerts
- **PagerDuty**: incidents, on-call schedules

### Infrastructure

- **AWS**: infrastructure, CloudWatch, resource configuration

### Code

- **GitHub**: repositories, commits, pull requests

### Knowledge & Collaboration

- **Slack:** conversations, context, tribal knowledge
- **Atlassian:** Jira tickets, Confluence docs

**Other integrations include:** Alert Manager, Alert Webhooks, Argus, Azure, GCP, GitLab, Kubernetes, and more.

Click any integration to configure it.

---

## Step 3: Configure Your Integration

Each integration has its own setup flow. Here's what to expect using Grafana as an example:

1. **Name**: Give this connection a name (e.g., "production-grafana" or "us-east-grafana"). Useful if you have multiple instances.

2. **Environments** (optional): Tag this integration with an environment label if you want to organize by prod/staging/dev.

3. **URL**: Enter your instance URL (e.g., https://your-org.grafana.net/).

4. **Credentials**: Depending on the integration, you'll provide an API token, service account, or OAuth connection.

![Configure integration](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image12.png)

Click **Save** when done. You'll see a green checkmark indicating the integration is connected.

> **Need help with a specific integration?** See our [detailed setup guides](https://docs.resolve.ai/setup-and-integrations) for step-by-step instructions, required permissions, and troubleshooting for each tool.

Repeat for any additional integrations you want to connect. You can always add more later.

---

## Step 4: Start Investigating

Once you've connected at least one integration, you'll see the ready screen:

**"Start your first investigation with Resolve AI"**

Your connected integrations are displayed with green checkmarks. Click **Ask your first question** to enter the main interface.

You're now investigating your own production environment.

---

## Step 5: What to Try First

Once you're in, look at the **prompt suggestions** on the home screen. These adapt to your connected integrations. They're a good starting point for exploring what's now available.

Try a few, then follow up based on what you find. Some examples:

> "What integrations are configured?"

> "Show me the most important services and their dependencies"

> "What were the most recent deployments?"

The prompt suggestions will evolve as you connect more tools. If you connect Kubernetes, you'll see infrastructure questions. Connect GitHub, and you'll see code-related prompts. Explore what's there. They're tailored to your environment.

---

## Adding More Integrations Later

You can connect additional tools anytime:

1. Click **Teams** in the sidebar
2. Select your team
3. Go to integration settings
4. Add new integrations

The more you connect, the better Resolve AI can correlate across domains—linking code changes to deployment events to performance metrics to alerts.

---

## Pro Tips

| Tip | Why It Matters |
|-----|----------------|
| **Connect at least two integrations** | One integration retrieves data. Two integrations connect the dots. Pair code + telemetry to link errors to recent commits. Pair infra + telemetry to correlate pod restarts with error spikes. Pair all three to get the full picture. |
| **Use descriptive names** | If you have multiple Grafana instances or AWS accounts, naming them clearly helps later. |
| **Start simple, expand later** | Don't let setup slow you down—connect two integrations now, add more as needed. |

---

## Troubleshooting

### Integration won't connect?

- Check that your API token has the required permissions
- Verify the URL is correct and accessible
- See the [setup guides](https://docs.resolve.ai/setup-and-integrations) for integration-specific requirements

### Don't see your tool?

- Check the full integrations list (scroll past "Common Integrations")
- Contact support if you need an integration we don't yet support

---

## What's Next?

- **→ Working with Teams**: Set up runbooks, alert routing, and team-specific configurations
- **→ [Integration Reference](https://docs.resolve.ai/setup-and-integrations)**: Detailed setup guides for each integration

---

## Getting Help

- **In Resolve AI**: Click Help in the sidebar
- **Support**: help@resolveai.com
