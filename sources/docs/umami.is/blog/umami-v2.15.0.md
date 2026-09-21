# Source: https://umami.is/blog/umami-v2.15.0

# Umami v2.15.0

December 12th, 2024Posted by Mike Cao

![Umami v2.15.0](https://umami.is/images/blog/image-v2.15.webp)

Umami v2.15.0 is here! Improvements to the funnel report, bugfixes and more.

## Features

The funnel report now allows partial matching for URLs. You can add `*` to the start and/or end of the text. In this example, we're seeing if users triggered ANY event with "button" in the name.

![image](https://github.com/user-attachments/assets/ec2abbd9-11a1-48f8-8964-dd92e7e5c14e)

You can now properly search on city, region and country names. Before you had to lookup by ISO codes because that is what is stored in the database.

![image](https://github.com/user-attachments/assets/e9ba4554-346a-4789-a575-0ff15dfc9182)

It even works with localized names.

![image](https://github.com/user-attachments/assets/ba3521e9-5c18-4569-b601-7a19e3750721)

## Fixes

- Fixed unicode characters in location names [#3106](https://github.com/umami-software/umami/issues/3106)
- Fixed `websiteId` missing error [#2614](https://github.com/umami-software/umami/issues/2614)
- Fixed favicon issue with www subdomains [#3073](https://github.com/umami-software/umami/issues/3073)

## Updates

- Language updates: Chinese, Japanese, Norweigan
- Upgraded Next to `v15.0.4`
- Upgraded Prisma to `v5.22.0`

See the full [release notes](https://github.com/umami-software/umami/releases/tag/v2.15.0).

[Back](https://umami.is/blog)

## Keep reading

[Product updates · Sep 16, 2026Umami v3.4Annotations, MCP support, account API keys, a typed API client, and session property filters for saved segments.](https://umami.is/blog/umami-v3.4) [Product updates · Sep 10, 2026Introducing Umami MCP: Your Analytics, in ConversationConnect your AI assistant to Umami and ask questions about your traffic, events, and conversions. MCP is live on Cloud, with support committed for self-hosting.](https://umami.is/blog/introducing-umami-mcp) [Product updates · Aug 11, 2026Umami v3.3Two-factor authentication, session identity stitching, property filtering, sparklines, board cloning, and a long list of performance and quality improvements.](https://umami.is/blog/umami-v3.3)