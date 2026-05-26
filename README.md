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

Fenrir is priced as a hosted access-control layer for paid communities, operators, and agencies — not as a generic link shortener.

| Plan | Price | Best For | Included |
| --- | ---: | --- | --- |
| Free Preview | $0 | Testing the lock flow | 1 domain, 1 Telegram lock, basic DNS guide, manual invite rotation |
| Starter | $9/mo | Small communities | 1 domain, 3 Telegram locks, Turnstile gate, username/name/surname checks, basic audit log |
| Pro | $19/mo | Paid communities | 3 domains, 10 Telegram locks, membership gate, Telegram profile completeness checks, optional photo check, invite rotation history |
| Operator | $49/mo | Serious operators | 10 domains, 50 Telegram locks, required/optional photo check, advanced audit events, priority bot checks, custom gate rules |
| Agency | $99/mo | Multi-client operators | 25 domains, 150 Telegram locks, client workspaces, branded gate pages, exportable reports, priority setup support |

### Add-ons

| Add-on | Price | Included |
| --- | ---: | --- |
| Extra domain pack | $5/mo | +5 domains |
| Extra lock pack | $5/mo | +25 Telegram locks |
| White-label gate page | $19/mo | Custom logo, colors, and branded verification copy |
| Done-for-you setup | $49 one-time | DNS, bot permission check, and first lock setup |
| Operator onboarding | $149 one-time | Multi-domain setup, gate policy configuration, and launch review |

### Pricing Notes

- Free Preview is intentionally limited and should not be used for active paid communities.
- Starter should be cheap enough for a real community admin, but not so cheap that support becomes unprofitable.
- Pro is the default recommendation for paid communities.
- Operator and Agency plans include the advanced verification controls that reduce abuse and support load.
- Photo checks should be treated as a premium verification feature, especially when configured as required.

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
