# Source: https://docs.umami.is/docs/guides/track-form-submissions

Menu

Tracking

# Track form submissions

Copy page

Capture when users submit forms on your website, such as sign-up forms, contact forms, newsletter subscriptions, or checkout flows.

This page covers the Umami implementation. For measurement strategy — form starts versus submissions, abandonment rates, and interpreting the data — see the [form tracking guide](https://umami.is/guides/form-tracking) on the main site.

## Using data attributes[#](https://docs.umami.is/docs/guides/track-form-submissions#using-data-attributes)

For simple forms, add tracking attributes directly to the submit button:

```html
<form action="/subscribe" method="POST">
  <input type="email" name="email" placeholder="Email" />
  <button
    type="submit"
    data-umami-event="form-submit"
    data-umami-event-form="newsletter"
  >
    Subscribe
  </button>
</form>
```

## Using JavaScript for more control[#](https://docs.umami.is/docs/guides/track-form-submissions#using-javascript-for-more-control)

For forms that use JavaScript submission (AJAX, fetch, or framework form handling), call `umami.track()` in your submit handler:

```js
document.querySelector('#contact-form').addEventListener('submit', function (e) {
  umami.track('form-submit', { form: 'contact', source: 'homepage' });
});
```

### React example[#](https://docs.umami.is/docs/guides/track-form-submissions#react-example)

```tsx
function SignupForm() {
  async function handleSubmit(e) {
    e.preventDefault();
    umami.track('form-submit', { form: 'signup', plan: 'free' });

    // Continue with your form submission logic
    await submitToAPI(new FormData(e.target));
  }

  return (
    <form onSubmit={handleSubmit}>
      <input type="email" name="email" required />
      <button type="submit">Sign Up</button>
    </form>
  );
}
```

## Tracking form completions vs. submissions[#](https://docs.umami.is/docs/guides/track-form-submissions#tracking-form-completions-vs-submissions)

If your form spans multiple steps (like a checkout flow), track each step to understand where users drop off:

```js
// Step 1: User enters email
umami.track('checkout-step', { step: 'email' });

// Step 2: User enters payment info
umami.track('checkout-step', { step: 'payment' });

// Step 3: User completes purchase
umami.track('checkout-step', { step: 'complete' });
```

You can then use the [Funnel](https://docs.umami.is/docs/funnel) insight to visualize the drop-off between steps.

## Viewing form data[#](https://docs.umami.is/docs/guides/track-form-submissions#viewing-form-data)

Navigate to **Events** to see submission counts, and **Event data** to break down submissions by form name, source, or any other properties you track.

To measure what percentage of visitors submit a form, create a [Goal](https://docs.umami.is/docs/goals) with the `form-submit` event as the conversion action.

[PreviousTrack file downloads](https://docs.umami.is/docs/guides/track-file-downloads) [NextIdentify logged-in users](https://docs.umami.is/docs/guides/identify-logged-in-users)

On this page