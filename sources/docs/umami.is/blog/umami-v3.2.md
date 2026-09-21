# Source: https://umami.is/blog/umami-v3.2

# Umami v3.2

June 24th, 2026Posted by Mike Cao

![Umami v3.2](https://umami.is/images/blog/image-v3.2.webp)

Today we are releasing Umami v3.2.

With v3.1, we expanded Umami into a more complete analytics platform with boards, performance metrics, and session replays. In v3.2, we are going deeper on understanding behavior on the page itself, making property reporting far more flexible, and putting a significant amount of work into security and reliability behind the scenes.

Here are the major changes and who they help most.

## Heatmaps

The headline feature in v3.2 is Heatmaps, now available as a first-class website report.

Click and scroll heatmaps show you exactly where visitors interact with each page, rendered as overlays directly on your site. You can filter by page path, group by screen width to compare responsive layouts, and read depth labels to see how far people actually scroll.

For **product teams and designers**, this closes the gap between "what happened" and "what people saw." You can validate whether a call to action is above the fold, find out if an important link is being ignored, or confirm that a redesign is actually pulling attention where you intended.

For **self-hosters**, heatmap recording and storage are fully supported on your own infrastructure, so you get the same insight without sending data anywhere else.

![Umami heatmap report showing click and scroll overlays on a page](https://umami.is/images/blog/screenshot-heatmaps.webp)

## Session Replay improvements

Session Replay got a round of reliability, filtering, and playback improvements.

You can now use replay filters to find the sessions that matter instead of scrubbing through everything. Playback is smoother, recordings are more reliable with fewer dropped sessions, and the experience on mobile has been cleaned up.

For **support and UX teams**, faster filtering makes replay a practical day-to-day tool for reproducing bugs and investigating drop-off, rather than something you only reach for occasionally.

![Umami session replay list filtered by country, showing duration, actions, location, browser, OS, and device for each session](https://umami.is/images/blog/screenshot-replay-filters.webp)

## Richer event and session property reporting

Property reporting is now much more capable across both event data and session data.

Reports support more data types, including booleans, dates, arrays, and numeric values, with charts to match. Session data gets its own screens with filtering, pivot tables, and property charts, and the property filter UI is now shared across event and session data so the experience is consistent wherever you are. Session property filters have also been optimized for faster queries.

For **analysts and growth teams**, this means you can slice your data the way you actually think about it. Chart a numeric property over time, pivot session attributes against each other, or filter on an array value without exporting to a spreadsheet.

![Umami event and session property reporting with charts and pivot tables](https://umami.is/images/blog/screenshot-property-reports.webp)

## Revenue reporting improvements

Revenue reports have been split into focused APIs and views for better performance and flexibility.

The chart, metrics, stats, and session queries are now separate, there is a new revenue metrics table and metrics bar, and you can switch charts into cumulative mode to see revenue build over a period. The realtime report UI has also been improved.

For **founders and ecommerce teams**, the split into a cleaner metrics table plus cumulative charts makes it easier to connect traffic and behavior directly to dollars, and to do it on data that loads quickly.

## Security hardening

A large part of v3.2 went into security, and it is worth calling out on its own.

Highlights include invalidating authenticated sessions after a password change, validating SSO redirect URLs before setting auth tokens, sanitizing sensitive data in logs, and hiding internal database and Prisma errors from API responses. We also tightened API access checks by website section and share permissions, fixed share-token confusion issues, restricted team owner assignment to admins, enforced team role hierarchy on user changes, sanitized CSV exports against formula injection, and limited batch API payloads.

For **security and platform teams**, especially those self-hosting Umami in regulated or multi-tenant environments, this release meaningfully raises the baseline. These are the kinds of changes that rarely show up in a UI but matter a great deal when you are responsible for the deployment.

## Quality of life improvements

v3.2 also includes a long list of smaller improvements that add up:

- **DataGrid and tables**: a manual table/card view toggle, sorting on non-analytics tables like websites, boards, links, pixels, and teams, horizontal scrolling for wide tables, and stable event chart colors across date range changes.
- **Tracker and API**: a new `data-auto-pageview` attribute to suppress SPA pageview tracking when auto-pageview is disabled, graceful handling of invalid `pushState` URLs, URL query values in the pages report, and configurable internal API URL handling.
- **Sharing**: share page options for filtering and theme enforcement, plus more granular share-token permissions for websites, boards, links, and pixels.

For **developers**, the tracker changes give you finer control over how pageviews are recorded in single-page apps. For **agencies and consultants**, the new share options and per-entity share permissions make it easier to hand clients exactly the right view, and nothing more.

## Wrapping up

v3.2 continues the direction we set with v3 and v3.1: keep Umami simple to use, while giving teams the depth they need when it matters. Heatmaps and richer property reporting help you understand behavior more clearly, the replay and revenue work make existing features more useful day to day, and the security pass strengthens the foundation everything else sits on.

## Thank you

As always, thank you to everyone using Umami, contributing code, reporting issues, and sharing feedback. Your input continues to shape what we build next.

[Back](https://umami.is/blog)

## Keep reading

[Product updates · Sep 16, 2026Umami v3.4Annotations, MCP support, account API keys, a typed API client, and session property filters for saved segments.](https://umami.is/blog/umami-v3.4) [Product updates · Sep 10, 2026Introducing Umami MCP: Your Analytics, in ConversationConnect your AI assistant to Umami and ask questions about your traffic, events, and conversions. MCP is live on Cloud, with support committed for self-hosting.](https://umami.is/blog/introducing-umami-mcp) [Product updates · Aug 11, 2026Umami v3.3Two-factor authentication, session identity stitching, property filtering, sparklines, board cloning, and a long list of performance and quality improvements.](https://umami.is/blog/umami-v3.3)