# Evoxt Japan: Tokyo vs Osaka, Is the $2.99 Plan Usable, and What the Add-Ons Really Cost (All 11 Plans Priced)

Evoxt sells two Japan locations at the same price: Tokyo on its Standard network and Osaka on its Premium Network. VM-0.5 costs $2.99/month in either city with identical CPU, RAM and disk. The only difference on the spec sheet is monthly transfer, 500 GB in Tokyo against 250 GB in Osaka. For most readers the plan worth buying is VM-1 at $5.99: 1 core, 2 GB RAM, 20 GB storage, 1,000 GB transfer in Tokyo.

Below is the full Japan price list, the add-on pricing that quietly changes the monthly bill, what "up to 6.0 GHz" actually refers to, and the cases where a different provider is the better buy.

> **Quick picks**
> - Cheapest box, single VPN endpoint, one small bot: **VM-0.5, $2.99** (512 MB RAM, 5 GB disk, 500 GB Tokyo / 250 GB Osaka)
> - Blog, Docker host, control panel, a handful of small sites: **VM-1, $5.99** (2 GB RAM, 20 GB disk, 1,000 GB Tokyo / 500 GB Osaka)
> - A small SaaS or several services on one box: **VM-4, $23.99** (4 cores, 8 GB RAM) or **VM-6, $29.99** (8 cores, 8 GB RAM)
>
> 👉 [Open the Evoxt console to pick Tokyo or Osaka and see today's plan pricing](https://bit.ly/EvoXt)

## All 11 Evoxt Japan plans

Every plan below is listed at "up to 6.0 GHz" per core and includes a free weekly offsite backup. Prices are per month and identical for Tokyo and Osaka; only the transfer allowance differs.

| Plan | CPU / RAM / Storage | Tokyo transfer | Osaka transfer | Price | Order |
| --- | --- | --- | --- | --- | --- |
| VM-0.5 | 1 core / 512 MB / 5 GB | 500 GB | 250 GB | $2.99/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-0.75 | 1 core / 1 GB / 10 GB | 750 GB | 250 GB | $4.99/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-1 | 1 core / 2 GB / 20 GB | 1,000 GB | 500 GB | $5.99/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-1.5 | 2 cores / 2 GB / 20 GB | 1,500 GB | 500 GB | $6.95/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-2 | 2 cores / 4 GB / 30 GB | 2,000 GB | 1,000 GB | $11.99/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-3 | 4 cores / 4 GB / 30 GB | 3,000 GB | 1,000 GB | $14.99/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-4 | 4 cores / 8 GB / 60 GB | 4,000 GB | 2,000 GB | $23.99/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-6 | 8 cores / 8 GB / 60 GB | 5,000 GB | 2,000 GB | $29.99/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-8 | 8 cores / 16 GB / 80 GB | 6,000 GB | 3,000 GB | $47.99/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-12 | 16 cores / 16 GB / 80 GB | 8,000 GB | 3,000 GB | $60.95/mo | [Deploy](https://bit.ly/EvoXt) |
| VM-16 | 16 cores / 32 GB / 100 GB | 10 TB | 5,000 GB | $95.99/mo | [Deploy](https://bit.ly/EvoXt) |

Two things about this table are worth pausing on. The first is the shape of the lineup: you can buy a 1-core box with 2 GB of RAM for $5.99 or a 2-core box with the same RAM and disk for $6.95. The second is jump from VM-0.75 to VM-1, which doubles RAM, doubles disk and adds 250 GB of Tokyo transfer for exactly one dollar more than the smaller plan. The $2.99 tier exists, but the value curve bends hard at $5.99.

## Tokyo vs Osaka: same price, different transit and a 4x overage rate

The hardware and price are the same in both cities. What changes is the network the box sits on and how much traffic you get before overage kicks in.

According to third-party write-ups of Evoxt's network, Tokyo peers through multiple Tier-1 carriers and BBIX, which is the usual recipe for low latency into Korea, eastern China, Taiwan and Hong Kong. Osaka's primary transit is described as Softbank, which the same write-up calls a favorite for China-bound traffic. Those are the vendor's claims as relayed by a third party, not something I can verify from a terminal.

Latency numbers circulating in those reviews put East Asia to Tokyo mostly in the 50 to 80 ms range, with a visible evening peak problem: some users report jumps from around 80 ms to 160 ms during Japanese prime time. Osaka is reported to hold up better under load, with lower p95 tail latency, which is presumably why it sits in the Premium Network tier despite costing the same.

The rule that falls out of that:

- **Traffic heading to or from mainland China, or anything where tail latency matters** (a trading bot, an API proxy, a game server): Osaka, and budget for the 250 GB entry allowance.
- **General Asia-facing work, or anything that moves real bandwidth**: Tokyo. VM-1 gives you 1,000 GB there instead of 500 GB, and the overage rate is a quarter of Osaka's.

That overage gap is the part that rarely makes it into comparison posts. Extra transfer costs **$3/TB on Standard (Tokyo)** and **$12/TB on Premium (Osaka)**. A box that pushes 2 TB past its limit costs $6 in Tokyo and $24 in Osaka. If your workload is streaming, mirroring, or anything with a steady outbound flow, the cheaper-per-gigabyte city is Tokyo by a wide margin.

Osaka's entry plan gives you 250 GB a month, roughly 8 GB a day. For a VPN endpoint or a small API that's plenty. For a media server it's a counting-down clock.

## The add-on prices are where a cheap plan stops being cheap

Evoxt lets you bolt resources onto an existing VM from the control panel instead of changing plans. The rates:

- Extra vCore: **$3/month**
- Extra 1 GB RAM: **$2/month**
- Extra IPv4: **$3/month**
- Extra transfer: **$3/TB (Standard), $12/TB (Premium), $24/TB (Premium Plus, not applicable to Japan)**
- Paid backup plan: priced by VM storage size, variable

Those numbers look reasonable in isolation. Run them against the plan ladder and they stop making sense.

Take VM-0.75 at $4.99 with 1 GB RAM. Add 1 GB of RAM for $2 and you're paying **$6.99** for 1 core, 2 GB RAM, 10 GB disk and 750 GB Tokyo transfer. VM-1 costs **$5.99** and gives you 2 GB RAM, 20 GB disk and 1,000 GB transfer. You pay a dollar less and get double the disk and 250 GB more traffic. The add-on is strictly worse.

Same story one rung up. VM-1 plus an extra vCore is **$8.99** for 2 cores, 2 GB RAM, 20 GB disk, 1,000 GB transfer. VM-1.5 is **$6.95** with the same 2 cores, same RAM, same disk and 1,500 GB of Tokyo transfer.

Add-ons earn their keep only when you need one dimension without touching the others. An extra IPv4 for $3 is the clean example: no plan tier sells you a second IP, and if you're running a mail server or separating services, you need it. Extra RAM on a plan whose core count you don't want to change is the other case. For everything else, check the next plan up first. It is usually cheaper than the add-on that mimics it.

The free weekly offsite backup is included on every plan, so the paid backup tier is an upgrade, not a prerequisite. Third-party tracking of Evoxt's plan pages describes the paid tier as adding daily backups, on-demand manual backups and five rotation copies, and notes those backups don't consume your VM disk. Confirm the current terms on the order page, since the price scales with storage and isn't published as a flat rate.

👉 [Check the current VM-1 price and add-on options in the Evoxt console](https://bit.ly/EvoXt)

## What "up to 6.0 GHz" actually means

Evoxt's own headline is "High CPU Frequency at Low CPU Frequency Prices," and every plan is labeled "up to 6.0 GHz." The "up to" is doing real work in that sentence. Third-party reviews note that not every node hits that ceiling and that older hardware in the fleet runs at 3.5 GHz and above.

What this buys you is single-thread performance, and that's the workload profile the pricing is built around. A VPN endpoint, a small API, a game server for a handful of players, a bot: these care about one fast core more than eight slow ones. Independent benchmark coverage has repeatedly placed Evoxt's single-core results above same-price DigitalOcean, Vultr and Linode instances, and VPSBenchmarks has ranked the company in the top tier of budget providers, including second place in a "Best VPS under $25" category.

An archived Evoxt Japan page lists Geekbench 5 scores of 1,073 and 1,098 for the two single-core plans, 1,940 for the 2-core VM-2 and 5,265 for the 8-core VM-8. That page also shows prices that no longer match the live pricing page, so treat the scores as historical reference points rather than a current promise.

Where the claim doesn't help you: multi-core throughput per dollar. If you're compiling, transcoding or running a database that spreads across cores, the 6.0 GHz label is irrelevant and you should compare core counts and RAM against Contabo and Vultr instead.

## Where Evoxt Japan is the wrong choice

Published entry-level Japan pricing from a third-party comparison, current as of late 2026:

| Provider | Entry Japan plan | Price | RAM | Storage | Transfer |
| --- | --- | --- | --- | --- | --- |
| Kamatera | Basic | $4.00/mo | 1 GB | 20 GB SSD | 5 TB |
| Vultr | Cloud Compute | $6.00/mo | 1 GB | 25 GB SSD | 2 TB |
| Contabo | VPS S | ~$5.50/mo | 8 GB | 50 GB NVMe | 32 TB |
| LightNode (Tokyo) | Small | ~$7.70/mo | 2 GB | 50 GB SSD | 1 TB |
| Hostinger | KVM 1 | ~$4.50/mo (promo) | 4 GB | 50 GB | 4 TB |

Read that table honestly and the conclusion is uncomfortable in places. Vultr gives you 2 TB of transfer at $6 against Evoxt's 1,000 GB at $5.99 in Tokyo, and 4x the allowance if you're comparing to Osaka. Contabo hands you 8 GB of RAM for around $5.50, though its Tokyo latency reviews are mixed and renewal pricing moves. Kamatera includes 5 TB at $4.

So:

- **Bandwidth-heavy workloads** (streaming, large downloads, mirrors): Vultr or Kamatera, or accept Tokyo's cheaper $3/TB overage and stay on Standard.
- **RAM-heavy workloads** (JVM apps, databases, containers with fat heaps): Contabo's specs are hard to argue with on paper.
- **You need live chat at 3 a.m.**: Evoxt runs ticket-based support, not 24/7 live chat.
- **You want a mature, heavily documented control panel and API ecosystem**: Vultr and Kamatera are the safer picks.

And the negative that should be on the record: a Reddit thread titled "Evoxt, Worst VPS hosting service I've ever experienced" describes packet loss on one specific IPv4 address. That's a single user's single data point, not a pattern, but $3/month hosts live and die on whether your particular node is healthy, and one angry thread is enough reason to keep your own backups and test the box in the first week.

Trustpilot sits around a 4-star average on a small review base. Small base means the number is soft in both directions.

## Ordering, payment, and the discount situation

The flow is short. Create an account with an email and password (third-party guides note Evoxt says it usually asks for nothing beyond your name), choose Tokyo or Osaka, pick an OS, choose a billing term, pay.

Billing runs from **monthly up to 3 years**, and you can top up account credit and let it apply to future invoices. Longer terms carry discounts, though the exact percentage isn't published as a flat rate on the pricing page.

Payment methods listed in Evoxt's own FAQ: credit cards, debit cards, PayPal, Bitcoin, and USDt Tron. Third-party guides add Litecoin, Ethereum and Alipay on the Chinese-language site. Card, PayPal and BTC are the ones you can count on from the official documentation.

OS support covers the standard Linux range (Ubuntu, Debian, CentOS, AlmaLinux, Rocky, Fedora) plus Windows Server, per third-party documentation; Evoxt's own Japan page advertises Windows RDP and Linux. Custom ISO upload is described as available on higher plans. Deployment is automated and third-party guides put it at around 2.5 minutes to credentials in your inbox.

On refunds, the sources disagree and I'm not going to paper over it. One third-party guide claims a 14-day money-back guarantee for new accounts. A pricing tracker that reads Evoxt's own pages lists a **7-day window, new customers only, from first deployment**. Neither figure appears as a headline term on the pages I could check. Assume the shorter window and confirm the actual term at checkout before you pay for a year.

Discount codes are the murkiest part of the whole thing. Coupon aggregators and affiliate write-ups circulate 5% codes, a recurring code attributed to a forum post, and seasonal promotions of up to 25% on selected plans. None of that is confirmed by Evoxt, several of those pages exist to sell you something, and claims of 40% off that appear in some search snippets have no supporting page behind them. There is a promo code field at checkout. Try what you find, verify the discounted total before you pay, and don't build your budget on it.

👉 [Start an Evoxt Japan deployment and see the final total at checkout](https://bit.ly/EvoXt)

## Which plan to actually buy

Match the workload, then stop reading:

- **One VPN endpoint, a DNS resolver, a monitoring probe**: VM-0.5 at $2.99. 512 MB is enough for WireGuard or Xray and not much else. Pick Tokyo unless you specifically need the Softbank path, because Osaka gives you half the traffic for the same money.
- **A blog, a small Django or Node app, a Docker host with three or four containers**: VM-1 at $5.99. This is the plan the pricing page is built around, and the jump from VM-0.75 is a dollar.
- **A staging environment that needs more than one core**: VM-1.5 at $6.95, not VM-1 plus a $3 vCore.
- **A small SaaS with a database on the same box**: VM-4 at $23.99. VM-6 at $29.99 buys four more cores for $6 if your workload is parallel rather than memory-hungry.
- **Anything past 8 GB of RAM**: compare against Contabo before clicking, because Evoxt's advantage thins out as you climb the ladder.

Two things to confirm before you pay. First, your monthly transfer: subtract the plan allowance from what you actually push, and price the difference at $3/TB in Tokyo or $12/TB in Osaka. A plan that looks cheap can lose that advantage in one heavy month. Second, whether ticket-based support fits how you operate. If you need someone on chat at any hour, this isn't the provider for that.

If both answers are fine, the entry price is real and the single-core performance is the reason to be here.

👉 [Pick a Japan location and deploy an Evoxt VM](https://bit.ly/EvoXt)
