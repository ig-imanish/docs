# Source: https://umami.is/blog/umami-v2.14.0

# Umami v2.14.0

November 21st, 2024Posted by Mike Cao

![Umami v2.14.0](https://umami.is/images/blog/image-v2.14.webp)

Umami v2.14.0 is here! Introducing a new revenue report, improved dashboard and more.

## Features

### Revenue report

We added a new report that allows you to track revenue. Simply send a custom event with revenue data and it will start tracking. [Learn more](https://umami.is/docs/reports/report-revenue).

![image](https://github.com/user-attachments/assets/51fb6167-8e6f-4638-ac3d-87c20396a47c)

### Improved dashboard

In the dashboard, you are now able to select which websites you want to appear, not just the order. Simply toggle the ones you want visible and the rest will be hidden. If none are toggled then all the websites will appear just like before. We also fixed an issue where you couldn't see all your websites if you had too many. Additionally you can now search for websites on the dashboard edit screen.

![image](https://github.com/user-attachments/assets/4dbee4b3-1529-40ce-adb0-aa5c2976f982)

### Hash based routing support

We now record hashes in URLs for websites that use hashed based routing.

### Redirect to team

Umami now redirects to your last selected team on login.

## Fixes

- Fixed dashboard editing [#3048](https://github.com/umami-software/umami/issues/3048)
- Fixed unknown countries [#3054](https://github.com/umami-software/umami/issues/3054)
- Fixed mobile display issue [#3039](https://github.com/umami-software/umami/issues/3039)
- Fixed wrong events count [#2980](https://github.com/umami-software/umami/issues/2980)
- Fixed display of event properties [#2928](https://github.com/umami-software/umami/issues/2928)
- Fixed session data not deleting [#2915](https://github.com/umami-software/umami/issues/2915)

## Updates

- Language updates (German, French, Russian, Czech, German - Switzerland)
- Added minor version tags to Docker images
- Allow underscores in subdomains
- Added cache control headers for tracker script

See the full [release notes](https://github.com/umami-software/umami/releases/tag/v2.14.0).

[Back](https://umami.is/blog)

## Keep reading

[Product updates · Sep 16, 2026Umami v3.4Annotations, MCP support, account API keys, a typed API client, and session property filters for saved segments.](https://umami.is/blog/umami-v3.4) [Product updates · Sep 10, 2026Introducing Umami MCP: Your Analytics, in ConversationConnect your AI assistant to Umami and ask questions about your traffic, events, and conversions. MCP is live on Cloud, with support committed for self-hosting.](https://umami.is/blog/introducing-umami-mcp) [Product updates · Aug 11, 2026Umami v3.3Two-factor authentication, session identity stitching, property filtering, sparklines, board cloning, and a long list of performance and quality improvements.](https://umami.is/blog/umami-v3.3)