# 1. Nobody could see the site

[Home](../README.md) · [Next →](02-getting-our-history-out.md)

## The problem

In September 2026, `www.mcgillxr.ca` redirected visitors to a Google sign-in page. The site
was a Google Site that wasn't public, so only accounts with access could see it. The bare
address, `mcgillxr.ca`, had no DNS record at all and had never worked.

On top of that, nobody on the current team had the login for the domain registrar.

## Finding the real blocker

I looked up the domain with WHOIS and `dig` on September 21:

- registered in April 2023, expiring April 2027
- locked against updates and transfers
- its only record was a `www` CNAME pointing to Google's hosting
- the nameservers were Google Cloud DNS

So Google Sites never controlled the domain. It only pointed there because of one DNS
record, managed outside Google Sites.

```mermaid
flowchart LR
    R[Registrar] --> D[Google Cloud DNS] --> G[Google Sites] --> W[Sign-in page]
```

That changed the plan. I didn't need access to the old Google Site. I needed the registrar
login, so I could unlock the domain and point it somewhere else. The old site could stay
exactly as it was.

## Working around it

I didn't want the missing login to hold everything up. I got the content out of the old
site, built the new one, and deployed it to a temporary Cloudflare address on October 9 so
the team could review it. The missing login only blocked the domain move at the very end.

## What I'd change for next time

The domain, the hosting account and the code should all belong to the club, with at least
two owners and auto-renew on, and be handed over before a term ends. I wrote that into the
handoff document so the next VP Technology doesn't inherit the same problem.
