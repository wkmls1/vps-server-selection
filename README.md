# buy vps server: How to Pick the Right Route, Location, and Billing Cycle Before You Spend a Dollar

Most people shopping for a VPS start with the wrong column. They scan the RAM, nod at the core count, and then buy whatever looks cheapest per gigabyte. Then they spend the next three months wondering why a 2GB box in Los Angeles feels slower than a 1GB box somewhere else, or why their traffic got throttled three weeks into the month.

The specs aren't fake. They're just not what you're paying for. When you buy a VPS server, the thing that determines whether it feels good is the network path between your server and the people using it — and that path is invisible on a spec sheet. It shows up on an invoice as a higher price with no obvious justification.

So this is a guide to the part of the purchase nobody puts in the comparison table.

## The problem with shopping by spec sheet

A 2 vCore / 4GB / 80GB instance is not a commodity. Two providers can sell you that exact configuration at a $60/month spread, and both can be telling the truth about the hardware. What differs is:

- **Route quality.** Whether traffic takes a premium backbone or gets dumped onto congested public transit at 8pm.
- **Overselling policy.** Whether "4GB RAM" means 4GB you can actually use, or 4GB shared with eleven noisy neighbors.
- **What happens at the cap.** Whether you get suspended, billed overage, or quietly throttled.
- **Stock model.** Whether plans sell out and stay sold out, which happens more often than people expect at providers that refuse to oversell.

None of these appear in a "starting at $X/month" tagline.

## Five questions to answer before you buy

Answer these and your shortlist collapses to two or three plans. Skip them and you'll be comparing 40 SKUs across three continents.

1. **Where are your users?** Latency is geography plus routing. Hong Kong to Shenzhen is a 10–30ms trip. Los Angeles to Shenzhen is 150ms+ on a good day. No amount of CPU closes that gap.
2. **Do you need China-optimized routing specifically?** If your audience is mostly in Europe, North America, or Southeast Asia, buying a premium China route is money spent on a problem you don't have.
3. **How much traffic, in both directions?** Many providers count inbound and outbound and bill the larger figure. A "1TB" plan is not always 1TB of usable transfer.
4. **Monthly or annual?** Monthly billing is typically 15–25% more expensive than quarterly and 30–40% more than annual once promotional discounts apply. It buys you flexibility and costs you real money.
5. **What's the refund window?** Test during it. Latency and packet loss are things you verify, not things you assume.

## Where DMIT fits into this

DMIT is a US-registered provider (New York) that has been selling KVM VPS since 2017–2018, with a China-based operations team and data centers in Los Angeles, Hong Kong, and Tokyo. Payment works with PayPal, credit cards, Alipay, and WeChat, and there's Chinese-language ticket support.

Two things define how it prices. First, it doesn't oversell — which is why plans go out of stock and stay out of stock for weeks, and why the same allocation costs more than at a budget host. Second, it runs its own backbone and buys CN2 GIA, AS9929, and CMIN2 capacity directly, which is why the route quality is the actual product. If you want the current lineup and live stock status rather than a stale blog table, 👉 [check DMIT's current plans and availability directly](https://www.dmit.io/aff.php?aff=12046).

The trade-off is honest: you're paying for latency and stability under peak load, not for raw specs per dollar. If your workload is international and latency-insensitive, you'll be overpaying.

## The three network tiers, and who each one is for

Every DMIT region is split into three network profiles. Pick the tier wrong and you've wasted either money or performance.

### Premium (.Pro) — CN2 GIA

China Telecom's premium backbone, AS4809, on the return path, with China Unicom and China Mobile traffic also optimized. This is the tier for anyone whose users are in mainland China and who can't accept evening congestion. It's also the most expensive, often by a factor of two or three over Tier 1.

### Eyeball (.EB) — CMIN2 and AS9929

The middle tier. Return traffic rides CMIN2 or Unicom's 9929 rather than pure CN2 GIA. Better than ordinary transit toward China, noticeably cheaper than Premium, and usually stocked with more generous traffic allowances and port speeds. If your budget has a ceiling but "worse than the cheapest routing" isn't acceptable, this is the compromise.

### Tier 1 (.T1) — international BGP

No China optimization at all. Routes are tuned for Asia–America and intra-America latency instead. This is the cheapest line, and it's the right one for European or North American audiences, CI/CD runners, backup nodes, monitoring, and relay points. Traffic that exceeds the cap gets throttled rather than cut off, which makes the cheaper plans behave roughly like unmetered ones at reduced speed.

One practical detail: the rate at which traffic is throttled after you hit the cap varies by plan, from 4Mbps on the entry Premium tiers up to 500Mbps on the larger Tier 1 tiers. That number matters more than most people realise if you regularly exceed your allocation.

## Full plan comparison

Prices below are the publicly listed monthly rates and are subject to change, particularly on the newer hardware platforms. Where a plan is listed as annual, the figure is the annual price.

Los Angeles runs on three hardware generations — AS3 (EPYC 7003), AN4 (EPYC 9004), and AN5 (EPYC 9005). AN5 pricing came in roughly 20–30% above the previous generation, and LAX.AN4 has been retired from sale.

### Los Angeles — Premium and Eyeball, AN5 platform

| Plan | vCPU / RAM / SSD | Traffic @ port | After cap | Price | Buy |
| --- | --- | --- | --- | --- | --- |
| AN5.Pro.TINY | 1 / 2GB / 20GB | 1TB @ 1Gbps | 4Mbps | $14.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046) |
| AN5.Pro.Pocket | 1 / 2GB / 40GB | 1.5TB @ 4Gbps | 4Mbps | $21.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046) |
| AN5.Pro.STARTER | 2 / 2GB / 80GB | 3TB @ 10Gbps | 4Mbps | $43.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046) |
| AN5.Pro.MINI | 4 / 4GB / 80GB | 5TB @ 10Gbps | 8Mbps | $79.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046) |
| AN5.Pro.MICRO | 4 / 4GB / 160GB | 7TB @ 10Gbps | 8Mbps | $110.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046) |
| AN5.Pro.MEDIUM | 6 / 8GB / 160GB | 14TB @ 10Gbps | 10Mbps | $289.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046) |
| AN5.Pro.LARGE | 8 / 16GB / 320GB | 25TB @ 10Gbps | 10Mbps | $499.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046) |
| AN5.Pro.GIANT | 12 / 24GB / 640GB | 50TB @ 10Gbps | 10Mbps | $1009.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=premium&aff=12046) |
| Plan | vCPU / RAM / SSD | Traffic @ port | After cap | Price | Buy |
| --- | --- | --- | --- | --- | --- |
| AN5.EB.TINY | 1 / 2GB / 20GB | 2.2TB @ 2Gbps | 4Mbps | $12.98/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=eyeball&aff=12046) |
| AN5.EB.Pocket | 2 / 2GB / 40GB | 3TB @ 4Gbps | 4Mbps | $18.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=eyeball&aff=12046) |
| AN5.EB.STARTER | 2 / 2GB / 80GB | 5TB @ 10Gbps | 4Mbps | $38.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=eyeball&aff=12046) |
| AN5.EB.MINI | 4 / 4GB / 80GB | 10TB @ 10Gbps | 8Mbps | $76.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=eyeball&aff=12046) |
| AN5.EB.MICRO | 4 / 4GB / 160GB | 14TB @ 10Gbps | 8Mbps | $99.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=eyeball&aff=12046) |
| AN5.EB.MEDIUM | 6 / 8GB / 160GB | 30TB @ 10Gbps | 10Mbps | $219.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=eyeball&aff=12046) |
| AN5.EB.LARGE | 8 / 16GB / 320GB | 50TB @ 10Gbps | 10Mbps | $459.90/mo | [View plan](https://www.dmit.io/cart.php?region=los-angeles&generation=an5&network=eyeball&aff=12046) |

The older AS3 Eyeball line still surfaces entry plans around $10.90/month for 1 core, 2GB, 20GB SSD with 1.5TB of traffic on a 2Gbps port. AN5 Eyeball was upgraded to EPYC 9005 hardware in late 2025. Allocations listed here are counted in both directions, so plan your headroom accordingly.

### Los Angeles — Tier 1 (no China optimization)

| Plan | vCPU / RAM / SSD | Traffic @ port | After cap | Price | Buy |
| --- | --- | --- | --- | --- | --- |
| AN5.T1.V2C2G (VOLUME) | 2 / 2GB / 40GB | 5TB @ 10Gbps | 100Mbps | $14.90/mo | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AN5.T1.V2C4G (VOLUME) | 2 / 4GB / 80GB | 10TB @ 10Gbps | 200Mbps | $23.90/mo | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AN5.T1.V4C4G (VOLUME) | 4 / 4GB / 120GB | 20TB @ 10Gbps | 200Mbps | $36.90/mo | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AN5.T1.V4C8G (VOLUME) | 4 / 8GB / 160GB | 40TB @ 10Gbps | 500Mbps | $52.90/mo | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AN5.T1.V8C16G (VOLUME) | 8 / 16GB / 240GB | 80TB @ 10Gbps | 500Mbps | $119.90/mo | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AN5.T1.G2C4G (GENERAL) | 2 / 4GB / 80GB | 4TB @ 10Gbps | 100Mbps | $16.90/mo | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AN5.T1.G4C8G (GENERAL) | 4 / 8GB / 160GB | 8TB @ 10Gbps | 100Mbps | $36.90/mo | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AN5.T1.G8C16G (GENERAL) | 8 / 16GB / 320GB | 12TB @ 10Gbps | 200Mbps | $79.90/mo | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AN5.T1.G16C32G (GENERAL) | 16 / 32GB / 640GB | 32TB @ 10Gbps | 200Mbps | $199.90/mo | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AS3.T1.WEE | 1 / 1GB / 20GB | 1TB @ 4Gbps | 100Mbps | $36.90/yr | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AS3.T1.TINY | 1 / 1GB / 20GB | 2TB @ 4Gbps | 200Mbps | $6.90/mo ($82.80/yr) | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AS3.T1.STARTER | 2 / 2GB / 40GB | 4TB @ 10Gbps | 200Mbps | $12.90/mo ($154.80/yr) | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AS3.T1.MINI | 2 / 4GB / 80GB | 8TB @ 10Gbps | 200Mbps | $21.90/mo ($262.80/yr) | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |
| AS3.T1.MICRO | 4 / 4GB / 120GB | 16TB @ 10Gbps | 500Mbps | $32.90/mo ($394.80/yr) | [View Tier 1 plans](https://www.dmit.io/aff.php?aff=12046) |

The $36.90/year WEE plan is the cheapest way into the network, and it's the one that sells out fastest. It is not a plan you should buy for a production site with Chinese traffic — 1GB of RAM and no China optimization is a specific tool for a specific job.

### Hong Kong and Tokyo

Asia is more expensive because Asian bandwidth is more expensive. Hong Kong Premium entry sits around $39.90/month; Tokyo Premium starts around $21.90/month. Tokyo has dropped its Eyeball line, leaving Premium and Tier 1 there.

| Plan | vCPU / RAM / SSD | Traffic @ port | Price | Buy |
| --- | --- | --- | --- | --- |
| HKG.AN5.Pro.MINI | 2 / 2GB / 80GB | 1.5TB @ 1Gbps | $149.90/mo | [View Hong Kong Premium](https://www.dmit.io/cart.php?region=hong-kong&generation=an5&network=premium&aff=12046) |
| HKG.AN5.Pro.MICRO | 2 / 4GB / 160GB | 2TB @ 1Gbps | $199.90/mo | [View Hong Kong Premium](https://www.dmit.io/cart.php?region=hong-kong&generation=an5&network=premium&aff=12046) |
| HKG.AN5.Pro.MEDIUM | 4 / 4GB / 160GB | 2.5TB @ 1Gbps | $279.90/mo | [View Hong Kong Premium](https://www.dmit.io/cart.php?region=hong-kong&generation=an5&network=premium&aff=12046) |
| HKG.AN5.Pro.LARGE | 4 / 8GB / 320GB | 3TB @ 1Gbps | $359.90/mo | [View Hong Kong Premium](https://www.dmit.io/cart.php?region=hong-kong&generation=an5&network=premium&aff=12046) |
| HKG.AN5.Pro.GIANT | 8 / 16GB / 640GB | 6TB @ 1Gbps | $759.90/mo | [View Hong Kong Premium](https://www.dmit.io/cart.php?region=hong-kong&generation=an5&network=premium&aff=12046) |
| HKG / TYO T1.WEE | 1 / 1GB / 20GB | 1TB @ 4Gbps | $36.90/yr | [View Asia Tier 1](https://www.dmit.io/aff.php?aff=12046) |
| HKG / TYO T1.TINY | 1 / 2GB / 40GB | 2TB @ 4Gbps | $6.90/mo | [View Asia Tier 1](https://www.dmit.io/aff.php?aff=12046) |
| HKG / TYO T1.STARTER | 2 / 2GB / 40GB | 4TB @ 10Gbps | $12.90/mo | [View Asia Tier 1](https://www.dmit.io/aff.php?aff=12046) |
| HKG / TYO T1.MINI | 2 / 4GB / 80GB | 8TB @ 10Gbps | $21.90/mo | [View Asia Tier 1](https://www.dmit.io/aff.php?aff=12046) |
| HKG / TYO T1.MICRO | 4 / 4GB / 80GB | 16TB @ 10Gbps | $32.90/mo | [View Asia Tier 1](https://www.dmit.io/aff.php?aff=12046) |

Notice the pattern: a Hong Kong Premium plan with 1.5TB of traffic costs more than a Los Angeles Tier 1 plan with 40TB. You're not buying storage or RAM at that point. You're buying 20–50ms instead of 150ms.

## What traffic overage actually costs you

DMIT's policy is throttle, don't suspend. When you hit your allocation, the port drops to the plan's reduced speed and keeps running indefinitely. On Premium entry plans that's 4Mbps; on mid-tier Tier 1 plans it can be 200Mbps or higher.

Practically, this changes how you should estimate. Instead of asking "what happens if I go over," ask "can I live at the throttled speed for a few days?" 4Mbps handles a small site comfortably. It does not handle video.

Also worth flagging: traffic is metered bidirectionally and the higher of the two directions counts. If your workload is upload-heavy — backups, mirrors, video delivery — your effective allowance is smaller than the number on the page suggests.

## Billing cycles, promo codes, and the honest math

DMIT runs recurring promo codes that apply on renewal, not just the first term, which is unusual and worth taking seriously. The codes that have circulated longest apply to the Standard/Lite line: roughly 30% off on annual billing and 20% off on semi-annual. Beyond that, codes rotate frequently — new ones appear around Black Friday, Christmas, Chinese New Year, and the 618 sales, and they're usually tied to a specific region, a specific tier, and a minimum billing cycle.

Codes are validated in the cart with a "Validate Code" button, and mismatched combinations simply won't apply. If a code you found on a blog doesn't work, the most likely reason is that it was scoped to a different tier or a different billing cycle, not that it expired yesterday.

The arithmetic that matters: jumping from monthly to annual billing is worth more than most coupon hunting. A one-off 15% code on a monthly plan is worse than annual pricing on the same plan in almost every case.

## Refunds, IP replacement, and payment

- **Refund window:** a full refund within 3 days, provided you've used no more than 30GB of traffic, and prorated refunds up to 30 days. That's enough time to run real latency tests from your users' locations.
- **IP replacement:** on Premium and Eyeball plans, if an IP becomes blocked in sensitive regions it can be replaced free once every 15 days. Other replacements cost $5.
- **Payment:** PayPal, credit cards, Alipay, and WeChat.
- **Stock:** plans sell out. LAX.AN5.Pro.MINI has shown as out of stock while higher tiers remain available. If you're set on a specific plan, check availability before you plan around it.

One genuine downside reported by users: hardware maintenance windows aren't always announced by email in advance, so a short unplanned outage can happen. If you need a written SLA, this isn't the provider you're looking for.

## Which one should you actually buy

- **Site or app with mainland China users, and you can't tolerate evening packet loss** → Los Angeles Premium, or Hong Kong Premium if the budget genuinely allows it. Hong Kong buys you latency; Los Angeles buys you the same route for less.
- **China-facing on a tighter budget** → Eyeball on the AN5 platform. You give up pure CN2 GIA and get CMIN2/9929 instead, at roughly half the price with more traffic.
- **International audience, dev environment, CI runner, backup node** → Tier 1. Start with T1.TINY at $6.90/month to test, or the WEE annual plan if the workload is light and permanent.
- **Heavy transfer, low CPU sensitivity** → AN5 Tier 1 VOLUME. 40TB for $52.90/month is a different category of value than anything on the Premium line.
- **Streaming and region-locked content** → Premium plans have historically shipped native IPs, but the provider makes no unlock guarantee. Buy monthly first, test, and only then commit to annual.

## FAQ

**Is DMIT suitable if my users are mostly in mainland China?** Yes — that's the core use case, and it's why Premium pricing is what it is. Tier 1, by contrast, is explicitly not optimized for China.

**Does my server get suspended when I exceed the traffic cap?** No. It's throttled and stays online.

**Why are so many plans out of stock?** Because the provider doesn't oversell. Capacity is added in batches, and popular plans sell through quickly. Restocks tend to cluster around sale periods, product migrations, and end-of-quarter releases of freed-up capacity.

**Can I run Windows?** Yes on plans with 4GB of RAM and above.

**Is monthly billing worth it?** For a first purchase, yes — it lets you verify routing during the refund window without committing a year. Once you've confirmed the plan fits, annual billing is where the real savings are.

## Before you click buy

Test first. Every region has a Looking Glass page, and 30 minutes spent checking ping and traceroute from your actual users' networks is worth more than any comparison table, including this one. Then buy monthly, watch it through a week of peak hours, and only convert to annual once the numbers hold.

If you've already done that and DMIT's routing is what you need, 👉 [the current plan list and live stock are here](https://www.dmit.io/aff.php?aff=12046). Plan prices on the newer AN5 hardware have moved up over the past year, so treat any older price you find in a forum post as expired until the order page confirms it.
