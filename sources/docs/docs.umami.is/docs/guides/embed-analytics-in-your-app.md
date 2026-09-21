# Source: https://docs.umami.is/docs/guides/embed-analytics-in-your-app

Menu

Developer

# Embed analytics in your app

Copy page

Use Umami's share URLs and API to embed analytics dashboards or data directly into your own application, internal tools, or client portals.

## Option 1: Embed a share URL in an iframe[#](https://docs.umami.is/docs/guides/embed-analytics-in-your-app#option-1-embed-a-share-url-in-an-iframe)

The simplest approach is to create a share URL and embed it in an iframe.

### Create a share URL[#](https://docs.umami.is/docs/guides/embed-analytics-in-your-app#create-a-share-url)

1. Navigate to your website in Umami.
2. Click **Edit** on the website.
3. Go to the **Share URL** section and create a new share.
4. Copy the generated URL.

### Embed in your app[#](https://docs.umami.is/docs/guides/embed-analytics-in-your-app#embed-in-your-app)

```html
<iframe
  src="https://your-umami.example.com/share/abc123/My-Website"
  style="width: 100%; height: 800px; border: none;"
  loading="lazy"
></iframe>
```

For this to work, you may need to configure the `ALLOWED_FRAME_URLS` environment variable on your Umami instance to allow your app's domain:

```dotenv
ALLOWED_FRAME_URLS="https://your-app.example.com"
```

## Option 2: Use the API to build custom dashboards[#](https://docs.umami.is/docs/guides/embed-analytics-in-your-app#option-2-use-the-api-to-build-custom-dashboards)

For full control over the presentation, use the Umami API to fetch data and render it in your own UI.

### Authentication[#](https://docs.umami.is/docs/guides/embed-analytics-in-your-app#authentication)

For self-hosted instances, get a token:

```js
const response = await fetch('https://your-umami.example.com/api/auth/login', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({ username: 'admin', password: 'your-password' }),
});
const { token } = await response.json();
```

Use the token in the `Authorization` header:

```js
const headers = { Authorization: `Bearer ${token}` };
```

For Umami Cloud, use your [API key](https://docs.umami.is/docs/cloud/api-key) as the Bearer credential instead:

```js
const apiKey = 'your-api-key';
const headers = { Authorization: `Bearer ${apiKey}` };
```

### Fetch website stats[#](https://docs.umami.is/docs/guides/embed-analytics-in-your-app#fetch-website-stats)

```js
const stats = await fetch(
  `https://your-umami.example.com/api/websites/${websiteId}/stats?startAt=${startAt}&endAt=${endAt}`,
  { headers }
).then(r => r.json());

// stats = { pageviews, visitors, visits, bounces, totaltime }
```

### Fetch page view time series[#](https://docs.umami.is/docs/guides/embed-analytics-in-your-app#fetch-page-view-time-series)

```js
const pageviews = await fetch(
  `https://your-umami.example.com/api/websites/${websiteId}/pageviews?startAt=${startAt}&endAt=${endAt}&unit=day`,
  { headers }
).then(r => r.json());
```

### Render with any charting library[#](https://docs.umami.is/docs/guides/embed-analytics-in-your-app#render-with-any-charting-library)

Use the returned data with Chart.js, Recharts, D3, or any visualization library:

```tsx
import { BarChart, Bar, XAxis, YAxis } from 'recharts';

function PageviewsChart({ data }) {
  return (
    <BarChart data={data.pageviews}>
      <XAxis dataKey="x" />
      <YAxis />
      <Bar dataKey="y" fill="#8884d8" />
    </BarChart>
  );
}
```

## Option 3: Use the API client[#](https://docs.umami.is/docs/guides/embed-analytics-in-your-app#option-3-use-the-api-client)

The [Umami API client](https://docs.umami.is/docs/api/api-client) simplifies authentication and provides typed methods:

```js
import { getClient } from '@umami/api-client';

// Configure via environment variables:
//   UMAMI_API_CLIENT_USER_ID
//   UMAMI_API_CLIENT_SECRET
//   UMAMI_API_CLIENT_ENDPOINT
// or, for Umami Cloud:
//   UMAMI_API_KEY
const client = getClient();

// Methods return { ok, data, status, error }
const { data } = await client.getWebsiteStats(websiteId, {
  startAt: Date.now() - 86400000,
  endAt: Date.now(),
});
```

See the [API reference](https://docs.umami.is/docs/api) for all available endpoints.

[PreviousSet up A/B testing with tags](https://docs.umami.is/docs/guides/setup-ab-testing) [NextSend server-side events](https://docs.umami.is/docs/guides/send-server-side-events)

On this page