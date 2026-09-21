# Source: https://umami.is/blog/introducing-umami-mcp

# Introducing Umami MCP: Your Analytics, in Conversation

September 10th, 2026Posted by Mike Cao

![Introducing Umami MCP: Your Analytics, in Conversation](https://umami.is/images/blog/image-umami-mcp.webp)

You can now connect your AI assistant to Umami and ask questions about your website analytics in plain language.

We've released MCP support on Umami Cloud, with self-hosted support on the way. Ask how traffic changed last week, which pages are getting attention, or where visitors drop out of a signup flow. Your assistant can query Umami for the data and help you work through the answer, with follow-up questions in the same conversation.

## What is MCP?

[Model Context Protocol](https://modelcontextprotocol.io/docs/learn/architecture), or MCP, is an open protocol that lets AI applications connect to external tools and data. Umami's MCP server gives compatible assistants a set of tools for reading your analytics through the Umami API.

Once connected, your assistant can find your websites, request metrics for a date range, and use those results to answer your questions. You don't need to export a spreadsheet or write an API request to get started.

## Start with a question, then follow the data

A weekly traffic review might start with:

> How many visitors did my website get last week, and how does that compare with the previous week?

Then you can narrow the question:

> Break that down by referral source. Which sources sent the most visitors?

> What were the top pages for visitors from those sources?

The useful part is being able to keep going. Each answer gives you a starting point for the next question, whether you're reviewing a campaign, investigating a traffic change, or preparing an update for your team.

## Go beyond pageviews

The shared MCP toolset covers traffic totals, trends, top pages, referrers, channels, campaigns, locations, devices, and realtime activity. It also includes tools for deeper analysis:

- **Events and sessions**: explore custom event totals, trends, and properties, or inspect a session's activity.
- **Conversions**: run a saved funnel or define steps for a question, check saved goals, and explore visitor journeys.
- **Retention and revenue**: query cohort retention, revenue reports, and first- or last-click attribution.
- **Context and performance**: use saved segments and cohorts to filter results, read timeline annotations, and query Core Web Vitals.

For example, you could ask:

> Run my checkout funnel for last month. Where did the largest drop-off happen?

> Which pricing plans did people select in the checkout event last month?

> Which pages have the worst LCP on mobile?

These questions use the data and definitions already in Umami. Event properties, revenue, and performance queries depend on what your website tracks; saved funnels, goals, and annotations provide context when you've configured them.

## Connect to Umami Cloud

Cloud users can connect directly to our hosted MCP endpoint. There is no separate MCP server to deploy.

In your MCP client's connection settings, choose a remote server with Streamable HTTP and enter:

```text
https://cloud.umami.is/mcp
```

Configure bearer authentication with your Cloud API key. If your client asks for an authorization header, use:

```text
Authorization: Bearer YOUR_CLOUD_API_KEY
```

Replace `YOUR_CLOUD_API_KEY` with the complete key, including its `api_` prefix. You can create a key in **Settings → API keys** in Cloud. Copy it when it is created; the full key is only shown once.

Cloud API keys are available with the [Pro plan](https://umami.is/pricing).

Use a client that supports bearer tokens or custom headers. Clients with custom-header support can also send the key using `x-umami-api-key`. Cloud MCP follows the same subscription requirements, API rate limits, and website and team permissions as the Cloud API.

Once connected, try: **“Show my websites.”**

## Self-hosting support

We've also committed MCP support to the open-source Umami repository. To use the remote endpoint, your installation needs a build containing these changes.

MCP is disabled by default on self-hosted instances. Enable it in your deployment environment and restart your instance:

```text
MCP_ENABLED=1
```

Create an API key under **Settings → API keys**, then connect your MCP client to your instance's `/mcp` endpoint:

```text
https://your-umami.example.com/mcp
```

Authenticate with the complete self-hosted API key, including its `umami_` prefix:

```text
Authorization: Bearer YOUR_SELF_HOSTED_API_KEY
```

The remote endpoint uses API keys and respects the key owner's existing permissions. You can revoke the key in Settings to disconnect access.

For clients that run MCP servers locally, we also provide the `@umami/mcp` package with stdio support. See the [MCP package README](https://github.com/umami-software/umami/blob/dev/packages/mcp/README.md) for local configuration examples and the full tool list.

## Read-only access, existing permissions

Every tool exposed by Umami MCP is read-only. The assistant can retrieve analytics and calculate reports, but these tools cannot change your settings, create websites, or delete data.

Requests go through the Umami API and its existing permission checks. Connecting an assistant does not grant access to websites outside your account or team permissions. Query results are returned to the AI application you connect.

## Try it out

MCP is live on [Umami Cloud](https://cloud.umami.is). Connect your assistant, pick a website, and ask a question you normally answer by opening several reports.

We'd love to hear which questions you're asking and what else you'd like to explore. Share your feedback on [GitHub](https://github.com/umami-software/umami) or [Discord](https://discord.gg/4dz4zcXYrQ).

[Back](https://umami.is/blog)

## Keep reading

[Comparisons · Oct 4, 2024Understanding Custom Events - Umami vs. Google Analytics 4Data can drive improvements in user experience, inform product development roadmaps, and ultimately contribute to business growth.](https://umami.is/blog/understanding-custom-events-umami-vs-ga4) [Analytics guides · Aug 15, 2024Optimizing Conversion Paths Using the Funnel ReportUnderstanding conversion paths and user journeys is the first step to optimizing them.](https://umami.is/blog/optimizing-conversion-paths-using-the-funnel-report) [Analytics guides · Aug 20, 2024Understanding Retention AnalysisUnderstanding user behavior goes beyond how users discover and start using your product.](https://umami.is/blog/understanding-retention-analysis)