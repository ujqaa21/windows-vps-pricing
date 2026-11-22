# Cheapest Windows VPS: Is $3.99 a Month Real, How Many RDP Users Do You Get, and What Happens When the Licence Runs Out?

The cheapest Windows VPS listings are real numbers. MassiveGRID advertises a shared-vCPU Windows VPS from **$3.99/month**. Contabo shows **€4.40/month for the first 24 months** on its smallest Windows cloud VPS. AVA Hosting's Windows line starts at **€5.00/month** for 1 vCPU, 2 GB RAM and 25 GB NVMe with a dedicated IPv4.

None of those figures is invented. None of them is the full bill either. Two items usually sit outside the headline price: a licensed copy of Windows, and Remote Desktop sessions past the first two. A third arrives later, when the introductory rate ends and the renewal invoice shows a different number.

What follows is the arithmetic behind those three items, what a low-end Windows box can actually run, verified prices from four other providers, and a checklist to put to any host before you pay.

> **Quick pick:** one person, one Windows desktop, no appetite for patching it yourself. AVA Hosting's managed Windows VPS page lists an entry tier at €5.00/month with 1 vCPU, 2 GB RAM, 25 GB NVMe and a dedicated IPv4, and standard purchases carry a 30-day refund window. 👉 [Check AVA Hosting's Windows VPS plans and current prices](https://my.ava.hosting/aff.php?aff=15562)

## What AVA Hosting lists, and what the quote still has to answer

AVA's Windows VPS pages state the two ends of the range explicitly: €5.00/month for 1 vCPU with 2 GB RAM and 25 GB NVMe at the bottom, €40.00/month for 8 vCPU with 16 GB RAM and 160 GB NVMe at the top. The tiers in between are picked in the plan selector on the order page, so the exact configuration and price should be confirmed there before checkout.

| Configuration as listed | vCPU / RAM | Storage | Price | Order |
| --- | --- | --- | --- | --- |
| Entry tier | 1 vCPU / 2 GB | 25 GB NVMe | €5.00/mo | [Check this plan](https://my.ava.hosting/aff.php?aff=15562) |
| Largest tier | 8 vCPU / 16 GB | 160 GB NVMe | €40.00/mo | [Check this plan](https://my.ava.hosting/aff.php?aff=15562) |

Every plan in the line ships with a dedicated IPv4 address, KVM virtualisation, a 1 Gbps network port, DDoS mitigation and NVMe storage, with 24/7 technical support. AVA describes each plan as getting a fixed number of virtual cores rather than a share of a busy host, which is the claim worth testing during the refund window rather than taking on faith. Control panels are paid additions (Plesk, cPanel, ispmanager, DirectAdmin); a free panel can be installed by the customer instead.

The managed side is the reason the €5.00 entry point is interesting. AVA's technical team handles OS provisioning, Windows Server patch management, IIS bindings and application pools, Windows Firewall rules, and component upgrades, and SQL Server runs natively on the same instance. If your reason for wanting Windows is a .NET app, a SQL Server Express database or a piece of accounting software that only exists as a Windows binary, that work is normally billed as your evening.

Two commercial details matter as much as the price. Standard purchases can be refunded within 30 days. **Orders paid with a promotional code or a discount are not refundable**, and dedicated servers are refunded minus a €5 setup fee and a 30% processing fee. If you plan to test and possibly walk away, pay the standard rate.

👉 [Compare AVA Hosting's Windows VPS configurations](https://my.ava.hosting/aff.php?aff=15562)

## The three bills hiding behind a $3.99 sticker

### Windows Server licensing is often not in the price

MassiveGRID spells out what most hosts leave in the small print. Every Windows Server template (2016, 2019, 2022, 2025) installs as a Microsoft evaluation image at zero licence cost. You activate online within 10 days, get full functionality for **180 days**, and the desktop shows a countdown. On day 181 the data and applications stay on disk, but the server **shuts itself down every hour** and only accepts security updates until a licence is attached. Adding the licence is an in-place conversion, no reinstall.

The licence is available separately at **$6.31 per vCPU**. On a 4-vCPU box that is $25.24/month, which is more than the VPS itself. A 180-day evaluation is genuinely useful for a migration or a short project. It is a trap for anything meant to stay online into next year, because an hourly shutdown ends remote-desktop work, bot sessions and scheduled jobs at random.

Desktop Windows works differently. Windows 11 Pro and Windows 10 Pro templates install unactivated and you enter your own product key, because Microsoft does not let hosting providers rent desktop Windows licences. Desktop editions also allow a single interactive session. Anyone promising a "$4 Windows 11 VPS" with a licence included is either selling you an unactivated template or something that will not survive an audit.

### The third person who wants to log in

Windows Server includes **two administrator sessions** by default. That is a Microsoft number, not a host being stingy, and it applies to every provider in this article. The third concurrent user needs an RDP licence at **$8.90 per user per month** on MassiveGRID.

Run the total for a three-person team on the cheapest tier: $3.99 for the VPS, $6.31 for one vCPU of Windows Server licensing, $8.90 for the extra session. **$19.20/month.** The $3.99 sticker was accurate and the real cost was five times higher. If three or more people need to be in the machine at once, price the whole stack before comparing hosts, because the licence line is where the cheap option stops being cheap.

### The month the introductory price ends

Contabo labels its Windows CLOUD VPS prices "for the first 24 months". CLOUD VPS 4 shows €4.40/month against a €5.50 standard rate; CLOUD VPS 8 shows €11.20 against €14.00. From month 25 the standard rate applies, so a three-year term on CLOUD VPS 4 costs €171.60 rather than the €158.40 the intro price implies.

Fasthosts runs a shorter clock. VPS 2 is £22/month normally and **£14/month for 3 months**, on a 1- or 12-month contract. Spread over a year on the 12-month term that is £240, not the £168 that £14 times twelve suggests. Neither structure is dishonest, and both are cheaper than the standard rate for as long as they last. Just put the renewal figure in the spreadsheet before you commit to a 12- or 24-month term.

## What the cheapest tier can run, and where it stops

MassiveGRID splits its Windows products along a line worth copying when you evaluate anyone's range: **shared vCPU from $3.99/month** and **dedicated (reserved) cores from $18.84/month**, a 4.7× gap.

Shared vCPU suits a remote desktop for one or two people, a small IIS site, accounting or practice-management software, and a handful of automation bots. Reserved cores are for SQL Server with real load, IIS under constant traffic, three or more RDP users, emulator farms, and SEO tools that pin the CPU at 100% for hours. If your workload idles most of the day and spikes occasionally, shared is fine. If a neighbour's workload can slow your invoice run, you need reserved cores.

Memory is the other hard floor. A 1 GB Windows Server instance boots and runs a desktop, which is why $3.99 exists. Windows 11 Pro needs at least 2 GB, so its smallest configuration on MassiveGRID is 1 vCPU, 2 GB, 32 GB NVMe at **$4.79/month**, with your own key. AVA's entry tier starts at 2 GB for €5.00, which puts it in the same bracket as that Windows 11 Pro minimum while remaining a server edition with two RDP sessions.

On versions: **Windows 10 reached end of support on 14 October 2025** and no longer receives security updates. Legacy templates still exist for old software, but a new deployment should be Windows 11 Pro or Windows Server 2025, with 2019 and 2022 kept for applications not yet certified on the newer release.

## Verified Windows VPS prices, side by side

Four providers, listed prices only, no promotions attached. Currency and tax treatment differ, so compare the billing note before the number.

| Provider | Entry Windows configuration | Displayed price | Billing note | Known limit |
| --- | --- | --- | --- | --- |
| MassiveGRID | Windows VPS, shared vCPU, 1 GB (Windows Server Starter) | $3.99/mo | USD, monthly | Licence is 180-day evaluation or $6.31/vCPU; 2 admin RDP sessions |
| Contabo | CLOUD VPS 4: 4 vCPU / 8 GB / 100 GB SSD | €4.40/mo for the first 24 months, €5.50 standard | EUR, unmanaged | Pre-installed Windows Server Standard 2016–2025; 9 regions, 11 datacentres; unlimited traffic |
| OVHcloud | VPS-2: 4 vCores / 8 GB / 75 GB NVMe | from US$8.50/mo ex. GST | USD, taxes excluded | Unlimited traffic excludes Asia-Pacific datacentres; Local Zones do not support Windows |
| Fasthosts | VPS 2: 2 vCPU / 4 GB / 120 GB NVMe | £14/mo for 3 months, then £22 | GBP, 1- or 12-month contract | UK, Germany, Spain or US datacentres; Plesk £5/mo extra |

A note on Fasthosts' uptime figure: the specification table lists a 99.999% SLA while the FAQ text on the same page says 99.99%. Two different numbers from one source, so treat the guarantee as unconfirmed until it appears in your contract.

IONOS belongs in the shortlist on features but not in a price table here, because the plan pages I could inspect listed Windows L+ at 4 vCores, 8 GB and 240 GB NVMe without a visible price. Its published claims are 99.99%+ uptime, unlimited traffic, no setup fee, 31 datacentres and ISO 27001 certification, with Windows accessed over RDP. One limit is worth quoting in full because it is easy to miss: **once you choose Windows on an IONOS virtual server, you cannot switch that server to Linux later**; you would have to order again. Their Cloud Server line keeps the operating system flexible.

## Choosing a tier without overbuying

- **One person, one Windows application, always on.** Lowest shared-vCPU tier, 2 GB RAM, evaluation licence only if the project ends within six months. AVA's €5.00 entry tier fits this shape and includes the patching work.
- **Two people sharing a desktop.** Same tier. Two administrator sessions are included on Windows Server at no cost.
- **Three or more concurrent RDP users.** Add the RDP licence cost to every quote before comparing, then check whether reserved cores are needed for the load those users create.
- **SQL Server, IIS under constant traffic, or CPU-heavy automation.** Go straight to reserved cores. A $3.99 shared box that spends the afternoon throttled costs more in lost hours than the $18.84 upgrade.
- **A project with a defined end date under six months.** An evaluation licence and a 3-month introductory price are a legitimate combination. Diarise the day the evaluation expires so the hourly shutdown doesn't surprise you mid-demo.
- **Anything with a compliance or continuity requirement.** Buy the licence on day one and read the refund exclusions first, since discounted orders are commonly non-refundable.

## FAQ

**Does a $3.99 Windows VPS include the Windows licence?**
Usually not. On MassiveGRID it is a 180-day evaluation image, with a real licence at $6.31 per vCPU. Desktop editions cannot be resold by any host at all, so Windows 11 Pro runs on your own product key. Ask every provider which of the two you are buying.

**What happens when the 180-day evaluation ends?**
The data and installed applications survive. The server shuts down every hour and receives only security updates until a licence is added, which is done in place without reinstalling.

**Is 1 GB of RAM enough?**
For a bare Windows Server desktop with a light application, yes. For Windows 11 Pro, no, since 2 GB is the floor. AVA's entry tier starts at 2 GB, which removes the question.

**How many people can log in at the same time?**
Two administrator sessions on Windows Server by default. Each additional concurrent user needs an RDP licence, quoted at $8.90 per user per month on MassiveGRID.

**Can I switch a Windows VPS to Linux later?**
Depends on the provider. IONOS states plainly that a Windows virtual server cannot be converted to Linux afterwards. If you might change your mind, confirm the policy in writing before ordering, or pick a product line that allows reimaging.

**Do I still have time to move off Windows 10?**
Windows 10 support ended on 14 October 2025. New deployments should use Windows 11 Pro or Windows Server.

## Before you order

Match the tier to the number of people who need to be inside the machine, not to the size of the price on the landing page. Most single-user workloads are served by the cheapest shared tier with 2 GB of RAM. Every workload with a third concurrent user or a database under real load needs the licence and reserved-resource maths done first.

Two questions to settle with the host before paying: whether the quoted price includes a licensed Windows Server or an evaluation image, and what the renewal price is after the introductory period ends. At AVA Hosting the entry Windows tier is listed at €5.00/month with a 30-day refund window on standard-rate orders, which is enough time to check patching, RDP behaviour and disk speed on your own workload. 👉 [Start with AVA Hosting's current Windows VPS offer](https://my.ava.hosting/aff.php?aff=15562)
