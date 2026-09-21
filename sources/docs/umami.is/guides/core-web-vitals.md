# Source: https://umami.is/guides/core-web-vitals

# Core Web Vitals: What to Measure and How to Improve Them

What LCP, INP, and CLS actually measure, why field data beats lab data, and how to find and fix the pages that are slow for real users.

6 min readUpdated August 2nd, 2026

![Core Web Vitals: What to Measure and How to Improve Them](https://umami.is/images/guides/header-core-web-vitals.webp)

Core Web Vitals are Google's standard metrics for how a page _feels_ to use: how fast it loads, how quickly it responds to input, and how stable it is while rendering. They matter twice over — as a component of Google's page-experience ranking signal, and more directly because slow, janky pages lose visitors regardless of how they were found.

This guide explains what each metric represents, why real-user (field) data is the measurement that counts, and a workflow for finding and fixing your worst pages.

## The metrics

The three Core Web Vitals, with Google's "good" thresholds:

| Metric | What it measures | Good threshold |
| --- | --- | --- |
| **LCP** (Largest Contentful Paint) | Time until the main content is visible | ≤ 2.5s |
| **INP** (Interaction to Next Paint) | Responsiveness to user interactions across the visit | ≤ 200ms |
| **CLS** (Cumulative Layout Shift) | Visual stability — how much content unexpectedly moves | ≤ 0.1 |

Two supplementary metrics are commonly reported alongside them:

| Metric | What it measures | Good threshold |
| --- | --- | --- |
| **FCP** (First Contentful Paint) | Time until the first content appears | ≤ 1.8s |
| **TTFB** (Time to First Byte) | Server response time | ≤ 0.8s |

A note on history: INP replaced First Input Delay (FID) as the responsiveness Core Web Vital in March 2024. If a tool or article still reports FID, it's out of date.

### The 75th percentile

Google evaluates each metric at the **75th percentile (p75)** of real page loads: the experience that 75% of your visitors get _or better_. This is deliberate — averages hide the slow tail, and the median ignores it. When you see "LCP: 2.1s (p75)", it means a quarter of your visitors still waited longer than 2.1 seconds. Track p75, and judge improvements by whether p75 moves.

## Field data versus lab data

There are two ways to measure performance, and confusing them causes endless wasted effort:

- **Lab data** (Lighthouse, WebPageTest) runs your page in a controlled, simulated environment. Perfect for debugging — reproducible, detailed, available before launch — but it describes one hypothetical visit.
- **Field data** (real-user monitoring, or RUM) aggregates measurements from your actual visitors' browsers: their devices, networks, and geographies. This is what Google's ranking signal uses (via CrUX data), and it's the only view that reflects your real audience.

The practical division of labor: use **field data to decide what to fix** and **lab data to figure out how**. A page that scores 95 in Lighthouse on your fiber-connected workstation can still deliver a 5-second LCP to mobile visitors abroad — and only field data will tell you.

## Collecting field data with Umami

Umami can collect Web Vitals from your real visitors. Enable performance tracking by adding the `data-performance` attribute to your tracker script (available from Umami v3.1.0):

```html
<script
  defer
  src="https://your-umami.example.com/script.js"
  data-website-id="your-website-id"
  data-performance="true"
></script>
```

Umami then records LCP, INP, CLS, FCP, and TTFB from real visits. In the **Performance** screen you'll see:

- **Metric cards** with the p75 value for each metric.
- **Score indicators** using Google's thresholds: good, needs improvement, poor.
- **Pages breakdown** — performance per URL.
- **Environment breakdown** — performance by browser, operating system, and device type.

See the [Performance documentation](https://docs.umami.is/docs/performance) for details.

## Segment before you diagnose

Site-wide averages obscure where problems live. Three cuts reveal most issues:

- **By page template.** Your homepage, article pages, and product pages have different layouts, assets, and scripts — and therefore different failure modes. A "site LCP problem" is usually a _template_ LCP problem: one hero image pattern or one embed used across a family of pages.
- **By device.** Mobile hardware and networks are slower; a page comfortably "good" on desktop can be "poor" on mobile. If your traffic is majority mobile, judge yourself on the mobile numbers.
- **By geography.** Visitors far from your servers eat higher TTFB on every request. If a key market shows poor TTFB, that's an infrastructure decision (CDN, edge caching), not a page-code fix.

## Diagnosing and fixing each metric

Once field data has identified the worst pages, use lab tools on those specific pages. The common causes and remedies:

**LCP** — the main content paints late.

- Causes: large unoptimized images, slow server response, render-blocking CSS/JS.
- Fixes: compress images and use modern formats (WebP/AVIF), preload the LCP image, lazy-load only below-the-fold media, reduce TTFB with caching or a CDN.

**INP** — the page reacts sluggishly to clicks and taps.

- Causes: long-running JavaScript tasks, oversized DOM, expensive event handlers.
- Fixes: break up long tasks, defer non-essential scripts, move visual updates to `requestAnimationFrame`, simplify the DOM.

**CLS** — content jumps around while loading.

- Causes: images and embeds without declared dimensions, dynamically injected banners, web fonts swapping in.
- Fixes: always set `width` and `height` on media, reserve space for ads/banners/dynamic content, use `font-display: swap` with metric-compatible fallbacks.

## Performance and business outcomes

Performance work competes for the same engineering time as features, so it needs a business argument. Field data lets you make one — carefully.

You can correlate performance with behavior: compare bounce rates or [conversion rates](https://umami.is/guides/conversion-tracking) between fast and slow segments of the same page, or watch conversion trends after a performance fix ships using a before/after comparison. Industry experience consistently associates faster pages with better engagement, and your own data may show the same pattern.

But be honest about what a correlation shows. Slow experiences cluster on cheap devices and congested networks — audiences that may convert differently for reasons unrelated to speed. "Visitors with good LCP convert 2× more" is _not_ evidence that halving LCP doubles conversion. The clean claim available to you is the before/after one: "we improved p75 LCP from 4.1s to 2.3s on the checkout template; conversion over the following month rose X% against the prior period" — stated as an association, with seasonality and campaigns acknowledged (see [analyzing traffic changes](https://umami.is/guides/website-traffic-analysis)).

## Worked example: a publisher's article template

A publisher enables performance tracking and finds site p75 LCP is 3.9s (poor). The workflow:

1. **Pages breakdown** shows the homepage at 2.2s but article pages clustered around 4.2s — it's a template problem.
2. **Environment breakdown** shows desktop at 2.8s, mobile at 4.9s. The issue is concentrated in mobile article views.
3. **Lab analysis** of one slow article reveals the culprit: a full-width uncompressed hero image (1.8 MB JPEG) that is also the LCP element, plus fonts loading late.
4. **Fixes**: hero images converted to WebP with responsive sizes (~140 KB on mobile), the LCP image preloaded, `font-display: swap` enabled.
5. **Validation**: over the next two weeks, mobile article p75 LCP drops to 2.4s in the field data. Comparing the period before and after, mobile bounce rate on articles declines — reported as an associated improvement, alongside the metric change itself.

The pattern to copy: field data → worst template → worst segment → lab diagnosis → fix → field-data validation.

## Common mistakes

1. **Optimizing for the lab score.** Chasing a Lighthouse 100 on a developer machine while real mobile users still wait 5 seconds. Consequence: effort spent, users unchanged. Remedy: treat field p75 as the scoreboard; use lab tools only to debug pages field data flagged.
2. **Reading averages instead of p75.** A decent average can coexist with a terrible experience for a third of your visitors. Consequence: "performance is fine" while a large minority suffers. Remedy: use p75 (as Umami's metric cards do) and check the breakdowns.
3. **Fixing pages nobody visits.** Sorting by worst score instead of worst score × traffic. Consequence: the slowest page on the site gets fixed; the slightly-slow page with 100× the visits keeps bleeding. Remedy: prioritize by impact — poor metrics on high-traffic templates first.
4. **Claiming causal conversion wins from correlations.** "Fast visitors convert more, therefore speed causes conversion." Consequence: credibility loss when the promised revenue doesn't materialize. Remedy: report before/after associations honestly and control for what else changed in the period.

## Frequently asked questions

### What are the Core Web Vitals?

Google's Core Web Vitals are three metrics measured from real users — Largest Contentful Paint (loading), Interaction to Next Paint (responsiveness), and Cumulative Layout Shift (visual stability). INP replaced First Input Delay as a Core Web Vital in March 2024. FCP and TTFB are useful supplementary metrics but are not Core Web Vitals.

### Why do my scores differ between Lighthouse and real-user monitoring?

Lighthouse is a lab test — one simulated device, one network profile, one run. Real-user monitoring aggregates thousands of actual visits on real devices and connections. Both are useful, but they routinely disagree; a page can score well in the lab and perform badly for your actual mobile audience in another region.

### Do Core Web Vitals affect search rankings?

Google has stated that page experience, including Core Web Vitals, is a ranking signal, though a modest one relative to content relevance. The stronger business case is usually user experience — slow, unstable pages frustrate the visitors you already have — with the ranking benefit as a bonus.

Put this guide into practice.

Umami is a simple, privacy-first analytics platform. Set up tracking in minutes and see your data without the complexity.

[Try Umami Cloud](https://cloud.umami.is/signup?ref=umami-guide-core-web-vitals) [Read the documentation](https://docs.umami.is)

## Related documentation

- [Performance documentation](https://docs.umami.is/docs/performance)
- [Tracker configuration documentation](https://docs.umami.is/docs/tracker-configuration)

## Related guides

[![How to Analyze Changes in Website Traffic](https://umami.is/images/guides/header-website-traffic-analysis.webp)](https://umami.is/guides/website-traffic-analysis)

Marketing analytics5 min read

### [How to Analyze Changes in Website Traffic](https://umami.is/guides/website-traffic-analysis)

A practical method for comparing traffic across time periods, separating real changes from seasonality and measurement artifacts, and finding what actually caused a spike or a drop.

[Read the guide](https://umami.is/guides/website-traffic-analysis)

[![How to Build and Analyze a Conversion Funnel](https://umami.is/images/guides/header-conversion-funnels.webp)](https://umami.is/guides/conversion-funnels)

Behavior and optimization6 min read

### [How to Build and Analyze a Conversion Funnel](https://umami.is/guides/conversion-funnels)

How to design funnel steps, set time windows, interpret drop-off rates, and turn funnel data into changes worth testing.

[Read the guide](https://umami.is/guides/conversion-funnels)