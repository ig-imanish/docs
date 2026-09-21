# Source: https://docs.umami.is/docs/links

Menu

Tracking

# Links

Copy page

_Available since v3.0.0_

Umami links monitor and record clicks on specific URLs to show where visitors come from and how they interact with your links. It works by adding a redirect link that captures metrics and data at the time of click. This helps businesses measure campaign performance, identify high-performing channels, and optimize marketing efforts for better conversions.

## Add a link[#](https://docs.umami.is/docs/links#add-a-link)

Log into Umami and click on **Links** in the sidebar.

![image](https://docs.umami.is/images/docs/navbar.png)

Click on the **Add link** button in the top-right corner.

![image](https://docs.umami.is/images/docs/link-add.png)

Fill out the **Name** and **Destination URL**. Two optional sections expand on demand:

- **Customize preview** — controls the social-media preview card shown when the short link is shared on platforms like Facebook, X, LinkedIn, Slack, WhatsApp, Telegram, and Discord. Leave fields empty to auto-detect the title, description and image from the destination URL's Open Graph tags; or fill them in to override.
- **UTM** — appends UTM parameters (`utm_source`, `utm_medium`, `utm_campaign`, `utm_term`, `utm_content`) to the destination URL when the link is clicked, so visits can be attributed in your analytics.

Click the **Save** button.

![image](https://docs.umami.is/images/docs/link-add-form.png)

### Customize preview[#](https://docs.umami.is/docs/links#customize-preview)

When you fill in the **Destination URL**, Umami fetches the destination and detects its Open Graph metadata. The detected values appear as placeholder hints in the **Title**, **Description** and **Image URL** fields, with a small thumbnail preview of the detected image. Type your own value into any field to override; clear it to revert to auto-detection.

![image](https://docs.umami.is/images/docs/link-customize-preview.png)

### UTM parameters[#](https://docs.umami.is/docs/links#utm-parameters)

Track campaign attribution by appending UTM parameters that Umami merges into the destination URL on each click. Existing query parameters on the destination URL are preserved; conflicting UTM keys are overwritten by the link-level values.

![image](https://docs.umami.is/images/docs/link-utm.png)

## Collect data[#](https://docs.umami.is/docs/links#collect-data)

After saving, Umami generates a tracking link (e.g., `https://your-umami-instance/l/abc123`). Use this link instead of the destination URL in your marketing campaigns, emails, social media posts, or anywhere you want to track clicks. When a user clicks the tracking link, they are redirected to the destination URL while Umami records the click.

![image](https://docs.umami.is/images/docs/link-overview.png)

The link overview displays metrics including total clicks, unique visitors, referrer sources, and geographic data.

## Edit or Delete a link[#](https://docs.umami.is/docs/links#edit-or-delete-a-link)

From the **Links** screen click on the **Edit** button to update a link or click on the **Delete** button to delete a link.

![image](https://docs.umami.is/images/docs/link-table.png)

[PreviousTags](https://docs.umami.is/docs/tags) [NextPixels](https://docs.umami.is/docs/pixels)

On this page