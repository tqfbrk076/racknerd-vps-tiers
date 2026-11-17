# Virtual Private Server Hosting: Is a $22-a-Year KVM Plan Enough, What Does Unmanaged Actually Mean, and Which RackNerd Tier Should You Pick? (Plans, Renewal Terms, Hidden Costs)

Most people searching for virtual private server hosting want one number: the least they can pay for a machine that stays up. RackNerd's KVM specials currently start at **$21.99/year** for 1 vCPU, 1 GB RAM, 20 GB SSD and 3 TB of monthly transfer; the 2 GB tier is **$35.99/year**. Both are unmanaged, both include a dedicated IPv4 and a 1 Gbps port, and both renew at the same rate you signed up for.

The uncertainty is whether the cheap tier is enough for your workload, and what the annual price leaves out. Those two questions decide most purchases, so they get most of the space below.

> **Quick pick:** Take the **2 GB KVM special at $35.99/year** if you're running WordPress, a small database, Docker, or a control panel. Double the RAM is the difference between a package update finishing and the box swapping itself to death. Take the **1 GB plan at $21.99/year** for a static site, a VPN endpoint, a bot, or a Linux sandbox you plan to break and rebuild. Neither plan includes backups or managed support.
>
> 👉 [See RackNerd's current VPS specials and prices](https://bit.ly/RacKnerd)

## RackNerd VPS plans and what each one comes with

The specials page currently lists five annual KVM plans. The two entry tiers are where nearly all first purchases land, and their confirmed specs and prices are below. The three tiers above them add RAM and SSD at higher annual prices, and those figures move often enough that the plan page is the only reliable source.

| Plan | Confirmed specs | Price and billing | Order |
| --- | --- | --- | --- |
| 1 GB KVM Special | 1 vCPU, 1 GB RAM, 20 GB RAID-10 SSD, 3 TB/month transfer, 1 Gbps port | **$21.99/year**, renews at the same rate | [Start with the 1 GB plan](https://bit.ly/RacKnerd) |
| 2 GB KVM Special | 2 GB RAM, KVM, one dedicated IPv4, 1 Gbps port (CPU and disk specs are listed on the plan page) | **$35.99/year**, renews at the same rate | [Compare the 2 GB plan](https://bit.ly/RacKnerd) |
| Higher tiers | More RAM and SSD, same feature set | Priced per plan on the specials page | [See all current tiers](https://bit.ly/RacKnerd) |

Everything in the specials line shares one feature set, which matters more than the price difference between tiers:

| Feature | Detail |
| --- | --- |
| Virtualization | KVM |
| Access | Full root, SSH |
| Control panel | ctrl, included with every plan: reboot, OS reinstall, HTML5 VNC console, firewall rules, root password reset, in-panel upgrades |
| IPv4 | One dedicated address per plan |
| IPv6 | Up to 100 free addresses in Los Angeles and France, on request after ordering |
| Operating systems | CentOS, Rocky Linux, AlmaLinux, Fedora, Debian, Ubuntu; custom ISO installs via support ticket |
| Locations | Los Angeles, San Jose, Seattle, Dallas, Atlanta, Chicago, New Jersey, New York, Ashburn, Amsterdam, France |
| Backups | Not included |
| Management | Unmanaged |

Two things in that table are worth pulling out. The control panel is free, which is not standard in this price bracket; several mainstream hosts sell panel licences as a monthly add-on. And the IPv6 allowance applies to two locations only, so if you need a block of addresses, pick the datacenter accordingly rather than ordering first and asking later.

## VPS vs shared hosting vs a dedicated server vs a cloud VM

A VPS is a virtual machine carved out of a physical server that the provider owns and operates. You get a fixed slice of CPU, RAM and disk, your own operating system, and root access. Isolation is the point: a neighbour's compromised site cannot reach into your filesystem, and their traffic spike does not eat your memory.

The restaurant version: a VPS is a private room in a restaurant. You get your own table, your own key, and you order from the menu, but the kitchen and staff are shared. A dedicated server is renting the entire venue and hiring your own crew.

Where the four options sit:

- **Shared hosting** pools one server across many accounts with no guaranteed allocation. It's the cheapest and the least predictable under load.
- **A VPS** allocates a defined amount of resources and gives you an OS and root access. Traditional VPS plans run on a single physical server split into slices, billed at a flat monthly or annual rate, which keeps costs predictable for small workloads.
- **A dedicated server** reserves the whole machine. You pay for capacity you may not need.
- **A cloud VM** runs on a distributed pool instead of one box, can migrate automatically when hardware fails, and bills by consumption. That flexibility is what you pay for.

The line between VPS and cloud VM has blurred. Some providers now run their virtual servers on the same platform as their cloud products with a reduced feature set, so "VPS means one physical server" is a description of the traditional model, not a law.

One practical consequence of the traditional model: if the physical host fails, a single-server VPS goes down with it. RackNerd's budget tiers are the traditional kind. If you need automatic failover, that's a different product category and a different budget.

## Managed or unmanaged? The question that decides whether a $22 plan works for you

RackNerd's specials are unmanaged. The provider handles hardware, power, network connectivity and service availability. You handle the operating system, the firewall, the application stack, patching and anything that breaks inside the VM.

That division is standard across the industry. GoDaddy's own FAQ says unmanaged hosting requires advanced technical know-how and a basic understanding of Linux and the command line. AWS frames unmanaged hosting as suited to established businesses that already have the IT capability in-house.

A test that predicts the answer better than any feature list: can you SSH in, read a log file, and find out why a service failed to start? If yes, unmanaged is fine and the savings are real. If that sentence described a task you would have to Google from scratch, a $35.99 annual plan plus a managed service on top usually costs more than buying managed hosting in the first place.

The ctrl panel covers the routine operations without a terminal: rebooting, reinstalling the OS, opening a browser console when SSH is down, resetting the root password, and setting inbound firewall rules. It does not patch your applications, tune your database, or clean up after a compromised plugin.

## The costs the annual price does not show

This is where budget VPS comparisons usually stop short. The sticker price is accurate, and it is also incomplete.

**Renewal pricing.** RackNerd's own wording on the specials page is that plans renew at the same rate for as long as you keep the service. That is unusual in the budget segment, where a low first-term price followed by a higher renewal is the standard play. It also means the annual figure you see is the figure you will pay next year, so the comparison is honest.

**Backups.** Nothing on the product pages advertises automated backups or snapshots for these plans. Assume there are none and build an off-server routine from day one: a scheduled dump pushed to object storage or another machine, tested by actually restoring it once. Backup storage is not free anywhere; one mainstream host prices cloud backup from $0.065/GB/month, which is a reasonable yardstick for what a real backup strategy costs.

**Control panels.** ctrl is included. Plesk and cPanel are not. If you want one of those, price the licence and the disk it needs before choosing a tier. Plesk, for example, is listed at $6/month on one provider's VPS line and requires at least 20 GB of storage on Linux or 32 GB on Windows. On a 20 GB plan, the panel would consume the disk it was installed on.

**Extra IP addresses.** One dedicated IPv4 is included with every special. Additional addresses are billed separately almost everywhere; one provider charges $5/month per extra IPv4, which on a $21.99 annual plan would cost more than the server itself.

**Coupon codes.** The specials price is already the promotional price, so there is no code to hunt for. Codes circulating on coupon sites that promise a percentage off VPS plans are expired or apply to other product lines.

**Provisioning time.** Deployment happens minutes after payment, with the IP and root password arriving by email. That is faster than the fine print at some larger hosts, where the same FAQ admits provisioning can take up to 24 hours.

**RAM floors for one-click apps.** The ctrl catalog installs software directly, but the memory minimums are not negotiable. OpenClaw wants at least 8 GB. Hermes Agent, AnythingLLM, Ollama and LibreChat want at least 4 GB. n8n and Coolify are comfortable from 2 GB. A 1 GB plan is a fine lightweight web server and a bad place to run a local model.

If the annual commitment is the part giving you pause, the 2 GB tier is the safer place to spend it: $14 more per year buys headroom you will notice the first time a kernel update, a database import and a crawler arrive in the same hour.

👉 [Check the 2 GB KVM special and its current price](https://bit.ly/RacKnerd)

## Who should not buy one of these plans

An unmanaged annual VPS is the wrong purchase in four situations, and saying so is cheaper than finding out later.

- **You want someone else to fix things.** No managed tier on these specials. If a broken plugin at 11pm is not something you want to handle, buy managed hosting.
- **You need monthly flexibility.** These are annual plans. Cancelling in month three means paying for twelve. Project-based work with an unknown lifespan fits monthly billing better, even at a higher rate.
- **You need snapshots or automatic backups as product features.** They are not part of the offer. Build them yourself or choose a platform that bundles them.
- **You run one low-traffic site and have no interest in servers.** Shared hosting costs less and someone else handles updates. The VPS becomes worthwhile when you need root access, a specific runtime, or isolation from other tenants.

There is also a latency caveat worth checking before you commit. Budget nodes on ordinary transit can slow during peak evening hours for users in Asia, which is exactly what test IPs and looking glass tools exist to measure. Pick the datacenter closest to your users, and Los Angeles is the common choice for Asia-facing audiences.

## FAQ

**How long until the server is usable?**
Minutes after payment. You receive the IP and root password by email, then log in over SSH or through the ctrl console. If nothing arrives within an hour, open a support ticket rather than waiting.

**Can I install Windows?**
The order form lists Linux distributions: CentOS, Rocky Linux, AlmaLinux, Fedora, Debian and Ubuntu. Custom ISO installs go through a support ticket, so confirm licensing and feasibility with support before paying if Windows is a requirement.

**Do I need to buy a dedicated IP separately?**
No. One dedicated IPv4 is included with every special. Extra IPv6 addresses are free on request in Los Angeles and France, up to 100 per account.

**Can I move to a bigger plan later?**
The ctrl panel includes an upgrade function, so scaling up stays inside the same interface. Moving between datacenters or downgrading is a support request, not a self-service button.

**Are backups included?**
No. Set up your own from the first day and verify a restore, because an untested backup is a guess.

## Which tier to order

Match the workload, not the budget:

- Static site, reverse proxy, VPN endpoint, IRC bot, a box to learn Linux on → **1 GB at $21.99/year**.
- WordPress, a small MySQL or Postgres database, Docker with a few containers, n8n, Coolify → **2 GB at $35.99/year**.
- Ollama, LibreChat, AnythingLLM, Hermes Agent → **4 GB minimum**, so a tier above the 2 GB plan; OpenClaw needs 8 GB.
- Anything you want someone else to administer → none of these plans.

Two checks before you pay. First, ping the test IP or use the looking glass from your own location and from where your users are, because a datacenter that looks close on a map can route badly. Second, read the cancellation and refund terms on the order page, since these are annual commitments and the terms are stricter than a monthly plan's.

After that, the decision is mostly arithmetic: a year of root access on a KVM box for less than the price of two lunches, with the renewal locked at the same number.

👉 [Compare RackNerd's VPS specials and pick a tier](https://bit.ly/RacKnerd)
