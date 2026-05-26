# Fenrir Telegram Lock by Frisky

Lock Telegram groups behind your own domain.

Fenrir Telegram Lock lets Telegram group admins share a stable URL from their own domain instead of exposing raw Telegram invite links.

```text
https://join.customer-domain.com/main
```

If an invite leaks, the admin rotates or revokes the Telegram invite while the public domain URL stays the same.

## What It Does

- Keeps Telegram invite links private behind a stable customer-owned domain
- Rotates leaked Telegram invites without changing the public URL
- Revokes access when a group, campaign, or paid community needs a lock down
- Guides admins through DNS setup with Cloudflare as the recommended path
- Checks whether the Telegram bot has the right admin permissions
- Tracks audit events for sensitive access changes
- Supports configurable community verification rules such as username, first name, surname, Turnstile, and optional Telegram profile photo checks

## Product Position

Fenrir is not a generic hosting product. It is a Telegram access-control product.

The domain bridge is infrastructure. The customer-facing promise is simple:

```text
Stop sharing raw Telegram invite links.
Use your own domain.
Rotate invites anytime.
Keep the public link forever.
```

## Example Flow

1. Admin connects `join.customer-domain.com`.
2. Fenrir shows the exact DNS records to add.
3. Cloudflare DNS verifies the domain and issues SSL.
4. Admin connects a Telegram chat ID.
5. Admin configures the community gate rules.
6. Fenrir creates a stable lock URL.
7. Users verify through Telegram, Turnstile, and membership checks.
8. When an invite leaks, Fenrir rotates it behind the same URL.

## Pricing Draft

Fenrir should keep the original simple tier ladder: Free, Starter, Pro, and Operator.

The product should feel affordable for small Telegram communities, but not so cheap that DNS setup, bot support, abuse prevention, and custom verification work become unprofitable.

### Recommended Public Pricing

| Plan | Price | Best For | Included |
| --- | ---: | --- | --- |
| Free | $0 | Testing the lock flow | 1 domain, 1 Telegram lock, basic DNS guide, manual invite rotation |
| Starter | $5/mo | Small communities | 1 domain, 3 Telegram locks, Turnstile gate, username/name/surname checks, basic audit log |
| Pro | $12/mo | Paid communities | 3 domains, 10 Telegram locks, membership gate, Telegram profile completeness checks, optional photo check, invite rotation history |
| Operator | $29/mo | Serious operators | 10 domains, 50 Telegram locks, required/optional photo check, advanced audit events, priority bot checks, custom gate rules |

### Founder / Beta Offer

Founder and beta customers can receive their first year free as a launch incentive.

| Plan | Year 1 | After Year 1 | Positioning |
| --- | ---: | ---: | --- |
| Free | $0 | $0 | Testing only |
| Starter Founder | $0 for 12 months | $5/mo | Early small communities |
| Pro Founder | $0 for 12 months | $12/mo | Early paid communities and strongest default offer |
| Operator Founder | $0 for 12 months | $29/mo | Selected operators who give feedback and help validate scale |

### Founder Renewal Discount

When the free founder year is ending, offer a retention discount instead of extending free access forever.

| Plan | Normal Renewal | Founder Renewal Offer | Suggested Use |
| --- | ---: | ---: | --- |
| Starter | $5/mo | $3/mo for 6 months | Good for small communities that are active but price-sensitive |
| Pro | $12/mo | $7/mo for 6 months | Best default renewal save offer |
| Operator | $29/mo | $15/mo for 6 months | Use only for operators who are active, useful, or strategically valuable |

### Founder Offer Rules

- Keep founder access limited and invite-only.
- Do not call this a permanent discount.
- Require useful feedback, bug reports, testimonials, or case-study permission when possible.
- Founder users keep their same tier for the free year, then convert to the normal public monthly price unless a renewal discount is offered.
- Send the renewal discount near the end of the free year, not at signup.
- Renewal discounts should be time-limited, usually 6 months.
- For high-support operators, require manual approval before granting the free Operator year or the Operator renewal discount.
- Use founder access to build proof, not to create unlimited free support obligations.

### Add-ons

| Add-on | Price | Included |
| --- | ---: | --- |
| Extra domain pack | $5/mo | +5 domains |
| Extra lock pack | $5/mo | +25 Telegram locks |
| White-label gate page | $12/mo | Custom logo, colors, and branded verification copy |
| Done-for-you setup | $39 one-time | DNS, bot permission check, and first lock setup |
| Operator onboarding | $99 one-time | Multi-domain setup, gate policy configuration, and launch review |

### Pricing Notes

- Do not add an Agency tier yet. Keep the ladder simple until real operator demand appears.
- Free should stay limited and should not be used for active paid communities.
- Starter should stay cheap enough for one small community owner to say yes quickly.
- Pro should be the default recommendation for paid communities.
- Operator should stay below $30/mo during the early product phase, then increase later if support demand proves high.
- Photo checks should be treated as a premium verification feature, especially when configured as required.
- The original $3 / $7 / $15 pricing works best as a temporary founder renewal discount, not the permanent public price.

## DNS Note

Frisky tip: You can keep any registrar you want. DNS does not change who owns or renews the domain.

Cloudflare is recommended for DNS and certificates because it makes custom hostnames easier to automate.

## Current Status

Private MVP is in development.

This public repo is intentionally a showcase and exposure surface. It does not contain the private application source code, backend logic, credentials, customer data, Telegram bot tokens, or deployment configuration.

## Interested?

Open an issue in this repo with:

- Your Telegram group use case
- How many groups you manage
- Whether you already own a domain
- Whether you want the hosted version or operator setup

## Security

Do not post Telegram invite links, bot tokens, private DNS tokens, Cloudflare API tokens, or customer data in public issues.

For sensitive access questions, use private contact with Frisky Developments. See [SECURITY.md](SECURITY.md) for the full policy and scope.
