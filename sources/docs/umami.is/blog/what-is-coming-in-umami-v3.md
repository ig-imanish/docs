# Source: https://umami.is/blog/what-is-coming-in-umami-v3

# What is Coming in Umami v3

July 25th, 2025Posted by Mike Cao

![What is Coming in Umami v3](https://umami.is/images/blog/image-new-in-v3.webp)

Umami has come a long way from being a simple web analytics app to a more robust analytics platform challenging [Google Analytics](https://marketingplatform.google.com/about/analytics/), [Mixpanel](https://mixpanel.com/) and [Amplitude](https://amplitude.com). We have added many features over the years requested by our users and continue to work with them to define our roadmap.

In this release we are focused on improving the user experience, adding more customization options, and introducing new tools for tracking. We're excited to share what we've been working on!

## New design

One of the main goals of Umami is to be as simple to use as possible. Users should be able to quickly and easily get to the data they want. In v3, we are introducing a more streamlined design with a new sidebar navigation. We plan to add lots more features in the future and needed a design that would scale and be friendly to navigate.

Also, the sidenav now includes a website selector so you can quickly switch between websites.

![image](https://umami.is/images/blog/screenshot-v3-sidenav.webp)

## Reports reworked

With reports, we originally planned on having the primary functionality on the overview page and any extra functionality would exists in separate reports. However this caused a few problems. First, reports felt hidden away and it took too many extra steps to get to your data. Second, reports functionality was too disjointed and didn't follow a standard pattern. In some reports you could filter by certain criteria, others you couldn't, and it was a frustrating experience.

In v3 we are making reports a seamless part of the app. You will be able to click through the different reports as tabs in the application. For example, instead of opening individual goals reports, you can see all your saved goals on one screen. All of your existing reports will be converted to the new system automatically.

![image](https://umami.is/images/blog/screenshot-v3-reports.webp)

## Universal filters

One thing we really wanted to achieve in this release was to provide a consistent experience. So we refactored how filters worked and now they can be applied to any screen in the application.

As you navigate the app, the filters and date range will remain in place, so you can always be in the same context as you explore. Filters are also saved to the query string, so you can bookmark or share the URL with your team.

![image](https://umami.is/images/blog/screenshot-v3-filters.webp)

## Segments

Along with the update to filters, you will have the ability to save a set of filters as a segment. You just give the segment a name and then you can then filter by the saved segment just as you would any other filter.

We're also introducing an improved filter editing experience that will allow you to edit multiple filters at once.

![image](https://umami.is/images/blog/screenshot-v3-filters-edit.webp)

## Cohorts

Along with segments, you will be able to create **cohorts**. In analytics, cohorts are used to group users based on shared characteristics or experiences within a defined time frame, allowing you to track how those users behave over time.

You will be able to create cohorts from the sessions screen by filtering your sessions and saving the group as a cohort. You can then use the cohort as a filter parameter, just like segments.

## Boards

A major new feature we are adding to Umami are custom dashboards. These are customizable views that you create using various visual components like charts, graphs and tables. This allows you to create custom views showing what is important to you and your team.

You'll also be able to share your individual boards via a public URL so you can easily make them available to your team or clients.

![image](https://umami.is/images/blog/screenshot-v3-boards.webp)

## Links and pixels

In v3 we are introducing new tools for tracking, **links** and **pixels**. Currently all tracking is done through the Umami tracking script that you place on your website. However, you may want to track events that happen outside of your website.

With links, you can create custom short URLs that redirect the user to another location. Anytime the link is clicked, Umami will be able to track the event and provide you with the same detailed data. You can distribute your links across social media, through marketing campaigns, or create product links to track downloads.

Additionally, with pixels you can create a custom transparent pixel that you can include on other sites. When the image is loaded, it will collect data automatically.

## Breaking changes

Umami v3 will no longer support MySQL, only PostgreSQL. Supporting multiple databases required too much additional testing and development time and MySQL usage was much lower than PostgreSQL.

## What next?

Umami v3 will be rolled out to Umami Cloud first, followed by an open source release for self-hosting.

[Back](https://umami.is/blog)

## Keep reading

[Product updates · Sep 16, 2026Umami v3.4Annotations, MCP support, account API keys, a typed API client, and session property filters for saved segments.](https://umami.is/blog/umami-v3.4) [Product updates · Sep 10, 2026Introducing Umami MCP: Your Analytics, in ConversationConnect your AI assistant to Umami and ask questions about your traffic, events, and conversions. MCP is live on Cloud, with support committed for self-hosting.](https://umami.is/blog/introducing-umami-mcp) [Product updates · Aug 11, 2026Umami v3.3Two-factor authentication, session identity stitching, property filtering, sparklines, board cloning, and a long list of performance and quality improvements.](https://umami.is/blog/umami-v3.3)