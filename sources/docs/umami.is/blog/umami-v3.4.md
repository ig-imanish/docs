# Source: https://umami.is/blog/umami-v3.4

# Umami v3.4

September 16th, 2026Posted by Mike Cao

![Umami v3.4](https://umami.is/images/blog/image-v3.4.webp)

Today we are releasing Umami v3.4.

This release adds context to your charts and new ways to work with your analytics. Annotations help you connect changes in traffic to launches, campaigns, and other milestones. MCP support brings your analytics into AI tools, while account API keys and a typed API client make it easier to build your own integrations.

## Annotations

You can now add dated notes to your website analytics, with markers on the chart to show when something happened.

Mark the day you launched a feature, started a campaign, changed your pricing, or experienced an outage. When you return to your analytics later, that context is there alongside the data. A spike in traffic is much easier to investigate when you can see that it coincided with a newsletter or product announcement.

The notes view lets you add, edit, and delete annotations, browse notes for the current date range or across all dates, and jump to the date of a note.

For teams reviewing performance together, annotations create a shared record of what changed, so the explanation does not depend on someone remembering what happened weeks ago.

## MCP support

Umami v3.4 introduces support for the Model Context Protocol (MCP), letting compatible AI tools query your analytics directly.

You can ask questions like:

- How did traffic this month compare with last month?
- Which channels brought the most visitors to our pricing page?
- Where are visitors dropping off in our checkout funnel?
- Which pages have the worst LCP on mobile?

The tools cover traffic, events, sessions, funnels, goals, journeys, retention, attribution, revenue, and performance metrics. They can also read your annotations and saved segments, giving your AI tool more context when investigating a change.

All MCP tools are read-only and use the Umami API with the same user and team permission checks as the app.

You can connect through a remote MCP endpoint or run the `@umami/mcp` package locally. For self-hosted instances, the remote endpoint is disabled by default; enable it with `MCP_ENABLED=1` and connect using an account API key. Cloud connections use a Cloud API key and follow the Cloud API's subscription requirements.

## Account API keys

Self-hosted users can now create and revoke API keys under **Settings → API keys**.

Give each key a name so you can keep track of the integrations using it. The full key is shown when it is created, so copy it before closing the dialog. If an integration no longer needs access, revoke its key from settings.

API keys provide a way to authenticate scripts, integrations, and remote MCP connections without using a browser login token. Access follows the key owner's existing permissions.

## A typed API client and expanded analytics APIs

For developers, v3.4 adds `@umami/api-client`, a TypeScript client generated from Umami's OpenAPI specification. It provides typed inputs and responses for API operations and supports both Cloud and self-hosted instances.

Analytics endpoints are now organized by website and feature, with GET routes for calculations and dedicated resources for saved funnels and goals. Performance reporting has separate stats, chart, and metrics endpoints, and UTM metrics can be requested by dimension.

Existing report API routes remain available through compatibility handlers, preserving their request and response formats. Saved report IDs and board references are retained. New integrations should use the feature-specific APIs; existing integrations can migrate without an immediate cutover.

## Session property filters in saved segments

Building on the property filtering introduced in v3.3, you can now include session property filters in saved segments.

If you attach properties such as plan type or account tier to a session, you can save that audience and return to it without rebuilding the filters. This makes it easier to compare the behavior of groups that matter to your product or business.

## Quality of life improvements

This release also includes a range of smaller improvements:

- **Visitor identity**: a new `data-distinct-id` tracker attribute lets you supply an identifier directly on the tracking script. Identified sessions are also separated correctly when distinct IDs differ.
- **Filtering**: fixes preserve commas in search values, keep values in sync when operators change, and improve custom page selections and wildcard inputs for goals and funnels.
- **Boards**: fixes for creating a board without a description and handling deleted websites in boards.
- **Mobile and navigation**: improvements to the mobile date picker, pasting two-factor authentication codes, website and team selectors, and the collapsed sidebar.
- **Performance**: PostgreSQL query improvements for visitor counts and session activity.
- **Languages and currencies**: Azerbaijani and Georgian translations, plus support for the Icelandic Króna and New Taiwan Dollar in revenue reporting.

## Thank you

Thank you to everyone using Umami, contributing code, reporting issues, and sharing feedback. Your input helps us improve the everyday analytics experience and build new ways to put your data to work.

[Back](https://umami.is/blog)

## Keep reading

[Product updates · Sep 10, 2026Introducing Umami MCP: Your Analytics, in ConversationConnect your AI assistant to Umami and ask questions about your traffic, events, and conversions. MCP is live on Cloud, with support committed for self-hosting.](https://umami.is/blog/introducing-umami-mcp) [Product updates · Aug 11, 2026Umami v3.3Two-factor authentication, session identity stitching, property filtering, sparklines, board cloning, and a long list of performance and quality improvements.](https://umami.is/blog/umami-v3.3) [Product updates · Jul 6, 2026Better Boards: New Widgets and CloningBuild richer analytics dashboards with realtime, revenue, UTM, goal, and funnel widgets, then clone them in one click.](https://umami.is/blog/boards-new-widgets-and-cloning)