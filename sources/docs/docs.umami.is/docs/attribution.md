# Source: https://docs.umami.is/docs/attribution

Menu

Analysis

# Attribution

Copy page

_Available since v2.18.0_

Umami Attribution helps track the effectiveness of marketing channels, measures campaign performance, and identifies which sources drive the most valuable traffic. By linking attribution data with traffic and engagement metrics, businesses can make informed decisions to enhance marketing ROI and drive sustainable growth.

It works by letting you choose a Viewed page or Triggered event to track attribution for, then displays referrer, paid ads, and UTM data through a specific attribution model.

## Models[#](https://docs.umami.is/docs/attribution#models)

| Model | Description |
| --- | --- |
| First-Click | Gives full credit for a conversion to the very first interaction a user had before converting. For example, if a user first found your site through a Google ad, then later returned via a newsletter link and converted, the Google ad gets the credit. |
| Last-Click | Gives full credit for a conversion to the final interaction before converting. Using the same example, the newsletter link gets the credit. |

## Parameters[#](https://docs.umami.is/docs/attribution#parameters)

- `Model`: (required) The attribution model applied to the insight.
- `Type`: (required) Viewed page or Triggered event.
- `Conversion Step`: (required) Viewed page or Triggered event user must hit to count as a conversion.

## Create an insight[#](https://docs.umami.is/docs/attribution#create-an-insight)

### Step 1: Choose a Model, Type, and Conversion step.[#](https://docs.umami.is/docs/attribution#step-1-choose-a-model-type-and-conversion-step)

![image](https://docs.umami.is/images/docs/attribution-model.png)

| Action Type | Description | Example |
| --- | --- | --- |
| Viewed page | The user must reach this specific URL. | `/pricing` |
| Triggered event | The user must generate this specific event. | `checkout-cart` |

### Step 2: Run insight[#](https://docs.umami.is/docs/attribution#step-2-run-insight)

![image](https://docs.umami.is/images/docs/attribution-details.png)

[PreviousRevenue](https://docs.umami.is/docs/revenue) [NextUsing boards](https://docs.umami.is/docs/using-boards)

On this page