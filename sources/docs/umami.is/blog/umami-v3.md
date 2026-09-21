# Source: https://umami.is/blog/umami-v3

# Umami v3

November 6th, 2025Posted by Mike Cao

![Umami v3](https://umami.is/images/blog/image-v3.webp)

Today we are excited to announce the release of Umami v3! This release comes with a new interface, lots of new features and enhancements and lays the groundwork for the future of the application.

## New features and improvements

### Updated UI

We've updated the UI to be more user friendly and help you see all your data at a glance. With the new navigation bar you can quickly see all your website content and even easily switch between websites with the embedded dropdown.

Additionally, all the previous reports have been separated out into individual pages for easier access.

![image](https://umami.is/images/blog/v3-app.webp)

### Improved filters

Filters are now applied universally everywhere in the application via the query string. That means you can copy the URL to share with your team and it will remember what filters were applied.

We've also enhanced the filter form so that you can add and edit multiple filters at once.

![image](https://umami.is/images/blog/v3-filters.webp)

### Segments and cohorts

Segments are a set of filters that you can save to use for later. For example, you can create a segment called _Windows users from the United States_, and apply it to your data via the filter form.

A cohort is a group of users who share a common event or experience during a specific time period, and are then tracked over time. For example, you can create a cohort called _Users who signed up in November_. You can then analyze retention or behavior over time. Just like segments, cohorts can be applied as a filter parameter.

### Links and pixels

Umami v3 introduces two additional elements you can use for tracking, links and pixels. Links are simply short URLs that redirect to another URL. You can use links to measure how often users are clicking on certain links or as download links to a file to see how many downloads it received.

Pixels are invisible images your can embed elsewhere to measure traffic. For example, on external websites where you can't install a website tracker but can post images. You can also embed pixels into your emails to measure open rates, for example in a monthly newsletter to members.

Both links and pixels have their own stats pages just like websites.

### New admin page

There is a new dedicated admin page for admin users. You can view and make changes to all the users, websites and teams in the system.

![image](https://umami.is/images/blog/v3-admin.webp)

### Coming soon

One feature that unfortunately didn't make it into this release was Boards. With boards, you would be able to create your own dashboards and components to display your data however you like. We're still hard at work on it and it will be available in the next release.

## Breaking changes

Umami v3 no longer supports MySQL as a database option, only PostgreSQL. If you want to migrate your data over we've written a [guide](https://docs.umami.is/docs/guides/migrate-mysql-postgresql) to help you migrate.

[Back](https://umami.is/blog)

## Keep reading

[Product updates · Sep 16, 2026Umami v3.4Annotations, MCP support, account API keys, a typed API client, and session property filters for saved segments.](https://umami.is/blog/umami-v3.4) [Product updates · Sep 10, 2026Introducing Umami MCP: Your Analytics, in ConversationConnect your AI assistant to Umami and ask questions about your traffic, events, and conversions. MCP is live on Cloud, with support committed for self-hosting.](https://umami.is/blog/introducing-umami-mcp) [Product updates · Aug 11, 2026Umami v3.3Two-factor authentication, session identity stitching, property filtering, sparklines, board cloning, and a long list of performance and quality improvements.](https://umami.is/blog/umami-v3.3)