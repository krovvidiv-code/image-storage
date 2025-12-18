# Getting Started in Less Than a Minute

Resolve AI uses OAuth for authentication. Sign up at [app0.resolve.ai](http://app0.resolve.ai), authorize access, and you're in. The whole process takes less than a minute.

![Sign up flow](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image13.png)

When you first log in, you'll see 2 options:

| Option | Description |
|--------|-------------|
| ![Login options](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image6.png) | **Explore Resolve AI in our playground.** Explore how Resolve AI can help in prod. The playground is designed to mirror the complexity of real production systems: microservices, message queues, caches, databases, intermittent failures, and more. |
| | **Set up Resolve AI for your environment.** Connect your observability stack, infrastructure, code repositories, and team knowledge when you're ready to use Resolve AI for your own production systems. |

We recommend starting with the Playground. It lets you build intuition for what Resolve AI can do without any setup. You can switch to your own environment anytime.

If you're already logged in, you can switch to the Playground anytime via **Change Orgs → Playground** in the menu.

---

## Navigating Resolve AI Homepage

Once you're in, you'll see the main investigation screen with the message: **"What can I help you investigate today?"**

This is where you ask questions. You can use natural language and you needn't learn any query syntax. You can ask about logs, traces, metrics, infrastructure, code, or any combination.

A few things to notice:

### @ Mentions

![@ mentions](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image7.png)

You can type @ to reference services, infrastructure, or dashboards by name. Resolve AI will pull context from whatever you reference.

### Image Uploads

The Image button lets you share screenshots. This is useful if you're looking at a dashboard or error message and want Resolve AI to help interpret it.

### Prompt Suggestions

![Prompt suggestions](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image1.png)

Below the input, you'll see example questions. These adapt to your environment, but they're a good starting point if you're not sure what to ask.

### Recent Investigations

![Recent investigations](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image8.png)

Below the prompt suggestions, you'll see recent alerts and investigations. In the Playground, you might see things like "AWS MSK consumer lag is high" or "Frontend error logs above threshold." These are real issues in the demo environment—you can click into them to explore how Resolve AI investigated these issues or ask Resolve AI about them directly.

### Navigation Menu

![Navigation menu](https://raw.githubusercontent.com/krovvidiv-code/image-storage/main/docs/images/image2.png)

- **New Chat:** Start a fresh investigation.
- **Teams:** Manage how Resolve AI works with your team. Set investigation priorities, add runbooks, and curate which alerts matter.
- **Investigations:** View all past investigations and alerts in one place. Filter by team, time range, or type.
- **Switch to my org:** Jump between Playground and your connected environment.
- **Help:** Access documentation or contact support.

---

## What Resolve AI Does

Resolve AI is AI for prod. It connects to your code, infrastructure, telemetry, and knowledge—then helps you resolve incidents, optimize costs, and ship faster with full production context. Resolve AI:

- **Understands and operates your tools:** Connects to your systems, tools, and code in a few clicks. Works across them to query information or take actions like updating tickets, generating PRs, or writing docs.

- **Combines expertise of your engineers:** Plans investigations, pursues multiple theories in parallel, and coordinates specialized agents to collect evidence across your stack. Builds timelines that link what changed to what broke.

- **Evolves with every interaction:** Learns from your runbooks, wikis, past incidents, and tribal knowledge that usually lives in people's heads. Adapts based on your feedback. Accepts custom instructions for how investigations should run. Gets better the more your team uses it.

---

## How Engineers Use Resolve AI

- **Resolve incidents.** Resolve AI joins your on-call rotation and starts investigating before you do. It pursues multiple hypotheses in parallel, builds causal timelines linking code changes to infrastructure events to telemetry, and surfaces root causes with evidence. It also helps you with fixes like creating code snippets, PRs, post-mortems, and more.

- **Optimize costs.** Engineers use Resolve AI chat interface to discover savings and performance improvements across your infrastructure that would otherwise require dedicated engineering time to find.

- **Ship faster.** When you're building on existing systems, engineers use Resolve AI to get architectural recommendations and implementation guidance with full production context: from system understanding to code.

---

**Next:** [Explore Playground →](quickstart-playground.md)
