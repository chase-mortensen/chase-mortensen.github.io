---
title: "Web Vitals 101: The Foundation of Good User Experience"
publishdate: 2022-02-23
lastmod: 2022-02-23
slug: "web-vitals"
description: "Core Web Vitals provide a foundation for good user experience."
keywords: ["web vitals", "user experience", "core web vitals", "javascript", "web performance"]
draft: false
tags: ["site-performance", "user-experience", "web-vitals", "human-centered-design"]
math: false
toc: true
---

This post is an introduction to the [Web Vitals initiative](https://web.dev/vitals/) from Google and why Web Vitals matter for your sites. Most of the content is summarized from Google’s articles on Web Vitals [1] and there are links throughout this article for further reading.

## Part 1: What are Web Vitals and why do they matter?


<video width=100% controls autoplay>
    <source src="/assets/web-vitals/cls.webm" type="video/webm">
    Your browser does not support the video tag.
</video>

Web Vitals are site metrics that measure some critical pillars of user experience. This Google initiative provides universally applicable benchmarks that can help developers focus on areas that have the greatest impact on user experience and site quality. These metrics can change over time.

Web Vitals are important for every site looking to provide a good user experience. A good user experience can make the difference between a one-time visitor leaving the site out of frustration and a regular user. While the user’s experience involves much more than Web Vitals, the metrics provide a solid foundation for a good user experience.

### Core Web Vitals
Out of the Web Vitals, Google has designated 3 metrics as Core Web Vitals. These three measurements are great indicators of loading performance, interactivity, and layout stability [1] - three important building blocks of good user experience.

Here’s a quick [explanation from Google](https://web.dev/vitals/#core-web-vitals) on three of the most important Web Vitals (known as Core Web Vitals):

* “[Largest Contentful Paint (LCP)](https://web.dev/lcp/) measures _loading_ performance. To provide a good user experience, LCP should occur within **2.5 seconds** of when the page first starts loading.” [1]

	LCP "measures when the largest content element in the viewport becomes visible. It can be used to determine when the main content of the page has finished rendering on the screen." [2]

* “[First Input Delay (FID)](https://web.dev/fid/) measures _interactivity_. To provide a good user experience, pages should have a FID of **100 milliseconds** or less.” [1]

	Here's Google's explanation: “FID measures the time from when a user first interacts with a page (i.e. when they click a link, tap on a button, or use a custom, JavaScript-powered control) to the time when the browser is actually able to begin processing event handlers in response to that interaction.” [3]

	* One note with FID - it requires real user data and not lab data. For that reason, [Total Blocking Time (TBT)](https://web.dev/tbt/) is recommended as a substitute for FID in situations where user data is not available.

* “[Cumulative Layout Shift (CLS)](https://web.dev/cls/) measures _visual stability_. To provide a good user experience, pages should maintain a CLS of **0.1.** or less.”  [1]

	“CLS - a  Core Web Vitals metric, measures the instability of content by summing shift scores across layout shifts that don’t occur within 500ms of user input. It looks at how much visible content shifted in the viewport as well as the distance the elements impacted were shifted.” [4]

	The CLS measurement is a little complicated, so I won't get into it here. A score of 0 is ideal, meaning there are no unexpected movements. You can read the full explanation [here](https://web.dev/cls/#layout-shifts-in-detail).

### Other Web Vitals
We’ll focus on the 3 Core Web Vitals, but other Web Vitals include

* [Time to First Byte (TTFB)](https://web.dev/ttfb/)  - “TTFB is a metric that measures the time between the request for a resource and when the first byte of a response begins to arrive.” [5]

* [First Contentful Paint (FCP)](https://web.dev/fcp/)  - “The First Contentful Paint (FCP) metric measures the time from when the page starts loading to when any part of the page’s content is rendered on the screen.” [6]

* [Total Blocking Time (TBT)](https://web.dev/tbt/)  - “TBT measures the total amount of time between First Contentful Paint and Time to Interactive during which the page is blocked from responding to user input”.  [7]

* [Time to Interactive (TTI)](https://web.dev/tti/) - “The TTI metric measures the time from when the page starts loading to when its main sub-resources have loaded and it is capable of reliably responding to user input quickly.” [8] <br>

---

## Part 2: How Can I Check My Web Vitals?
Broadly, there are two ways of [measuring Web Vitals](https://web.dev/vitals-measurement-getting-started/); lab data and real-world data, which is called Real User Monitoring (RUM) data. Ideally, both types of data will be used to check Web Vitals. Keep in mind the following: “There will always be discrepancies between RUM data and lab (or synthetic) data - particularly if the network conditions, device type, or location of the lab environment differs significantly from that of users.” [9]

### Recommended Tools
#### Tools for both RUM data and lab data
1. [PageSpeed Insights](https://pagespeed.web.dev/) - This site is simple and straightforward - enter a URL and it generates a report. It’s not the most comprehensive tool, but it’s easy to use and provides a summary of insights super fast. There are some issues with the site and it does crash fairly often.

2. [CrUX dashboard](https://developers.google.com/web/updates/2018/08/chrome-ux-report-dashboard)  - Both CrUX (Chrome User Experience) dashboard and PageSpeed Insights are based on the Chrome UX Report, so it’s the same data, but the CrUX dashboard feels a little more comprehensive (it includes historical data) than PageSpeed Insights.

#### Tools for Lab Data
1. [Web Vitals Chrome Extension](https://github.com/GoogleChrome/web-vitals-extension)  - “The Web Vitals Chrome extension measures and reports the Core Web Vitals (LCP, FID, and CLS) for a given page. This tool is intended to provide developers with real-time performance feedback as they make code changes.” [9] This has been a useful tool for me as I navigate to different pages of a site and is really fast and easy to use.

2. Lighthouse - Lighthouse is a great tool for measuring various Web Vitals and other important metrics, including accessibility, best practices, and SEO. Lighthouse is located on Chrome in the developer tools.

3.  [WebPageTest](https://webpagetest.org/) - “WebPageTest includes Web Vitals as a part of its standard reporting. WebPageTest is useful for gathering information on Web Vitals under particular device and network conditions.” [9]

### Collecting Real User Monitoring (RUM) Data
One option for collecting your own RUM data is the [`web-vitals` JavaScript library](https://github.com/GoogleChrome/web-vitals) - “`web-vitals` is a small, modular library (~1KB) that provides a convenient API for collecting and reporting each of the field-measurable Web Vitals metrics.” [9] <br><br>

---

## Part 3: Improving Web Vitals
In this section, I’ll go through a few of the most common issues for each of the Core Web Vitals and provide resources that you can use to improve your site.

### [Optimizing Largest Contentful Paint (LCP)](https://web.dev/optimize-lcp/)
LCP measures “when the largest element was rendered.” [2] The types of elements considered for LCP are `<img>`, `<image>` inside of `<svg>`, `<video>`, elements with a background image using `url()`, and “block-level elements containing text nodes or other inline-level text elements children.” [10]

According to Google, LCP is mainly affected by:
* Slow server response times
* Render-blocking JavaScript and CSS
* Resource load times
* Client-side rendering [10]

For tips on fixing LCP, see [this article](https://web.dev/lcp/#how-to-improve-lcp).

### [Optimizing First Input Delay (FID)](https://web.dev/optimize-fid/)
“The main cause of a poor FID is **heavy JavaScript execution**. Optimizing how JavaScript parses, compiles, and executes on your web page will directly reduce FID.” [11]

Methods to improve FID mentioned in that article include:
* Breaking up Long Tasks
* Optimizing your page for interaction readiness
* Using a web worker
* Reducing JavaScript execution time

### [Optimizing Cumulative Layout Shift (CLS)](https://web.dev/optimize-cls/)
According to Google, “Unexpected movement of page content usually happens because resources are loaded asynchronously or DOM elements get dynamically added to the page above existing content. The culprit might be an image or video with unknown dimensions, a font that renders larger or smaller than its fallback, or a third-party ad or widget that dynamically resizes itself.” [12]

[This article](https://web.dev/optimize-cls/) outlines the main factors that affect CLS, including:
* Images without dimensions
* Ads, embeds, and iframes without dimensions
* Dynamically injected content
* Web Fonts causing FOIT/FOUT
* Actions waiting for a network response before updating DOM

## Conclusion
I know this has been an information dump with a ton of links. There is a lot to dig into and it’s easy to get overwhelmed with all of the metrics and tools. If you’re looking at Web Vitals for the first time, just remember the 3 Core Web Vitals - Largest Contentful Paint, First Input Delay, and Cumulative Layout Shift.

If you’re looking to improve your site, take a look at [PageSpeed Insights](https://pagespeed.web.dev/). It provides quick feedback and even suggests ideas for improving your Core Web Vitals. I’d also suggest installing the [Web Vitals Chrome Extension](https://github.com/GoogleChrome/web-vitals-extension). The extension is super easy to use and gain insight from synthetic data.

Web Vitals are an essential tool for developers and UX designers. If our sites don’t provide a good user experience, we risk causing frustration and driving away users. Web Vitals help us build a solid foundation for a good user experience.

What do you think? Let me know at chase@chase-mortensen.dev.

Chase

## Sources
[1] [Web Vitals](https://web.dev/vitals/)

[2] [Optimize Largest Contentful Paint](https://web.dev/optimize-lcp/)



[3] [First Input Delay (FID)](https://web.dev/fid/)

[4] [Optimize Cumulative Layout Shift](https://web.dev/optimize-cls/)

[5] [Time to First Byte (TTFB)](https://web.dev/ttfb/)

[6] [First Contentful Paint (FCP)](https://web.dev/fcp/)

[7] [Total Blocking Time (TBT](https://web.dev/tbt/)

[8] [Time to Interactive (TTI)](https://web.dev/tti/)

[9] [Getting started with measuring Web Vitals](https://web.dev/vitals-measurement-getting-started/)

[10] [Largest Contentful Paint (LCP)](https://web.dev/lcp/)

[11] [Optimize First Input Delay](https://web.dev/optimize-fid/)

[12] [Cumulative Layout Shift (CLS)](https://web.dev/cls/#layout-shifts-in-detail)

### Other Links
[PageSpeed Insights](https://pagespeed.web.dev/)

[CrUX dashboard](https://developers.google.com/web/updates/2018/08/chrome-ux-report-dashboard)

[Web Vitals Chrome Extension](https://github.com/GoogleChrome/web-vitals-extension)

[WebPageTest](https://webpagetest.org/)

[`web-vitals` JavaScript library](https://github.com/GoogleChrome/web-vitals)

[Delay Javascript to Boost Web Vitals Score](https://blog.speedvitals.com/delay-javascript/)


<!-- {{< youtube ZJthWmvUzzc >}} -->



<!-- {{< tweet 1085870671291310081 >}} -->
