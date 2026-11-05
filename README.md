# Atrigen website

The website of Atrigen, a digital agency in Belgrade. It presents the agency's services, its prices and its work, and runs a blog in Serbian and English.

Live at [atrigen.rs](https://atrigen.rs), in English at [atrigen.rs/en/](https://atrigen.rs/en/).

The code is private. This repository describes the site and the decisions behind it.

## What is on the site

- A page for each of the nine services: websites, AI chatbots, SEO, Google Business Profile, Google ads, Meta ads, CMS, analytics and social media. Each one has a small animated demo built from real HTML, such as a search results page, an ad feed, a map listing or a terminal. Because the demos are text and not pictures, search engines and AI assistants can read them too.
- A price list, a FAQ, a projects page, an about page and a contact form.
- A blog with categories and RSS, with every article in both languages.
- Light and dark themes that follow the system setting and can be switched by hand, with no flash of the wrong theme on load.
- The AtriBot assistant, which answers visitors' questions about services and prices.

## Technical choices

- Astro with TypeScript in strict mode and Tailwind CSS. Every page is static HTML served from Cloudflare Pages. The only server code is a few small functions for the contact form and the newsletter.
- Fonts are self-hosted and cut down to the characters the site actually uses. CSS is inlined in each page, so the first screen does not wait for a stylesheet.
- Each page carries one block of structured data for the organization, the service or the article, and a social preview image generated at build time from the page's own title and description.
- The last-modified date of each page in the sitemap comes from the git history of the files the page is built from, not from the time of the build.
- Serbian and English pages point to each other with hreflang, and changed pages are reported to search engines through IndexNow. A plain-text summary of the agency is published for AI crawlers in llms.txt.
- Analytics loads only after the visitor accepts cookies, and consent is denied by default. The privacy policy lists the cookies that were actually measured on the live site.
- Every number on the site can be backed up with a real client or a dated measurement. Claims that could not be backed up were taken down.

## Stack

Astro, TypeScript, Tailwind CSS, Cloudflare Pages and Pages Functions, D1, Resend, satori and resvg for preview images, Playwright.
