# Source: https://umami.is/blog/umami-v2.13.0

# Umami v2.13.0

August 28th, 2024Posted by Nick Andrews

![Umami v2.13.0](https://umami.is/images/blog/image-v2.13.webp)

Umami v2.13.0 is here! This update introduces two new screens called Events and Sessions, the ability to save session data, session profiles, bug fixes, language updates, and more. All the details are right here:

## New Events screen

The Events screen quickly summarizes all of the custom events being recorded for a timeframe you define. It goes without saying that using custom events is a requirement for this screen. Here are some key features of the new Events screen:

- **Centralized Event Information**: We've moved the events chart and metrics table from the overview screen to this dedicated space, making it easier to focus on event-specific data.
- **Activity Stream**: Scrolling down from the Events screen (on the same screen) is a table that displays all your event activity, complete with visitor avatars. This visual representation helps you quickly identify who's (although anonymized) performing specific events.
- **Streamlined Custom Data Access**: The old event data screen has been deprecated. Now, you can access all your custom data under the "Properties" tab on the events screen. This section provides a breakdown of all custom data properties and their values.
- **Enhanced Visibility**: With this new layout, you can more easily track and analyze the performance of your custom events, leading to more informed decision-making.

![image](https://umami.is/images/blog/screenshot-events-screen.webp)

## New Sessions screen

The new Sessions screen summarizes session data. First, there is a weekly breakdown of session data by day and hour. Visual aids (blue circles) help you see which days/hours have a high number of sessions (indicated by a larger blue circle) or a low number of sessions (indicated by a smaller blue circle). Here are some key features of the new Sessions screen: Hourly Traffic Breakdown: Shows you an hourly traffic breakdown during a week. This feature lets you identify your website or app’s busiest times, helping you optimize content delivery and server resources.

![image](https://umami.is/images/blog/screenshot-sessions-screen.webp)

### Visitor Profiles

Clicking on any avatar in the activity stream just below the screen brings up a new page showing details about that particular visitor, including their activity history over time.

![image](https://umami.is/images/blog/screenshot-visitor-profile.webp)

## Save Session Data

We're introducing support for saving session data. This feature works similarly to custom event data and opens up new possibilities for user tracking and analysis: Easy Implementation: Use the identify function from the tracker script to save data about the current session. Saved session data will appear in the new session profile page under Properties.

For example:

```javascript
umami.identify({ email: 'bob@aol.com' });
```

## Bug Fixes and Improvements

Based on your feedback, we're constantly working to improve Umami. In this release, we've addressed several issues:

- Fixed the PORT variable being ignored
- Fixed an issue where the search box was disappearing
- Upgraded NextJS to v14.2.5
- Upgraded Prisma to v5.17.0
- Added the ability for team managers to transfer websites to teams

## Language Updates

We're committed to making Umami accessible to users worldwide. This release includes language updates for:

- Catalan (Spain)
- Korean
- Polish
- Chinese
- German
- Khmer
- Belarusian
- Japanese

We appreciate the contributions of our community in helping to make Umami more inclusive and accessible.

## We Want Your Feedback!

Your input is important to us in shaping the product roadmap of Umami. We would appreciate it if you could take just 30 seconds to fill out this [short survey](https://docs.google.com/forms/d/e/1FAIpQLScHb1vdxMq7e22Sn-X3WWWnGOSdnm37Ouw-4HoPZIahwEZivA/viewform?usp=sf_link). Your feedback helps us prioritize features and improvements that matter most to you. We're excited to see how you'll use these new features to optimize your websites and apps and improve your users' experiences. As always, we're here to support you in your analytics journey. If you have any questions about the new features or need help with any of the new features please contact our support team at [support@umami.is](mailto:support@umami.is).

[Back](https://umami.is/blog)

## Keep reading

[Product updates · Sep 16, 2026Umami v3.4Annotations, MCP support, account API keys, a typed API client, and session property filters for saved segments.](https://umami.is/blog/umami-v3.4) [Product updates · Sep 10, 2026Introducing Umami MCP: Your Analytics, in ConversationConnect your AI assistant to Umami and ask questions about your traffic, events, and conversions. MCP is live on Cloud, with support committed for self-hosting.](https://umami.is/blog/introducing-umami-mcp) [Product updates · Aug 11, 2026Umami v3.3Two-factor authentication, session identity stitching, property filtering, sparklines, board cloning, and a long list of performance and quality improvements.](https://umami.is/blog/umami-v3.3)