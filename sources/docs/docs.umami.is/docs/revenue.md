# Source: https://docs.umami.is/docs/revenue

Menu

Analysis

# Revenue

Copy page

_Available since v2.14.0_

Umami Revenue allows you to track financial performance, measure ROI, and identify which pages or products generate the most income. It provides insights into customer behavior, helping optimize revenue sources and improve conversion rates. By linking revenue data with traffic and user behavior, businesses can make informed decisions to boost profitability and plan for future growth.

The insight works by aggregating **Revenue** and **Currency** data across a specified time period.

## Configuring Revenue[#](https://docs.umami.is/docs/revenue#configuring-revenue)

To start collecting revenue data, you will track an event with dynamic data. This can be done through [tracker functions](https://umami.is/docs/tracker-functions#event-data) or [data attributes](https://umami.is/docs/track-events#using-data-attributes). The tracked event must be passed along with the two dynamic data properties `revenue` and `currency`. If a currency code (ISO 4217) is not recognized, the insight will default to `USD`.

### Tracker function[#](https://docs.umami.is/docs/revenue#tracker-function)

```js
umami.track('checkout-cart', { revenue: 19.99, currency: 'USD' });
```

When tracking events, the default properties are included in the payload. This is equivalent to running:

```js
umami.track(props => ({
  ...props,
  name: 'checkout-cart',
  data: {
    revenue: 19.99,
    currency: 'USD',
  },
}));
```

### Data attributes[#](https://docs.umami.is/docs/revenue#data-attributes)

Note

Revenue must be passed as a string while using this method.

```html
<button
  id="checkout-button"
  data-umami-event="checkout-cart"
  data-umami-event-revenue="19.99"
  data-umami-event-currency="USD"
>
  Checkout
</button>
```

## Parameters[#](https://docs.umami.is/docs/revenue#parameters)

| Parameter | Description |
| --- | --- |
| Currency | (required) The currency of the data to be aggregated. |

## Create an insight[#](https://docs.umami.is/docs/revenue#create-an-insight)

### Step 1: Choose a currency[#](https://docs.umami.is/docs/revenue#step-1-choose-a-currency)

![image](https://docs.umami.is/images/docs/revenue-currency.png)

### Step 2: Run insight[#](https://docs.umami.is/docs/revenue#step-2-run-insight)

![image](https://docs.umami.is/images/docs/revenue-details.png)

[PreviousUTM](https://docs.umami.is/docs/utm) [NextAttribution](https://docs.umami.is/docs/attribution)

On this page