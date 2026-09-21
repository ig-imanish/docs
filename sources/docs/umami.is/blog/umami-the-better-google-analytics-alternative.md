# Source: https://umami.is/blog/umami-the-better-google-analytics-alternative

# Umami - The Better Google Analytics Alternative

April 30th, 2024Posted by Nick Andrews

![Umami - The Better Google Analytics Alternative](https://umami.is/images/blog/image-ga-alternative.webp)

Both businesses and personal users need to understand their website data to gain insights into how their customers, users, and visitors engage with their content. Google Analytics provides these insights into website traffic, but its practices raise concerns about user privacy and data protection. Like most Google products, Google Analytics is free because Google collects all sorts of data and then uses it to make money in its other products, like Google Ads.

This blog post explores how Google Analytics works, the privacy implications regarding the data it collects and how it uses it, and why Umami is a suitable privacy-first alternative.

## How Google Analytics Works

To use Google Analytics, website owners have to first create an account and then add a tracking code to their website. The tracking code collects user behavior data, including the user's IP address, device, browser, and location. Google Analytics uses cookie-based tracking to monitor users across different sessions and to identify unique users. What Data Does Google Analytics Collect? Google Analytics collects various data about a user's behavior on a website. Such as:

1. **User location**: Google Analytics can track a user's location based on their IP address. This allows website owners to see where their visitors are coming from and can help them tailor their content to specific regions.
2. **Device type**: Google Analytics can track the user's device (i.e., desktop, iPhone, tablet, etc). This includes information about the user's operating system, browser, and screen size.
3. **User behavior**: Google Analytics tracks what users do on a website, such as page visits, time on site, and actions they perform (such as filling out a form, clicking a button, etc.). With specific settings enabled, Google Analytics can also track things like scroll depth.
4. **Referral source**: Google Analytics can track how users find the website, whether through a search engine, social media, clicking a link in an email, a paid advertisement, or another website.
5. **Demographic information**: Google Analytics can provide demographic information about users, such as age, gender, and interests.

Google can also source and combine data from other Google services like Search and YouTube and share it back to Google Analytics. Google states in Data Share Settings sections of the Google Analytics docs that, “Google products & services: When you turn this setting ON, Google can access and analyze data to better understand online behavior and trends, and use this data to improve Google products and services.”

## How Does Google Analytics Use This Data?

Google Analytics uses the data it collects on website visitors and creates profiles for them, which advertising can use as targeting criteria in their Google Ads campaigns. For example, if a user is identified as being interested in a particular topic (such as networking software), they may be shown ads related to that topic.

Google can bucket users into two categories: Affinity or In-Market. Affinity means the user is generally interested in a topic, and In-Market suggests the user is in the market to make a purchase. Google aggregates your actions online - not just from your website activity on Google Analytics - to create a profile for you. If a user visits a website about a new Honda, gets directions to the Honda dealership in Google Maps, visits websites about auto financing, and watches YouTube videos about Honda reviews, Google will bucket you as someone in the market to purchase a new car.

Although this type of advertising can work because it is based on the user's interests and behavior, it can feel unsavory that Google is tracking everything you're doing and bucketing you into categories. How would you feel if I stood over your shoulder watching and writing down everything you did, everywhere you went, and then used that information to sell something to you? We probably wouldn't be friends.

There are concerns about this data regarding user privacy, such as:

- Users might not know this data is being tracked
- Users should be informed that this data is being collected
- Users should have to give their consent for their data to be used in this way

Another concern is that the data collected by Google is only sometimes correct, which can lead to false assumptions about users' behavior.

## Privacy Implications of Using Google Analytics

Using Google Analytics raises questions about user consent and control over their personal information. Many users likely don't know the extent of the data collection and the implications of allowing Google Analytics to track their online activity. This lack of transparency and control over personal data goes against privacy and data protection principles.

The potential for data breaches on the information collected by Google Analytics is a concern. Users entrust their browsing behavior and personal details to website owners, who are responsible for safeguarding this data. However, reliance on third-party services like Google Analytics introduces additional security risks that may compromise user privacy.

## What Can Website Owners Do to Protect User Privacy?

Website owners should prioritize transparency and user consent when implementing tracking tools like Google Analytics. Respecting user privacy and providing clear information about what data is being collected can help build trust and foster a more ethical approach to website analytics.

One way to do this is to provide users with a clear and prominent privacy policy that explains what data is collected, why it is collected, and how it is used. Website owners should also give users the option to opt out of data collection if they choose to do so. This typically comes in the form of cookie opt-in/opt-out banners, where users need to click a button to be tracked.

Another option is to use an alternative analytics tool that prioritizes user privacy. Privacy-first website analytics tools, such as Umami, are now commonly available. Umami offers [similar features](https://umami.is/platform) to Google Analytics but with a significantly greater focus on user privacy. Umami is a cookie-free website analytics platform that does not require those annoying opt-in cookie banners.

Umami has two versions: self-hosted and cloud. Both versions allow full data ownership since users can export all their data from Umami anytime. This can provide added security and peace of mind for businesses concerned about data privacy. On the other hand, Google Analytics stores data on Google's servers, which some companies may be uncomfortable with.

## Why Open Source Matters Here

Umami's entire codebase is available on [GitHub](https://github.com/umami-software/umami), allowing for full transparency in how the tool collects and processes data. This openness is the structural difference between Umami and Google Analytics: you don't have to take our word for what happens to your visitors' data, because you can read the code that handles it.

That matters most for individuals and organizations with stringent security requirements, or those operating in regulated industries, where "trust us" isn't an acceptable answer. It also enables extensive customization — users with specific needs can fork the repository and modify the code, which is valuable for businesses that find off-the-shelf solutions lacking.

Umami is free to self-host, giving you complete control over your data and directly addressing the data ownership concerns that come with third-party analytics services. Self-hosting is a good fit for teams with the technical resources to manage their own infrastructure, offering maximum control and potential cost savings.

For those without the technical background or resources to run their own instance, Umami Cloud is available, with a free tier to test it out and paid tiers to scale.

## Umami's Reports

Beyond all the [standard analytics tracking](https://umami.is/platform) capabilities, Umami offers [custom event tracking](https://umami.is/docs/track-events), letting you track specific user interactions like button clicks, form sign-ups, and purchases. We wrote a detailed post comparing the custom event functionality of GA4 and Umami: [Understanding Custom Events - Umami vs. Google Analytics 4](https://umami.is/blog/understanding-custom-events-umami-vs-ga4).

Umami also includes a suite of customizable reports:

- The **Funnel** report helps analyze user paths and optimize conversion rates.
- The **Retention** report visualizes user return rates and engagement over time.
- The **Goals** report allows progress towards key objectives to be set and tracked.
- The **UTM** report measures the effectiveness of marketing campaigns.
- The **Breakdown** report provides advanced data segmentation capabilities.
- The **Journey** report helps visualize and optimize user journeys through the site.

We have [documentation available](https://umami.is/docs/reports) for each report, plus blog posts exploring each one in detail.

There are concerns with Google Analytics regarding user privacy and data protection. Website owners should prioritize transparency and user consent when implementing tracking tools like Google Analytics. Respecting user privacy and providing clear information about what data is being collected and how it is being used can help build trust and foster a more ethical approach to website analytics.

Try [Umami](https://cloud.umami.is/signup?ref=umami-blog) today, which makes it easy to collect, analyze, and understand your web data while maintaining visitor privacy and data ownership.

[Back](https://umami.is/blog)

## Keep reading

[Comparisons · May 25, 2024A Mega List of 60 Google Analytics AlternativesAlternatives to Google Analytics that prioritize user privacy and data ownership.](https://umami.is/blog/a-mega-list-of-google-analytics-alternatives) [Comparisons · May 15, 2024Transitioning from GA4 to Umami - A Marketer's GuideStuck on GA4? We provide an easy to follow guide on how to transition to Umami.](https://umami.is/blog/transitioning-from-ga4-to-umami) [Comparisons · Oct 4, 2024Understanding Custom Events - Umami vs. Google Analytics 4Data can drive improvements in user experience, inform product development roadmaps, and ultimately contribute to business growth.](https://umami.is/blog/understanding-custom-events-umami-vs-ga4)