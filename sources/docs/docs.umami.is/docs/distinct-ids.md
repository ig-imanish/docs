# Source: https://docs.umami.is/docs/distinct-ids

Menu

Tracking

# Distinct IDs

Copy page

_Available since v2.18.0_

A Distinct ID is a unique identifier assigned to a user, either anonymously or when they log in. This allows you to associate actions (page views, clicks, conversions) with a single user across multiple sessions. For a more extensive way to identify a session, take a look at [Session Data](https://docs.umami.is/docs/tracker-functions#session-data).

## Use Cases[#](https://docs.umami.is/docs/distinct-ids#use-cases)

- Properly attribute user behavior.
- Connect events across multiple sessions or devices.
- Identify repeat users vs. new users.
- Build out journeys and profiles based on user history.

## Usage[#](https://docs.umami.is/docs/distinct-ids#usage)

You can set a Distinct ID using the `umami.identify()` tracker function:

```js
umami.identify('bob@aol.com');
```

The `id` property is the key that sets the Distinct ID.

Or by adding the **id** property to the event payload when using the [Sending stats](https://docs.umami.is/docs/api/sending-stats) API directly:

```json
{
  "payload": {
    "hostname": "your-hostname",
    "language": "en-US",
    "referrer": "",
    "screen": "1920x1080",
    "title": "dashboard",
    "url": "/",
    "website": "your-website-id",
    "id": "bob@aol.com"
  },
  "type": "event"
}
```

The **id** property has a 50 character limit. If your identifiers are longer, consider using a hash or shortened version.

## Session linking[#](https://docs.umami.is/docs/distinct-ids#session-linking)

Setting a Distinct ID does not merge sessions together — each device/browser still gets its own session, identified independently by IP address, user agent, and website ID. Instead, Umami links each session to the Distinct ID.

When you open the profile for any session that has a Distinct ID, Umami automatically looks up every other session linked to that same ID and combines their activity into one timeline, expanding the visible date range to cover all of them. If a visitor is linked to more than one session, the profile shows a **Linked IDs** count so you know you're looking at combined, cross-device activity rather than a single visit.

![image](https://docs.umami.is/images/docs/sessions-linked-ids.png)

## Search[#](https://docs.umami.is/docs/distinct-ids#search)

Navigate to **Sessions** to view visitor activity.

![image](https://docs.umami.is/images/docs/traffic-navbar.png)

Search for a specific **Distinct ID** to view all connected sessions for that time range.

![image](https://docs.umami.is/images/docs/distinct-id-search.png)

[PreviousTrack events](https://docs.umami.is/docs/track-events) [NextTags](https://docs.umami.is/docs/tags)

On this page