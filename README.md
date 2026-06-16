# Tired of Sharing Your Root VPS Password With the Whole Team? Here's How VPS Sub Accounts Work, Which Cheap Providers Actually Include Them, and How to Set One Up (Plus a Full Plan & Pricing Breakdown)

If you've ever typed your root password into a group chat so a freelance developer could "just quickly fix one thing," you already know the problem. One person needs to install a script, another needs to check an invoice, a third just wants server uptime stats — and somehow they all end up with the same all-powerful login. That's the moment most people start typing "VPS sub accounts" into Google, usually right after something has gone slightly (or very) wrong.

The good news is that **VPS sub accounts** aren't some exotic enterprise feature locked behind a $200/month plan anymore. A handful of budget VPS providers now bake this kind of access control directly into their control panels — no extra software, no third-party permission hacks, no "just don't touch that folder" honor system. This guide walks through what sub accounts actually do, who needs them, how the feature tends to be implemented, and takes a close look at one provider — Evoxt — that includes role-based sub accounts across its entire VPS lineup, alongside a full breakdown of its plans and pricing.

## What Are VPS Sub Accounts, Exactly?

A VPS sub account is essentially a second (or third, or tenth) login to your hosting control panel that belongs to someone else — but with permissions you define. Instead of handing over your master credentials, you create a separate identity for a teammate, contractor, or department, and decide exactly what corner of your account they're allowed to touch.

This is different from creating a new user *inside* the operating system of your virtual machine (like adding a Linux user with `adduser`). That's still useful, but it only controls access to the server itself. VPS sub accounts, on the other hand, usually live at the **billing/control panel level** — the dashboard where you manage invoices, deploy new servers, configure firewalls, request backups, and so on. That's the layer where most "I accidentally gave the wrong person too much access" disasters actually happen.

In short:

- **OS-level user accounts** control what someone can do *inside* a running server.

- **VPS sub accounts** control what someone can do *to* your hosting account — billing, server management, support tickets, deployments — from the provider's dashboard.

Most people searching for "VPS sub accounts" are actually looking for the second kind, because that's where the real risk (and the real headache) tends to live.

## Why People Actually Need This Feature

It's easy to dismiss sub accounts as a "nice to have," until you're the one frantically resetting a shared password at midnight. Here are the situations where this feature stops being optional:

1. **Agencies managing client servers.** If you run a web agency, you might have five developers who need server access but zero reason to see the client's invoice history or payment method.

2. **Outsourced support or billing.** Plenty of small businesses hire a part-time bookkeeper or virtual assistant to handle renewals and invoices — but that person has no business rebooting a production server.

3. **Technical teams with different specialties.** One person handles firewall rules and backups, another handles deployments, and neither needs the other's permissions.

4. **Onboarding and offboarding.** When someone leaves the team, you revoke *their* sub account — without touching the master login that everything else depends on.

5. **Compliance and audit trails.** Shared logins make it impossible to know who did what. Separate sub accounts mean every action is tied to an actual person.

> The common thread here isn't "we don't trust our team." It's the much more boring (and much more important) principle of **least privilege** — give people exactly the access they need to do their job, and nothing more.

## How VPS Sub Accounts Typically Work (Roles & Permissions)

Most providers that offer this feature organize sub accounts around **roles** rather than asking you to tick a hundred individual permission boxes. The roles tend to map pretty closely to how a small team is actually structured:

| Role | Typical Access | Who It's For |

|---|---|---|

| Administrator | Full or near-full account access | Owners, senior staff |

| Technical Team | Server management, firewall, backups, deployments | Developers, sysadmins |

| Billing Team | Invoices, payment methods, renewals | Bookkeepers, finance staff |

| Support Team | Tickets, account communication | Customer-facing staff, VAs |

This kind of structure shows up across a lot of hosting platforms — cPanel's "Manage Team" feature, for example, lets you create team users with roles like Database, Email, and Web access for a single hosting account. The pattern is consistent: define a role, assign a person, done. No need to share the keys to the kingdom.

What varies a lot between providers is *where* this feature lives. Some bury it three menus deep inside an enterprise control panel. Others — including the provider we're about to look at — build it directly into the main VM management dashboard, available on every plan from the cheapest tier up.

## A Closer Look: Evoxt's Sub Accounts Feature

Evoxt is a Malaysia-based VPS provider that's built its whole pitch around two things: unusually high single-core CPU clock speeds (up to 6.0 GHz, compared to the 2.2–2.4 GHz baseline you'll see from some major cloud platforms) and refusing to nickel-and-dime customers with hidden fees. Less talked about, but directly relevant here, is that **Sub Accounts is listed as a standard feature of the VM control panel** — sitting right alongside monitoring, firewall, IP management, cloning, backups, VNC access, and API control.

The way Evoxt frames it on their dashboard is refreshingly close to the real-world problem described above: *"Require access to be given for each Administrator, Technical Team, Billing Team, Support Team? We've got that covered for you."* That's essentially the exact role breakdown most small teams and agencies are looking for when they search for VPS sub accounts in the first place — you're not stuck building your own workaround with shared spreadsheets and "please don't click that" warnings.

What makes this combination interesting from a practical standpoint is that sub accounts work *alongside* Evoxt's other management tools rather than as an isolated feature:

- **Technical Team** sub accounts can be scoped toward firewall configuration, cloning, VNC console access, and backup restores — the day-to-day server work.

- **Billing Team** sub accounts can handle renewals, credit top-ups, and invoice history without ever seeing server credentials.

- **Support Team** sub accounts can manage tickets and communications, which is handy if you outsource customer support for a reselling setup.

- **API Credentials** management sits in the same account area, so technical sub accounts can also be handed scoped API access for automation — useful if you're managing infrastructure as code rather than clicking through a dashboard every time.

If you want to see the dashboard where sub accounts and the rest of the account tools live, — the "Manage Users" section under account settings is where sub accounts get created and assigned roles.

## Full Evoxt VPS Plan & Pricing Breakdown

One of the more refreshing things about Evoxt is the pricing philosophy printed right on their site: *"If you order a $2.99 plan, you will pay $2.99. We don't charge any extra bandwidth fees or any CPU burst fees."* No surprise overage charges, no asterisk-laden "starting from" pricing that doubles after a teaser period.

Here's the full lineup of Evoxt's Cloud Virtual Machine plans, available across the **Standard network** (United States, United Kingdom, Canada, Germany, Poland, Amsterdam, Japan/Tokyo, Malaysia, and Australia). Every plan includes a 1 Gbps port, automatic weekly offsite backups, IPv6, and — relevant to this whole article — the Sub Accounts feature on the same dashboard:

| Plan | CPU | RAM | Storage | Monthly Transfer | Backup | Price | Order |

|---|---|---|---|---|---|---|---|

| VM-0.5 | 1 core (up to 6.0 GHz) | 512 MB | 5 GB | 500 GB | Weekly | $2.99/mo | |

| VM-0.75 | 1 core (up to 6.0 GHz) | 1 GB | 10 GB | 750 GB | Weekly | $4.99/mo | |

| VM-1 | 1 core (up to 6.0 GHz) | 2 GB | 20 GB | 1000 GB | Weekly | $5.99/mo | |

| VM-1.5 | 2 cores (up to 6.0 GHz) | 2 GB | 20 GB | 1500 GB | Weekly | $6.95/mo | |

| VM-2 | 2 cores (up to 6.0 GHz) | 4 GB | 30 GB | 2000 GB | Weekly | $11.99/mo | |

| VM-3 | 4 cores (up to 6.0 GHz) | 4 GB | 30 GB | 3000 GB | Weekly | $14.99/mo | |

| VM-4 | 4 cores (up to 6.0 GHz) | 8 GB | 60 GB | 4000 GB | Weekly | $23.99/mo | |

| VM-6 | 8 cores (up to 6.0 GHz) | 8 GB | 60 GB | 5000 GB | Weekly | $29.99/mo | |

| VM-8 | 8 cores (up to 6.0 GHz) | 16 GB | 80 GB | 6000 GB | Weekly | $47.99/mo | |

| VM-12 | 16 cores (up to 6.0 GHz) | 16 GB | 80 GB | 8000 GB | Weekly | $60.95/mo | |

| VM-16 | 16 cores (up to 6.0 GHz) | 32 GB | 100 GB | 10 TB | Weekly | $95.99/mo | |

The same plan names (VM-0.5 through VM-16) are also available with identical specs on two additional networks, with slightly different bandwidth allowances and one pricing tweak:

- **Premium Network** (Hong Kong, Japan/Osaka): identical specs and prices to Standard, but with lower monthly transfer allowances (e.g. 250 GB on VM-0.5/0.75 up to 5 TB on VM-16) — aimed at users who specifically want optimized Asia-Pacific routing.

- **Premium Plus Network** (Malaysia Premium): same specs as Standard, with its own transfer tiers (150 GB up to 4 TB), and one price difference — the entry-level VM-0.5 here is $3.49/mo instead of $2.99/mo.

If your workload is latency-sensitive and your users are mostly in Asia, the Premium or Premium Plus networks are worth selecting during deployment; otherwise, Standard covers the widest spread of global locations.

## Scaling Resources Without Switching Plans

Here's something that matters once you've got a team using sub accounts to manage a server: nobody wants to do a full migration just because you need 2 extra GB of RAM. Evoxt lets you bump individual resources up from the VM control panel's Upgrade tab, rather than forcing a plan change:

- **Extra IP Address** — $3/month per additional IP.

- **Extra CPU Cores** — $3/month per vCore

- **Extra RAM** — $2/month per GB

- **Extra Monthly Transfer** — $3/TB (Standard), $12/TB (Premium), $24/TB (Premium Plus)

- **Paid Backup Plan** — variable, based on VM storage size, for retention beyond the free weekly backup

For a team setup, this matters in a quiet but practical way: your "Technical Team" sub account can request these upgrades through the same dashboard where they already manage firewalls and backups, without anyone needing to involve billing for a routine RAM bump.

## Current Promo Codes & Deals

Pricing is already on the low end across the board, but there's a recurring discount code that's been circulating for Evoxt's VM-1 plan and above: **EVOXT595**, reportedly applying a **40% recurring discount** at checkout. As with any promo code, terms and availability can shift without notice, so it's worth simply trying it in the coupon field during checkout — if it's expired, you'll still be paying the already-transparent base price with no hidden surprises.

## Is Evoxt a Good Fit for Teams That Need Sub Accounts?

Let's be honest about the trade-offs, because no provider is a perfect fit for everyone.

**Where Evoxt makes sense:**

- Small agencies or freelance dev shops that need to give a few people scoped access without paying for an enterprise hosting plan

- Anyone who wants billing handled by one person and server management handled by someone else, on the same account

- Budget-conscious teams — entry plans start under $3/month, and the sub accounts feature isn't gated behind a higher tier

- Projects that benefit from genuinely fast single-core performance: WordPress sites, Discord bots, lightweight databases, development/staging environments

- Global teams, thanks to 16 data center locations spanning North America, Europe, and Asia-Pacific

**Where you might want to look elsewhere:**

- If you need a heavily managed experience where the provider's own staff handles all server administration (Evoxt is unmanaged — you or your technical sub account members are responsible for OS-level configuration)

- If you need dozens of full cPanel hosting accounts under one roof for a reselling business — that's a different product category than a general-purpose VM

- If 24/7 instant live chat support is a hard requirement; support is ticket-based, and response times during peak periods have been reported as inconsistent in some third-party reviews

For the specific use case this article started with — a small team that needs to stop sharing one root password — Evoxt's combination of low entry pricing, role-based sub accounts, and a relatively clean dashboard makes it a reasonable place to start without overcommitting.

## How to Set Up Sub Accounts on Evoxt (Step by Step)

1. if you don't already have one — registration just needs basic details.

2. Deploy your VM. — pick your region (Standard, Premium, or Premium Plus) and OS during setup; most deployments are ready within a couple of minutes.

3. Log into the client area and locate the **Manage Users** section under account settings — this is where sub accounts live.

4. Add a new sub account by entering the person's email address and assigning a role: Administrator, Technical Team, Billing Team, or Support Team.

5. The invited team member receives access scoped to that role only — they won't see areas outside their assigned permissions.

6. Repeat for each team member, and remove sub accounts immediately when someone's role changes or they leave the project — this is the whole point of not sharing a single login in the first place.

## Frequently Asked Questions

**Do all Evoxt plans include the sub accounts feature, or is it only on higher tiers?**

Sub Accounts is listed as a core feature of the VM control panel across the lineup, alongside monitoring, firewall, and API access — it isn't presented as a higher-tier add-on.

**Is sub-account access the same as giving someone root access to my VM?**

No. Sub accounts control access to your *Evoxt dashboard* (billing, deployments, server management tools). Whether a sub account holder also gets OS-level root access to a specific VM is a separate decision you make once they're inside the control panel.

**Can I limit a sub account to billing only, so they never see my servers?**

Yes — assigning the Billing Team role is designed for exactly this: invoice and payment management without server-level visibility.

**What happens to a sub account if I downgrade or change my plan?**

Sub accounts are tied to your overall Evoxt account rather than a single VM, so changing a plan's specs doesn't remove your configured sub accounts — you'd only need to revisit access if a sub account was tied to a specific server you've since removed.

**Is there a difference between "VPS sub accounts" and creating extra Linux users on the server itself?**

Yes, and it's worth keeping straight. OS-level Linux users (created via SSH) control access *inside* the running server's operating system. VPS sub accounts, as covered in this guide, control access to the provider's management dashboard — billing, deployments, firewall rules, backups, and so on. Most teams end up using both: dashboard sub accounts for account management, and separate OS users for actual server logins.

---

If the core problem that brought you here was "I need to stop sharing one login with my whole team," role-based sub accounts solve that specific headache without requiring a jump to enterprise-priced hosting. 👉 [Take a look at Evoxt's plans and deploy your first VM here](https://console.evoxt.com/deploy.php?aff=3510) to see the sub accounts setup in your own dashboard.
