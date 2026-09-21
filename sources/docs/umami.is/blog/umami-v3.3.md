# Source: https://umami.is/blog/umami-v3.3

# Umami v3.3

August 11th, 2026Posted by Mike Cao

![Umami v3.3](https://umami.is/images/blog/image-v3.3.webp)

Today we are releasing Umami v3.3.

With v3.2, we went deep on on-page behavior with heatmaps and made property reporting far more flexible. In v3.3, the focus shifts to two areas: securing access to your analytics with full two-factor authentication, and connecting the dots across a visitor's journey with session identity stitching. Alongside those, there is a steady stream of workflow, performance, and quality improvements throughout the app.

Here are the major changes and who they help most.

## Two-factor authentication

The headline feature in v3.3 is two-factor authentication, available to every Umami user including self-hosters.

You can now secure your account with TOTP-based 2FA using any standard authenticator app. Setup walks you through scanning a QR code (or entering a manual key), and you receive a set of backup codes you can download and store safely. The login flow prompts for your code after your password, with rate limiting on failed attempts to block brute-force attacks.

2FA goes beyond individual accounts. Team owners can require 2FA for all team members, and admins get dedicated security settings pages to manage enforcement across the instance, including the ability to reset 2FA for a user who has lost access to their device.

For **security and platform teams**, especially those self-hosting in regulated or multi-tenant environments, this closes one of the most requested gaps in Umami's account security. For **teams**, org-wide enforcement means you no longer have to rely on every member opting in individually.

![Umami two-factor authentication setup showing QR code and backup codes](https://umami.is/images/blog/screenshot-2fa-setup.webp)

## Session identity stitching

When you identify a visitor with the tracker, Umami now stitches their activity together across the identify boundary.

Previously, a visitor's anonymous activity and their identified activity could end up as separate sessions, breaking the picture of what actually happened. In v3.3, session activity is linked before and after identification, identified session IDs are generated consistently, and the session detail view shows the linked ID so you can see the full journey in one place.

For **product and growth teams**, this makes identified traffic dramatically more useful. You can follow a user from their first anonymous pageview through signup and into their logged-in activity without losing the thread.

![Umami session detail view showing linked identity and stitched activity timeline](https://umami.is/images/blog/screenshot-session-stitching.webp)

## Session and event property filtering

Building on the property reporting work in v3.2, you can now filter directly on session and event properties throughout the app.

This has been one of our longest-standing feature requests. If you attach custom data to your events or sessions, you can now use those values as filters, slicing your traffic by plan type, feature flag, A/B variant, or whatever else you send.

For **analysts**, this turns custom properties from something you report on into something you segment by, which is where their real value lives.

![Umami filter panel showing session and event property filters](https://umami.is/images/blog/screenshot-property-filters.webp)

## Sparklines and dashboard polish

Your websites, links, and pixels tables now show sparklines, giving you an at-a-glance trend for every item without opening it. The queries behind them are optimized so large lists stay fast.

Adding a website has also been streamlined with a new tracking code workflow, so you go straight from creating a site to installing the tracker without hunting through settings.

For **agencies and anyone managing many sites**, sparklines make the overview screens genuinely useful for spotting which properties are moving, not just a list of names.

![Umami websites table with sparkline trend charts for each site](https://umami.is/images/blog/screenshot-sparklines.webp)

## Board cloning

Boards, introduced in v3.1, can now be cloned. Build a board once, then duplicate it as a starting point for another website, client, or team instead of recreating it widget by widget.

For **consultants and teams with repeatable reporting**, this makes boards practical as templates.

## Smarter bounce rate

Bounce rate is now more accurate. A visit only counts as a bounce if it has a single pageview and no custom events, so an engaged visitor who lands on one page and interacts with it is no longer misreported as a bounce. The definition has also been simplified for single-page applications, where the old pageview-based logic didn't reflect reality.

For **SPA owners and anyone tracking custom events**, this means bounce rate finally matches how your site actually works.

## Performance

A significant amount of v3.3 went into query performance behind the scenes:

- Website event queries have been optimized, with query routing improvements for large datasets.
- Session activity and event pages load faster, and raw session writes stay on the primary database when read replicas are enabled, avoiding replication lag issues.

For **high-traffic deployments**, these changes add up to a noticeably snappier experience on the screens you use most.

## Quality of life improvements

As always, there is a long list of smaller improvements:

- **Sessions**: delete individual sessions, full-height session profile modals, and fixes for mobile session views.
- **Data accuracy**: same-domain referrers are no longer saved as external referrers, path-only referrers resolve correctly, organic Facebook traffic is attributed to the right channel, and duplicate property data types are resolved with dominant-type logic.
- **Tracker and domains**: internationalized (punycode) domain support, a TypeScript tracker build, and better handling of `x-forwarded-for` chains with a custom `CLIENT_IP_HEADER`.
- **UI**: themed overlay scrollbars, improved mobile menus and navigation, server-side validation for website names and domains, and a cleaned-up share table.
- **i18n**: Hebrew RTL support, the Iranian Rial (IRR) currency, and updated translations across Spanish, Korean, Russian, German, Persian, European Portuguese, and more.
- **Infrastructure**: the Docker image has been hardened and slimmed down.

## Wrapping up

v3.3 strengthens both ends of Umami: two-factor authentication protects who gets in, while identity stitching and property filtering deepen what you can learn once you are there. Combined with the performance work, this release makes Umami more secure, more accurate, and faster, without adding complexity to the experience.

## Thank you

As always, thank you to everyone using Umami, contributing code, reporting issues, and sharing feedback. This release includes a large amount of community-contributed work, from the 2FA implementation to translations, and we are grateful for all of it.

[Back](https://umami.is/blog)

## Keep reading

[Product updates · Sep 16, 2026Umami v3.4Annotations, MCP support, account API keys, a typed API client, and session property filters for saved segments.](https://umami.is/blog/umami-v3.4) [Product updates · Sep 10, 2026Introducing Umami MCP: Your Analytics, in ConversationConnect your AI assistant to Umami and ask questions about your traffic, events, and conversions. MCP is live on Cloud, with support committed for self-hosting.](https://umami.is/blog/introducing-umami-mcp) [Product updates · Jul 6, 2026Better Boards: New Widgets and CloningBuild richer analytics dashboards with realtime, revenue, UTM, goal, and funnel widgets, then clone them in one click.](https://umami.is/blog/boards-new-widgets-and-cloning)