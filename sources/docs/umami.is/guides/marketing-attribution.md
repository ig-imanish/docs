# Source: https://umami.is/guides/marketing-attribution

# Marketing Attribution: First Click, Last Click, and Traffic Sources

How attribution models assign credit for conversions, what referrer and UTM data can and cannot tell you, and how to read attribution reports without fooling yourself.

5 min readUpdated August 2nd, 2026

![Marketing Attribution: First Click, Last Click, and Traffic Sources](https://umami.is/images/guides/header-marketing-attribution.webp)

When a visitor converts, which marketing effort deserves the credit? That's the attribution question, and every analytics report answers it — sometimes explicitly, more often through silent defaults you never chose. Understanding how credit is assigned is the difference between reading your reports and being misled by them.

This guide explains where source data comes from, how first-click and last-click models differ, and the structural limits every attribution report inherits.

## Where traffic-source data comes from

Attribution starts with knowing where each visit originated. There are three raw inputs:

- **Referrer**: the URL of the page the visitor came from, passed by the browser. It identifies the site (`google.com`, `news.ycombinator.com`) but not the campaign, and it's frequently missing — apps, email clients, and privacy features often strip it.
- **UTM parameters**: campaign labels you attach to your own links (`utm_source`, `utm_medium`, `utm_campaign`). Precise and campaign-aware, but only present on links you tagged. See the [campaign tracking guide](https://umami.is/guides/marketing-campaign-tracking) for tagging conventions.
- **Direct**: the absence of both. No referrer, no UTMs. This bucket mixes genuinely direct visits (typed URLs, bookmarks) with every visit whose source information was lost in transit — so-called _dark social_: links shared in chat apps, some native email clients, and other referrer-stripping environments.

A practical consequence: the quality of your attribution is capped by the discipline of your link tagging. Untagged campaign links don't disappear — they leak into direct or generic referrer buckets and quietly credit the wrong channel.

## Attribution models: first click and last click

A single visitor might discover you through a blog post in March, return via a newsletter in April, and finally convert after clicking a retargeting ad in May. An attribution model is the rule that decides which touchpoint gets credit:

- **First-click** gives all credit to the first recorded touchpoint (the blog post). It answers: _what introduces people to us?_ It flatters discovery channels — content, social, PR.
- **Last-click** gives all credit to the final touchpoint before conversion (the ad). It answers: _what closes?_ It flatters bottom-of-funnel channels — branded search, retargeting, email to existing subscribers.

Neither is "correct." They are two projections of the same journey, and the gap between them is itself informative: a channel that dominates first-click but vanishes in last-click is doing discovery work that last-click reporting would tell you to defund.

### Attribution windows

Every model also has a lookback window — how far back a touchpoint can be and still receive credit. A 30-day window and a 7-day window will attribute the same conversion differently if the first touch was three weeks ago. When comparing attribution numbers across tools (or against an ad platform's self-reported conversions), mismatched windows are one of the most common reasons the numbers disagree.

## Running attribution in Umami

Umami's Attribution insight connects traffic sources to a conversion you define:

1. Open your website and go to the **Attribution** insight.
2. Choose the model: **First-Click** or **Last-Click**.
3. Choose the conversion action — a page view (such as `/thank-you`) or an event (such as `purchase`).
4. Run the insight.

The results show which referrers, UTM sources, and channels contributed most conversions under the chosen model. Because switching models is one click, the most useful habit is to run both and compare. Details are in the [Attribution documentation](https://docs.umami.is/docs/attribution).

To go deeper, use the **Breakdown** insight to segment conversions by referrer, UTM campaign, or country — for example, to see which specific sites send converting traffic rather than just traffic.

## Worked example: reading a first/last-click comparison

An agency runs content marketing, a newsletter, and Google Ads for a client whose conversion is a `contact-form` submission. One month's attribution results:

| Channel | First-click conversions | Last-click conversions |
| --- | --- | --- |
| Blog (organic search) | 58 | 12 |
| Newsletter | 15 | 34 |
| Google Ads (branded) | 6 | 31 |
| Direct | 21 | 23 |

Reading this correctly:

- The blog is the dominant _introducer_ — most eventual converters met the brand there — but it rarely closes. Cutting content because last-click shows only 12 conversions would strangle the top of the funnel.
- The newsletter and branded ads are _closers_: they harvest demand that earlier touches created. Their last-click numbers overstate their independent value — branded search in particular mostly catches people already looking for you.
- Direct is stable in both models, which suggests a chunk of untracked journeys. Before drawing finer conclusions, check whether newsletter and social links are consistently tagged.

The defensible recommendation isn't "shift all budget to the newsletter" — it's that the channels work as a system, and the first/last gap quantifies each one's role in it.

## Structural limits to keep in mind

- **Cross-device journeys break the chain.** A visitor who researches on a phone and converts on a laptop appears as two unrelated visitors. Privacy-first analytics (Umami included) does not stitch identities across devices, so multi-device journeys under-credit early touchpoints.
- **Cross-domain hops can reset the source.** If your checkout lives on a different domain, the arrival there may register your own site as the referrer. Keep conversions and their attribution on the same tracked property where possible.
- **Blocked and stripped data is not random.** Tracker-blocking skews by audience — developer-heavy traffic underreports more than average. The missing data biases channel comparisons, not just totals.
- **Attribution is credit assignment, not causation.** A model can only distribute conversions among observed touchpoints. It cannot tell you what would have happened without the channel. When a budget decision is large enough to matter, validate with a holdout or a before/after comparison against a baseline (see [website traffic analysis](https://umami.is/guides/website-traffic-analysis)).

## Common mistakes

1. **Treating last-click reports as the whole truth.** Most tools default to last-click, so discovery channels chronically look unproductive. Consequence: top-of-funnel budget gets cut, and months later the "efficient" closing channels have nothing left to close. Remedy: always read first-click alongside last-click.
2. **Inconsistent campaign tagging.** The same newsletter tagged `email`, `Email`, and untagged across sends splits one channel into three buckets, one of which is "direct." Consequence: no single channel looks big enough to defend. Remedy: a shared UTM convention, enforced before links ship.
3. **Comparing numbers across mismatched windows and models.** Your ad platform's "conversions" (view-through, 30-day, platform-modeled) will never match your analytics' click-based last-click count. Consequence: hours lost reconciling numbers that measure different things. Remedy: state model and window next to every figure.
4. **Overstating causality in reporting.** "Channel X drove 40 conversions" slides easily into "Channel X earned us 40 customers we'd otherwise lack." Consequence: budget reallocations that don't survive contact with reality. Remedy: report attribution as _credited_, and reserve causal language for experiments.

## Frequently asked questions

### Which attribution model should I use?

Use both first-click and last-click, and read them as two perspectives rather than choosing a winner. First-click shows which channels introduce people to you; last-click shows which channels close. If a channel scores well on either, it is contributing.

### Why is so much of my traffic "direct"?

Direct traffic includes everyone whose source could not be determined — typed URLs and bookmarks, but also links from apps, messaging tools, some email clients, and any environment that strips referrer information. Large direct numbers usually mean missing data, not devoted fans.

### Can attribution prove which channel caused a conversion?

No. Attribution assigns credit according to a rule; it observes touchpoints, not causes. A channel can receive credit for conversions that would have happened anyway. Treat attribution as evidence for budget decisions, and use experiments when you need proof.

Put this guide into practice.

Umami is a simple, privacy-first analytics platform. Set up tracking in minutes and see your data without the complexity.

[Try Umami Cloud](https://cloud.umami.is/signup?ref=umami-guide-marketing-attribution) [Read the documentation](https://docs.umami.is)

## Related documentation

- [Attribution documentation](https://docs.umami.is/docs/attribution)
- [UTM report documentation](https://docs.umami.is/docs/utm)
- [Breakdown documentation](https://docs.umami.is/docs/breakdown)

## Related guides

[![How to Measure Marketing Campaign Performance](https://umami.is/images/guides/header-marketing-campaign-tracking.webp)](https://umami.is/guides/marketing-campaign-tracking)

Marketing analytics5 min read

### [How to Measure Marketing Campaign Performance](https://umami.is/guides/marketing-campaign-tracking)

Learn how to track marketing campaigns end to end — from UTM parameters and conversion events to reading the results — so you can prove which channels actually drive outcomes.

[Read the guide](https://umami.is/guides/marketing-campaign-tracking)

[![A Practical Guide to Website Conversion Tracking](https://umami.is/images/guides/header-conversion-tracking.webp)](https://umami.is/guides/conversion-tracking)

Marketing analytics5 min read

### [A Practical Guide to Website Conversion Tracking](https://umami.is/guides/conversion-tracking)

How to define conversions, choose between page-based and event-based tracking, name events well, and calculate conversion rates you can trust.

[Read the guide](https://umami.is/guides/conversion-tracking)

[![How to Analyze Changes in Website Traffic](https://umami.is/images/guides/header-website-traffic-analysis.webp)](https://umami.is/guides/website-traffic-analysis)

Marketing analytics5 min read

### [How to Analyze Changes in Website Traffic](https://umami.is/guides/website-traffic-analysis)

A practical method for comparing traffic across time periods, separating real changes from seasonality and measurement artifacts, and finding what actually caused a spike or a drop.

[Read the guide](https://umami.is/guides/website-traffic-analysis)