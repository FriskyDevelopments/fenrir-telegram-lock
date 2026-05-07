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
5. Fenrir creates a stable lock URL.
6. When an invite leaks, Fenrir rotates it behind the same URL.

## Pricing Draft

| Plan | Price | Included |
| --- | ---: | --- |
| Free | $0 | 1 domain, 1 Telegram lock |
| Starter | $3/mo | 3 Telegram locks |
| Pro | $7/mo | 10 Telegram locks |
| Operator | $15/mo | Unlimited Telegram locks |

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

For sensitive access questions, use private contact with Frisky Developments.
