# Source: https://docs.umami.is/docs/guides/track-single-page-apps

Menu

Tracking

# Track a single-page application

Copy page

Single-page applications (SPAs) built with React, Next.js, Vue, Nuxt, Angular, and similar frameworks work with Umami out of the box. The tracker script automatically detects client-side navigation and records page views without any extra configuration.

## Basic setup[#](https://docs.umami.is/docs/guides/track-single-page-apps#basic-setup)

Add the Umami tracker script to your application's `<head>` just like any other website. The script handles both traditional page loads and client-side route changes.

### Next.js (App Router)[#](https://docs.umami.is/docs/guides/track-single-page-apps#nextjs-app-router)

Add the script to your root layout:

```tsx
// app/layout.tsx
export default function RootLayout({ children }) {
  return (
    <html>
      <head>
        <script
          defer
          src="https://your-umami.example.com/script.js"
          data-website-id="your-website-id"
        />
      </head>
      <body>{children}</body>
    </html>
  );
}
```

Alternatively, use the Next.js `Script` component:

```tsx
import Script from 'next/script';

<Script
  src="https://your-umami.example.com/script.js"
  data-website-id="your-website-id"
  strategy="afterInteractive"
/>
```

### React (Vite / Create React App)[#](https://docs.umami.is/docs/guides/track-single-page-apps#react-vite--create-react-app)

Add the script tag to your `index.html`:

```html
<!-- index.html -->
<head>
  <script
    defer
    src="https://your-umami.example.com/script.js"
    data-website-id="your-website-id"
  ></script>
</head>
```

### Vue / Nuxt[#](https://docs.umami.is/docs/guides/track-single-page-apps#vue--nuxt)

For Nuxt, add it to `nuxt.config.ts`:

```ts
export default defineNuxtConfig({
  app: {
    head: {
      script: [
        {
          src: 'https://your-umami.example.com/script.js',
          defer: true,
          'data-website-id': 'your-website-id',
        },
      ],
    },
  },
});
```

For plain Vue with Vite, add the script to `index.html` just like React.

### Angular[#](https://docs.umami.is/docs/guides/track-single-page-apps#angular)

Add the script to `src/index.html`:

```html
<head>
  <script
    defer
    src="https://your-umami.example.com/script.js"
    data-website-id="your-website-id"
  ></script>
</head>
```

## How it works[#](https://docs.umami.is/docs/guides/track-single-page-apps#how-it-works)

Umami's tracker script monitors the browser's History API (`pushState` and `replaceState`) and the `popstate` event. When your SPA navigates to a new route, Umami automatically sends a page view with the updated URL and title.

This means you do **not** need to manually call `umami.track()` for page views in most cases.

## Tracking custom events in components[#](https://docs.umami.is/docs/guides/track-single-page-apps#tracking-custom-events-in-components)

To track button clicks or other interactions within your components, use the [data attributes](https://docs.umami.is/docs/track-events) approach or call `umami.track()` directly:

```tsx
// React example
<button data-umami-event="signup-click" data-umami-event-plan="pro">
  Sign Up
</button>
```

Or with JavaScript:

```tsx
function handleCheckout() {
  umami.track('checkout', { plan: 'pro', price: 29 });
}
```

Troubleshooting

- **Pages not tracked after navigation**: Make sure the tracker script is loaded once in the root layout, not re-added on every route change.
- **Duplicate page views**: Avoid calling `umami.track()` without arguments in `useEffect` or `onMounted` hooks, since the tracker already records navigation automatically.
- **Hash-based routing**: If your app uses hash routing (`/#/page`), Umami tracks these by default. You can disable hash collection with `data-exclude-hash="true"` if needed.

[PreviousTrack outbound links](https://docs.umami.is/docs/guides/track-outbound-links) [NextTrack file downloads](https://docs.umami.is/docs/guides/track-file-downloads)

On this page