<div align="center">

# Awesome Cloudflare Turnstile Solvers [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of tools, libraries, APIs, and research for solving, integrating, and understanding **Cloudflare Turnstile** and the Cloudflare interstitial ("Just a moment") challenge.

<sub>Maintained by <a href="https://peak.fo/?utm_source=github&utm_medium=readme&utm_campaign=awesome&utm_content=awesome-turnstile-solvers">Peak</a>, a Cloudflare Turnstile solving API. Peak is listed below with the other services; contributions of any tool, open or commercial, are welcome. See <a href="#contributing">Contributing</a>.</sub>

</div>

---

Cloudflare Turnstile is the CAPTCHA-style widget that returns a `cf-turnstile-response` token, validated server-side through `siteverify`. The Cloudflare interstitial challenge (the "Just a moment" / 5-second page) is the JavaScript wall that issues a `cf_clearance` cookie. This list covers both: the services that solve them, the open-source libraries that wrap those services, the framework integrations, and the research on how the challenge actually works.

## Contents

- [Solving services (APIs)](#solving-services-apis)
- [Open-source libraries and integrations](#open-source-libraries-and-integrations)
- [Framework guides](#framework-guides)
- [Understanding Turnstile](#understanding-turnstile)
- [Contributing](#contributing)

## Solving services (APIs)

Hosted APIs that take a sitekey and page URL and return a valid token. Prices are approximate list rates for Cloudflare Turnstile as advertised in 2026 and change over time; confirm before you rely on a number. All of these bill only for successful solves.

- **[Peak](https://peak.fo/?utm_source=github&utm_medium=readme&utm_campaign=awesome&utm_content=awesome-turnstile-solvers)** — Cloudflare specialist (Turnstile and the 5s challenge). One API call returns the token in about a second, with a proxy or without. From $0.90 per 1,000, pay per success, 1,000 free solves to start with no card. [Docs](https://peak.fo/docs/turnstile). *(This list's maintainer.)*
- **[CapSolver](https://www.capsolver.com/)** — General anti-bot solver covering many CAPTCHA types, with a browser extension and SDKs.
- **[CapMonster Cloud](https://capmonster.cloud/)** — General solving API, pay per solved CAPTCHA, with SDKs and a dashboard.
- **[2Captcha](https://2captcha.com/)** — Long-running solving service with support across many CAPTCHA types and SDKs in most languages.
- **[Anti-Captcha](https://anti-captcha.com/)** — General CAPTCHA-solving API with client libraries.
- **[NSLSolver](https://nslsolver.com/)** — Turnstile and challenge solver with REST API and multiple SDKs.
- **[EzCaptcha](https://www.ezcaptcha.com/)** — Solving API with a developer AppID revenue-share program.
- **[NextCaptcha](https://nextcaptcha.com/)** — Turnstile and reCAPTCHA solving API.
- **[Bright Data Web Unlocker](https://brightdata.com/products/web-unlocker)** — Proxy-plus-unlock product that renders and solves challenges as part of returning clean HTML.

## Open-source libraries and integrations

Drop-in libraries and framework plugins. Several call a solving API under the hood.

**Python**

- [cloudscraper-turnstile](https://github.com/CircuitSavage/cloudscraper-turnstile) — `cloudscraper` drop-in that actually solves Turnstile and the 5s challenge (via the Peak API).
- [scrapy-turnstile](https://github.com/CircuitSavage/scrapy-turnstile) — Scrapy middleware that solves Turnstile inline so blocked spiders keep running.
- [playwright-turnstile](https://github.com/CircuitSavage/playwright-turnstile) — Token injection for Playwright, works headless on datacenter IPs.
- [selenium-turnstile](https://github.com/CircuitSavage/selenium-turnstile) — Injects a valid token in Selenium, no physical click.
- [turnstile-curl](https://github.com/CircuitSavage/turnstile-curl) — Solve Turnstile from `curl_cffi` with no browser.
- [crawl4ai-turnstile](https://github.com/CircuitSavage/crawl4ai-turnstile) — Turnstile solving for Crawl4AI crawls.
- [Theyka/Turnstile-Solver](https://github.com/Theyka/Turnstile-Solver) — Browser-automation Turnstile solver.
- [sarperavci/CloudflareBypassForScraping](https://github.com/sarperavci/CloudflareBypassForScraping) — Bypass toolkit for the Cloudflare interstitial.

**Node.js**

- [puppeteer-extra-plugin-turnstile](https://github.com/CircuitSavage/puppeteer-extra-plugin-turnstile) — `puppeteer-extra` plugin that auto-solves Turnstile by reading the sitekey off the page.

## Framework guides

Practical write-ups on getting past Turnstile in common stacks.

- [Solving Cloudflare Turnstile in 2026 — a developer's guide](https://blog.peak.fo/how-to-solve-cloudflare-turnstile-in-2026-dev-guide/)
- [How to find a Cloudflare Turnstile sitekey](https://blog.peak.fo/how-to-find-a-cloudflare-turnstile-sitekey/)
- [Cloudflare Turnstile 403: why your scraper is blocked](https://blog.peak.fo/cloudflare-turnstile-403-scraper-fix/)
- [Handling Turnstile in Playwright and Puppeteer](https://blog.peak.fo/handling-turnstile-in-playwright-and-puppeteer/)
- [How to scrape Cloudflare-protected sites without getting blocked](https://blog.peak.fo/how-to-scrape-cloudflare-protected-sites-without-getting-blocked/)

## Understanding Turnstile

How the challenge works under the hood, for research and defense.

- [cloudflare-turnstile-reversed](https://github.com/CircuitSavage/cloudflare-turnstile-reversed) — A sourced teardown of how Turnstile fingerprints and scores browsers, plus the widget parameters, the token, and the `siteverify` flow. Every claim is cited or tagged observed / inferred.
- [What is Cloudflare Turnstile and how it works](https://blog.peak.fo/what-is-cloudflare-turnstile-how-it-works/)
- [The Cloudflare 5-second challenge explained](https://blog.peak.fo/the-cloudflare-5-second-challenge-explained/)
- [Cloudflare Turnstile — official documentation](https://developers.cloudflare.com/turnstile/)

## Contributing

Pull requests welcome. Add a tool with a one-line, factual description and a link. Open-source libraries, framework plugins, and commercial services all belong here; keep descriptions neutral and do not inflate claims. If you add a service, note that its pricing may change.

## License

[CC0](https://creativecommons.org/publicdomain/zero/1.0/) — public domain. Do whatever you want with it.
