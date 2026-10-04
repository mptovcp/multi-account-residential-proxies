# proxies for multiple accounts: How to Keep Each Login on Its Own Residential IP, and What the Plans Actually Cost

Password reuse is the obvious mistake, and it's the one everyone fixes first. The one that actually gets accounts linked is quieter: the IP address behind them.

When a platform's trust-and-safety system decides whether ten logins belong to one person or ten, it looks at three things — device fingerprint, behavioural timing, and IP. The IP is the cheapest of the three to check, and the hardest to fake convincingly. Ten accounts logging in from one datacenter range is a cluster. Ten accounts logging in from ten different residential connections in the cities they claim to be in is, from the platform's side of the table, just ten customers.

So the real question isn't "do I need proxies for multiple accounts." It's which type, how many, and whether the billing model matches the way account work actually runs. That's what this breaks down — including the current plan structure at 9Proxy, which has a pricing model that suits this specific job better than most.

## Why residential IPs keep coming up

Datacenter IPs are cheap and fast, and for account work they're mostly a liability. They belong to hosting ASNs, and hosting ASNs are published. Any platform that cares has a list.

Residential IPs are assigned by consumer ISPs to real home connections. There's no list to check against, because the list is "everyone." That's the whole argument, and it's why residential is the default recommendation for anything involving account trust scores rather than raw request volume.

The trade-off is real, though: residential IPs are volatile. A home connection goes offline, the IP drops with it. Datacenter proxies stay up for months. So a residential provider worth using needs to handle churn mechanically rather than making you babysit a list.

## Static, rotating, or ISP? Picking the type before the vendor

Multi-account work and scraping want opposite things, and providers sell both under the same roof.

| Proxy type | Looks like | Stays the same? | Best for |
| --- | --- | --- | --- |
| Datacenter | A server | Yes, basically forever | Bulk scraping, price checks, non-sensitive tasks |
| ISP / static residential | A home user | Yes, stable | Accounts that need a permanent home IP |
| Residential (session) | A real home user | Hours up to ~24h | Account logins, warmup, browsing, purchases |
| Rotating residential | A different home user each request | No | High-volume requests where session identity doesn't matter |
| Mobile | A phone on 4G/5G | Rotates, high trust | Platforms that weight mobile traffic heavily |

If the goal is ten eBay seller accounts, thirty Instagram profiles, or a handful of ad accounts, you want the middle rows — real residential, one IP parked per account, held for as long as the session needs. Rotating IPs are the wrong tool for that job: an account that changes city every request looks exactly like what it is.

## How many proxies does a multi-account setup actually need

The rule that matters: **one account, one dedicated IP, never shared between profiles.** Two accounts on the same IP is the single most common reason a "clean" setup still gets flagged.

The practical wrinkle is churn. Because residential IPs come and go, you want headroom on top of your account count — roughly 30–50% more than the number of profiles you're running, so you can swap a dropped IP without pulling one from another account.

A workable starting ratio:

- 10–20 accounts → 20–30 IPs in reserve
- 50 accounts → 70–80 IPs
- 200+ accounts → 250–300 IPs, plus a rotation rule for anything non-critical

At 9Proxy's entry tier, 100 IPs run **$24** — twenty-four cents per IP, with no recurring charge. That's the number worth holding onto when comparing against providers that bill monthly per proxy.

## What 9Proxy's plan structure looks like

9Proxy sells residential proxies from a pool of 20M+ IPs across 90+ countries, with HTTP/HTTPS and SOCKS5 support and targeting down to country, state, city, ZIP, and ISP level. Two things about the pricing are unusual, and both matter for multi-account work.

First, it's **balance-based, not subscription-based**. You buy IPs or gigabytes once; they sit in your account until you use them. Unused IPs never expire. GB traffic carries 180-day validity (unlimited on Enterprise).

Second, the IP-based product charges **per IP with unlimited bandwidth** rather than per gigabyte. A profile that browses heavily all day costs the same as one that logs in twice.

Pricing was adjusted on 1 June 2026 for IP-based and bundle packages; GB-based rates were left unchanged. What's published now:

| Package | What you get | Price | Effective rate | Billing | Buy |
| --- | --- | --- | --- | --- | --- |
| IP-100 | 100 residential IPs | $24 | $0.24 / IP | One-time, IPs never expire | Get this package |
| IP-500 | 500 residential IPs | $72 | $0.144 / IP | One-time, IPs never expire | Get this package |
| IP-1,000 + 500 bonus | 1,500 residential IPs | $126 | $0.084 / IP | One-time, IPs never expire | Choose this plan |
| IP-2,500 | 2,500 residential IPs | $210 | $0.084 / IP | One-time, IPs never expire | Get this package |
| IP-5,000 | 5,000 residential IPs | $360 | $0.072 / IP | One-time, IPs never expire | Get this package |
| IP-15,000 | 15,000 residential IPs | $720 | $0.048 / IP | One-time, IPs never expire | Get this package |
| IP-25,000 | 25,000 residential IPs | $863 | $0.035 / IP | One-time, IPs never expire | Get this package |
| IP-50,000 | 50,000 residential IPs | $1,438 | $0.029 / IP | One-time, IPs never expire | Get this package |
| Business 100K | 100,000 residential IPs | $2,300 | $0.023 / IP | One-time, IPs never expire | Get this package |
| Business 200K | 200,000 residential IPs | $4,140 | $0.021 / IP | One-time, IPs never expire | Get this package |
| Business 500K | 500,000 residential IPs | $8,625 | $0.018 / IP | One-time, IPs never expire | Get this package |
| GB-5 | 5 GB rotating residential | $15 | $3.00 / GB | One-time, 180-day validity | Choose this plan |
| GB-50 + 5 bonus | 55 GB rotating residential | $105 | $2.10 / GB | One-time, 180-day validity | Get this package |
| GB-100 | 100 GB rotating residential | $150 | $1.50 / GB | One-time, 180-day validity | Get this package |
| GB-200 | 200 GB rotating residential | $200 | $1.00 / GB | One-time, 180-day validity | Get this package |
| GB-1,000 | 1,000 GB rotating residential | $800 | $0.80 / GB | One-time, 180-day validity | Get this package |
| GB-2,000 | 2,000 GB rotating residential | $1,500 | $0.75 / GB | One-time, 180-day validity | Get this package |
| Bundle Starter | 100 IPs + 5 GB | $30 | — | One-time, bundled traffic 180-day validity | Get this package |
| Bundle Popular | 1,500 IPs + 50 GB | $180 | — | One-time, bundled traffic 180-day validity | Get this package |
| Bundle Pro | 5,000 IPs + 500 GB | $720 | — | One-time, bundled traffic 180-day validity | Get this package |
| Enterprise | Custom IP/GB volume, unlimited data validity, team mode (1 owner + 5 members), per-member traffic controls, activity logs | Quote-based | — | Custom | Talk to 9Proxy about Enterprise |

Two caveats worth stating plainly. These are the rates currently published following the June 2026 adjustment, and vendors change pricing — confirm on the pricing page before committing to a large balance. And Enterprise is genuinely quote-based; there's no public number to compare.

Also worth knowing: paying in crypto adds a **5% IP bonus**, and 9Proxy's referral program gives accounts that sign up through a referral link a 5% discount at purchase.

## Which tier actually fits a multi-account workflow

For solo operators running a handful of social or marketplace profiles, the 100-IP tier at $24 is the honest starting point. It's enough for roughly 60–70 active accounts with churn headroom, and it never expires, so there's no clock running while you figure out your setup.

The **1,000 + 500 bonus** tier is where the per-IP economics change most sharply — from $0.24 down to $0.084, a 65% cut — without jumping into five-figure IP commitments. That's the tier most people running this kind of work end up on, and it's the one 9Proxy itself labels as popular.

Agencies managing accounts for multiple clients usually land on 5,000 IPs ($360) or the Popular bundle at $180, which pairs 1,500 IPs with 50 GB of rotating traffic — useful when some profiles need a parked IP while lighter tasks just need rotation.

The one thing the IP-based tiers do *not* solve: they need the desktop app. IP-based proxies work through local port forwarding, so Windows, macOS, or Linux software is required. If your accounts live in a cloud phone farm or a browser profile tool running off a server, the GB-based product is the better fit — it runs entirely from the dashboard with username/password or IP-whitelist authentication, no app involved.

## Setting it up without wasting IPs

Rough order of operations:

1. Create the account, then decide IP-based or GB-based based on whether you need parked IPs or flexible traffic. You don't need both — that's what the bundles are for.
2. Pull the IP list. On IP-based plans, filter by country, city, state, ISP, or ZIP inside the app.
3. Assign one IP per browser profile. In anti-detect tools, that's a one-to-one mapping in the proxy settings; SOCKS5 is the protocol to use if the tool supports it, since it passes non-HTTP traffic too.
4. Bind ports. Quick Bind and port configuration let you route a specific profile to a specific IP without reconfiguring the app each time.
5. Turn on auto-refresh. When an IP drops, the replacement is handled rather than leaving a profile on a dead proxy — which is its own flag, because a login that suddenly fails from a vanished IP is a pattern too.
6. Set rotation only where it's harmless. Auto-rotation runs on custom intervals on selected ports. Don't point it at your account profiles.

One account per IP. That's the whole discipline.

Where the account work specifically benefits: 9Proxy's **Today List** lets you reuse any IP you've already forwarded within the last 24 hours without spending a new one from your balance. For agencies where profiles log in and out through the day, this is a meaningful cost reduction on repeated work. The **60-second credit policy** covers the other side — if a proxy fails to connect within the first minute of activation, it gets credited back rather than consumed.

Neither feature exists to make the product sound generous. They exist because residential IPs die predictably often, and the alternative is you paying for a dead IP and manually re-issuing.

## Where this setup has limits

A few things that will bite if you go in expecting otherwise:

- **Residential IP lifespan is variable.** Hours to about 24 hours is normal, and it's not a bug you can configure away — it's how consumer connections behave. Plan around it with headroom IPs, not by expecting permanence.
- **Roughly three concurrent threads per proxy.** 9Proxy's own guidance recommends keeping it at or under three for performance. Ten parallel threads through one IP will slow it down and looks nothing like a human.
- **No PayPal.** Cards, Google Pay, local payment methods, crypto, and wallet balance. Crypto purchases get that 5% IP bonus; PayPal isn't on the list.
- **Refunds are narrow by design.** It's a digital product; credits are issued for system errors and failed connections within the 60-second window, not for changed plans.
- **The pool is large but not the largest.** 20M+ IPs is comfortably enough for account work. Providers advertising 70–100M are competing on a number that matters more for industrial scraping. Depth is concentrated in the US, Canada, France, the UK, and Germany — relevant if your accounts claim those regions, less so if they're spread thinly elsewhere.
- **Free trials come and go.** They're offered periodically and usually need a request to support rather than a button on the pricing page. Don't plan your evaluation around one.

Independent reviews put success rates in the low-to-mid 90s and average response times in the 0.4–0.6 second range, which is normal-to-good for residential. Nobody's getting 100% — that's not a vendor thing, it's a "residential IPs belong to real people who turn their router off" thing.

## A short hygiene checklist

Proxies solve the IP layer. They don't solve the rest, and getting the rest wrong wastes the money you spent.

- Never reuse a proxy across two profiles, even briefly.
- Match the IP's city to the account's profile history. A US account that logs in from Frankfurt is a bigger red flag than a datacenter IP.
- Give new accounts a warmup period — browsing, scrolling, light activity — before the first high-stakes action.
- Keep logins consistent on the same IP where possible. Account work is a static problem, not a rotation problem.
- Don't chase 1:1 IP-to-account exactly. Keep two or three spare IPs per ten accounts so a dropped connection doesn't cascade.
- Watch the account, not just the proxy. If a profile starts drawing CAPTCHAs, the fingerprint is likely the issue, not the IP.

## The short version

If you're running multiple accounts and the current setup is one home IP or a shared datacenter range, that's the thing to fix first — before fingerprint browsers, before proxies with better marketing.

For account work specifically, you want session-based residential IPs, one per profile, with headroom for churn, on a balance-based plan with no monthly bleed. 9Proxy fits that shape: $24 gets you 100 IPs with unlimited bandwidth that don't expire, the Today List cuts the cost of reuse, and the 60-second credit policy absorbs the occasional dead connection. Scale up when the account count demands it, not before — the per-IP rate drops sharply at 1,500 IPs, and there's no reason to prepay past what you're actually running.

👉 [Grab a 9Proxy account and start with 100 IPs](https://bit.ly/9-Proxy) — twenty-four cents per IP, no subscription, and the IPs stay in your balance until you use them.
