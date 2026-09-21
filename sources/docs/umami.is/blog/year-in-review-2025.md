# Source: https://umami.is/blog/year-in-review-2025

# A Year in Review 2025

January 5th, 2026Posted by Mike Cao

![A Year in Review 2025](https://umami.is/images/blog/image-2025.webp)

2025 was a defining year for Umami. We shipped 13 releases, closed over 350 issues, merged more than 200 pull requests, and delivered the most ambitious update in our history: Umami v3. Here's a look back at what happened, what it taught us, and where we're headed.

## By the numbers

- **13** official [releases](https://github.com/umami-software/umami/releases)
- **350+** [issues](https://github.com/umami-software/umami/issues) closed
- **200+** [PRs](https://github.com/umami-software/umami/pulls) merged
- A growing list of open source contributors from around the world

## What we shipped

### Umami v3

The headline release of the year. We started 2025 on v2.16.0 and ended it with the long-awaited launch of [Umami v3](https://umami.is/blog/umami-v3). The goal was clear: fewer screens, fewer clicks, and faster access to the data that matters. v3 introduced a more streamlined experience that puts insights front and center.

### Umami Cloud improvements

Behind the scenes, we made significant changes to [Umami Cloud](https://cloud.umami.is) to improve performance, reliability, and security. The most impactful change was a complete redesign of our data collection pipeline to be more fault-tolerant, ensuring we never lose a single event, even during upstream outages.

### Documentation overhaul

We completely revamped our [documentation](https://umami.is/docs) to make it easier to read and navigate. We also split the legacy [v2 documentation](https://v2.umami.is/docs) onto its own site so that self-hosters on older versions still have a clear reference without cluttering the current docs.

## What we learned

### Being an open source company is hard

Balancing community needs with company goals is a constant tension. Our approach has always been to build the best analytics product possible and make it accessible to as many people as possible. That's why we've never gated major features behind Umami Cloud. Every significant feature we shipped in 2025 is available to self-hosters too.

### Your users see what you can't

One of the greatest advantages of building in the open is exposure to use cases you'd never discover on your own. In 2025, community feedback directly shaped features like revenue tracking, channel attribution, pre-send data validation hooks, batch event collection, and in-app data exports. These weren't on our original roadmap. They came from real users solving real problems.

### Move fast, fix things

In late 2025, a serious [React vulnerability](https://nextjs.org/blog/CVE-2025-66478) was discovered that affected many Next.js applications, including Umami. We patched all affected releases and secured our systems quickly.

On top of that, significant [Cloudflare outages](https://blog.cloudflare.com/18-november-2025-outage/) forced us to rethink parts of our infrastructure. We added additional layers of resiliency so that a single provider going down doesn't take Umami Cloud with it. These incidents reinforced a simple principle: assume things will break, and design accordingly.

## What's next

With v3 as a foundation, we can move faster than ever. The next major feature on the roadmap is **Boards**: a way for users to build fully custom dashboards and arrange their data however they want. Think of it as your analytics workspace, tailored to the questions you care about most.

In 2026, we're committed to continuing to build in the open. Whether you're using the product, contributing to the source, or just following along. Thank you. Your feedback directly shapes what we build next.

[Back](https://umami.is/blog)

## Keep reading

[Product updates · Sep 16, 2026Umami v3.4Annotations, MCP support, account API keys, a typed API client, and session property filters for saved segments.](https://umami.is/blog/umami-v3.4) [Product updates · Sep 10, 2026Introducing Umami MCP: Your Analytics, in ConversationConnect your AI assistant to Umami and ask questions about your traffic, events, and conversions. MCP is live on Cloud, with support committed for self-hosting.](https://umami.is/blog/introducing-umami-mcp) [Product updates · Aug 11, 2026Umami v3.3Two-factor authentication, session identity stitching, property filtering, sparklines, board cloning, and a long list of performance and quality improvements.](https://umami.is/blog/umami-v3.3)