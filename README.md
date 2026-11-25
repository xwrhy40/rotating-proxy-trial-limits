# Rotating proxies free trial: what you actually get, where the limits are, and how to pick a plan that fits (full plan and credit-cost table)

A "rotating proxies free trial" in this market hands you one of four things: a small traffic allowance (100MB to 1GB), a short time window (24 hours to 7 days), a signup credit of around $5, or a paid trial that costs $1.99 for three days. Almost none of them are unlimited, and the shape of the trial decides whether it's enough to finish your test or just enough to get a card on file.

ScraperAPI sits in the first camp and gives more room than most: **7 days and 5,000 API credits, no credit card required**, and when the week ends your account drops to a free plan with 1,000 credits a month instead of going dark.

Below you'll find the full ScraperAPI plan table, the four trial formats with real numbers, the conditions buried in the terms, what a trial quota is worth in actual scraping work, and a rule for matching the trial to the job you're running.

> **Quick pick.** If you want to test a rotating proxy pool without typing card details, start with the ScraperAPI trial. At 1 credit per standard page, 5,000 credits cover roughly 5,000 ordinary pages, 1,000 Amazon pages, or 200 Google result pages. Small projects can then stay on the free 1,000-credit plan indefinitely.
> 👉 [Start the ScraperAPI trial with 5,000 credits, no card](https://www.scraperapi.com/?fp_ref=coupons)

Worth knowing before you compare: ScraperAPI is a scraping API built on rotating proxy pools, not a shop that sells you a list of `host:port` endpoints. Its own documentation states there's no option to buy individual proxies from the pools. If your tool needs a raw proxy string to paste into a browser profile, that changes the shortlist, and I'll say which way to go further down.

## ScraperAPI plans and prices

Every plan currently shown on the official pricing page, with the annual rate expressed as the effective monthly price when you pay for a year.

| Plan | API credits / month | Concurrent threads | Monthly price | Annual price (per month) | Plan page |
| --- | --- | --- | --- | --- | --- |
| Free | 1,000 | 5 | $0 | $0 | [Free plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Hobby | 100,000 | 20 | $49 | $44.10 | [Hobby plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Startup | 1,000,000 | 50 | $149 | $134.10 | [Startup plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Business | 3,000,000 | 100 | $299 | $269.10 | [Business plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Scaling | 5,000,000 | 200 | $475 | $427.50 | [Scaling plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Professional | 10,500,000 | 300 | $975 | $877.50 | [Professional plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Advanced | 21,500,000 | 500 | $1,975 | $1,777.50 | [Advanced plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Enterprise | 22,000,000+ | 500+ | Custom | Custom | [Talk to sales via pricing](https://www.scraperapi.com/pricing?fp_ref=coupons) |

Three differences between tiers that the price column doesn't show:

- **Geotargeting.** Hobby and Startup are limited to US and EU regions. Country-level global targeting starts at Business.
- **Analytics history.** Hobby and Startup keep 30 days. Business and above keep everything.
- **Pay-as-you-go.** Only Scaling, Professional, Advanced and Enterprise can keep scraping past the credit cap at a fixed per-credit rate, up to a monthly spending cap you set. Hobby, Startup and Business simply pause (a 429 response, not a bill).

Annual billing takes exactly 10% off. Credits reset on each monthly renewal date and unused credits do not roll over.

## What 5,000 trial credits buy you

Credit-based trials are harder to judge than a gigabyte figure, so here is the cost side of the ledger. Every request type below is charged in credits, and the multiplier applies per domain, not per plan.

| Request type | Credits | Note |
| --- | --- | --- |
| Standard page | 1 | Most public websites |
| Amazon, Walmart, eBay | 5 | Per request |
| Google, Bing (including subdomains) | 25 | Per request |
| LinkedIn | 30 | Per request |
| Bot-protection bypass | +10 | Added when bypass logic activates |
| JS rendering (`render=true`) | 10 | Per request |
| Premium proxies (`premium=true`) | 10 | Per request |
| Screenshot | 10 | Per request |
| Premium proxies + JS rendering | 25 | Per request |
| Ultra premium | 30 | Paid plans only |
| Ultra premium + JS rendering | 75 | Paid plans only |
| Geotargeting, sessions, device type, output format, auto parsing | 0 | No extra cost |

Read that table against the 5,000-credit trial and the honest range is wide. Plain HTML pages: 5,000 of them. JS-rendered pages at 10 credits each: 500. Rendered pages behind bot protection at 25 credits: 200. If your target is a Google SERP at 25 credits per request, the trial gets you 200 queries, which is a real test of a rank-tracking pipeline but nowhere near a week of hourly monitoring.

That's the trade-off with credit pricing. It's cheap for simple pages and expensive for hard ones, and the trial is only generous if you know which kind of page you're hitting. ScraperAPI puts a credit cost in the `sa-credit-cost` response header on every request and offers a Domain Cost Estimator in the dashboard, so you can price a URL before spending anything.

👉 [Check the plan sizes and credit allowances side by side](https://www.scraperapi.com/pricing?fp_ref=coupons)

## The four things "free trial" means in this market

This is where most comparisons mislead, because the same phrase covers four different commercial arrangements.

| Provider | What the trial actually is | Duration | Card needed |
| --- | --- | --- | --- |
| ScraperAPI | 5,000 API credits, then a permanent 1,000-credit free plan | 7 days | No |
| MacroProxy | 100MB of rotating proxies **or** 1 static proxy IP | Static usually 1 day; rotating "depends on your tasks" | Not stated |
| PXYEDGE | 1GB of traffic plus 10 rotating residential IPs | 7 days | No |
| Oxylabs | Headline says up to 7 days; its own FAQ says a $5 welcome credit for verified company registrations | Up to 7 days / credit-based | Not stated |
| Froxy | A paid trial: $1.99 for any plan | 3 days | Yes, it's a purchase |
| Bright Data | No quota published; the page only promises you can start without a card | Not stated | No |

**Free allowance.** MacroProxy gives 100MB of rotating traffic or a single static IP, with rotating coverage across 195+ countries, unlimited concurrent sessions and a pool it puts at 95M+ IPs. PXYEDGE gives 1GB of traffic plus 10 rotating residential IPs for 7 days, including automatic rotation, country-level targeting and basic API access, across 195+ countries. The gap between those two is a factor of ten in traffic.

**Paid trial.** Froxy's three-day trial costs $1.99 on any plan. It's a legitimate way to test a service, but it is a purchase, not a free trial, and it shouldn't be counted as one when you're comparing costs. Froxy's own numbers: 120M+ IPs across 200+ locations, rotation adjustable from 90 to 3600 seconds, up to 1000 simultaneous connections, traffic that rolls over to the next period, rotating proxies from $5.50/month, residential from $2.69/GB.

**Signup credit.** Oxylabs' free-trial page carries two descriptions of its own offer at once. The title promises "up to 7 days", while the FAQ says verified company registrations receive a $5 welcome credit applicable to all products. Both statements sit on the same page, and I'm not going to pick one for them. What is consistent: HTTP, HTTPS, HTTP3 and SOCKS5 support, unlimited concurrent sessions, 99.9% uptime, and country, state, city and ASN targeting.

**Time-boxed full access.** SparkProxy advertises a 24-hour trial with 250 threads in its own listing, a format that suits a single verification run rather than a week of monitoring. Bright Data's rotating proxy page says no credit card is required to start and quotes 400M+ monthly IPs across 195 countries with free city, state, ZIP and ASN targeting, though that page is dated 2023 and no trial quota is published on it.

## Where the terms bite

Four conditions show up repeatedly and rarely make it into the comparison tables.

**One trial per user.** MacroProxy states its free trial is generally limited to one per user, with anything longer requiring a conversation with support. Assume the same posture elsewhere and plan your trial around the test you most need to run.

**Static gets a day, rotating gets a negotiation.** MacroProxy is explicit: static proxy trials usually run 1 day, while rotating trial length depends on your tasks and has to be arranged with the support team. If your test needs a week of continuous monitoring, a 1-day static trial won't answer the question.

**A company certificate can be the price of entry.** Oxylabs' $5 credit is tied to verified company registrations. Individual developers may find that the credit route isn't open to them, which makes the "up to 7 days" headline the only path left, and the page doesn't spell out how that's granted.

**"Up to 7 days" is not "7 days".** The word "up to" sets a ceiling, not an allowance. PXYEDGE's 7 days is stated as a flat trial period. Same number, different commitment.

## What a trial quota is worth in dollars

Converting free traffic into money makes the 100MB versus 1GB question concrete. Using Froxy's published residential rate of $2.69/GB as the reference:

- 1GB of trial traffic ≈ **$2.69** of usage at list price
- 100MB of trial traffic ≈ **$0.27** of usage at list price

That's a conversion at a competitor's public per-gigabyte rate, not anyone's official valuation of their trial, but the order of magnitude is the point. A 100MB allowance is enough to confirm that requests succeed and IPs rotate; it will not carry a scraping job. 1GB will carry a modest one for a few days.

Credit-based trials don't convert cleanly to gigabytes, which is why the credit table above matters more than the headline number. ScraperAPI's 5,000 credits are worth 5,000 standard pages and 200 Google SERPs, and those two figures describe very different amounts of work.

## Match the trial to the job

- **Confirming a scraper runs at all.** A few hundred requests over an hour is enough. Any of these trials covers it; ScraperAPI's 5,000 credits leave room to fail and retry, and the free 1,000-credit plan lets you keep the integration alive afterward without paying.
- **A week of monitoring at low volume.** PXYEDGE's 1GB over 7 days and ScraperAPI's 5,000 credits over 7 days are the two that actually give you a week. Check the credit burn first if your pages need rendering.
- **Testing geo-targeted collection.** Country-level targeting starts at ScraperAPI's Business tier, so the trial will show you whether the pipeline works but not the cheapest tier that includes global targeting. Oxylabs lists country, state, city and ASN targeting as part of its trial page, and Bright Data lists ZIP and ASN targeting as free.
- **Feeding a browser profile or anti-detect tool.** You need a proxy endpoint, and ScraperAPI doesn't sell individual IPs. MacroProxy's single static IP trial or PXYEDGE's 10 rotating IPs fit this job better.
- **Running a long-term small project.** A one-shot trial expires. ScraperAPI's free plan does not: 1,000 credits and 5 concurrent threads every month, indefinitely.

## What ScraperAPI's trial does and doesn't cover

The trial gives full API access for 7 days with 5,000 credits and no card. Everything in the credit table is available, including JS rendering, premium proxies, JSON auto parsing and rotating proxy pools, all of which are core features included on every plan. Geotargeting, sessions, device type, output format and auto parsing carry no credit surcharge.

Two limits to plan around. Hobby and Startup, the tiers most individuals land on, restrict geotargeting to US and EU regions. And unused credits are lost at each renewal rather than carried forward, so there's no reason to buy a tier above your monthly usage hoping to bank the difference.

The paid side is more forgiving than most. Subscriptions can be cancelled at any time from the dashboard at no charge, and there's a **7-day no-questions-asked refund policy** if the service doesn't work out. On Hobby through Professional you can switch on auto-upgrade so the account moves to the next tier when credits run out; leave it off and scraping pauses until renewal. On Scaling and above, pay-as-you-go continues at a fixed per-credit rate under a spending cap you set, and the cap is a limit rather than a pre-charge.

👉 [See the current ScraperAPI tiers, refund terms and free plan](https://www.scraperapi.com/?fp_ref=coupons)

## FAQ

**Do I need a credit card for a rotating proxy free trial?**
Not at ScraperAPI, PXYEDGE or Bright Data, all of which state no card is required. Froxy's 3-day trial is a $1.99 purchase, so a card is involved by definition. MacroProxy and Oxylabs don't state the card requirement on the pages reviewed.

**How much traffic does a free trial give?**
Between 100MB and 1GB at the proxy vendors: MacroProxy offers 100MB of rotating traffic, PXYEDGE offers 1GB. ScraperAPI works in credits instead: 5,000 during the trial, equal to 5,000 standard pages or 200 Google SERP requests.

**How long does a trial last?**
1 day for MacroProxy's static proxies, 7 days for PXYEDGE and ScraperAPI, up to 7 days per Oxylabs' headline. Rotating trials at MacroProxy are negotiated per task rather than fixed.

**Can I get a second trial?**
MacroProxy states the trial is generally limited to one per user and directs requests for more to its support team. Other providers don't publish a repeat-trial policy on the pages reviewed, so ask before assuming.

**What happens when the trial credits run out?**
At ScraperAPI the account moves to the free plan with 1,000 credits and 5 threads per month. On paid plans, scraping pauses at the credit cap unless you've enabled auto-upgrade or, on Scaling and above, pay-as-you-go.

## Picking in one minute

Need a proxy endpoint to paste into a browser or tool: take MacroProxy's single static IP or PXYEDGE's 10 rotating IPs, and skip ScraperAPI entirely, because it doesn't sell individual IPs.

Need to scrape pages through a rotating pool with rendering and bot-protection handling built in: start the ScraperAPI trial, price three or four of your real target URLs with the Domain Cost Estimator during the 7 days, and multiply by your monthly volume before choosing a tier. If that number lands under 100,000 credits, Hobby at $49 covers it and nothing above it is worth the difference.

Two things to confirm before any card is entered, with any provider: whether the trial converts into a paid subscription automatically when the clock runs out, and whether your use case needs a verified company registration to qualify. Both change the real price of "free".

👉 [Start with ScraperAPI's 5,000-credit trial or stay on the free 1,000-credit plan](https://www.scraperapi.com/?fp_ref=coupons)
