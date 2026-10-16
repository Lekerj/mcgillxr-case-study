# 1. Nobody could see the site

[← Back](../README.md) · [Next →](02-getting-our-history-out.md)

## The problem

`www.mcgillxr.ca` led to a Google sign-in page, and `mcgillxr.ca` didn't load at all. On top
of that, nobody on the team had the login for the domain.

## Finding the real blocker

The obvious fix was to make the Google Site public again. Instead I traced where the domain
actually pointed. It turned out Google Sites never controlled it. A single DNS record did.

```mermaid
flowchart LR
    R[Registrar] --> D[Google DNS] --> G[Google Sites] --> W[Sign-in page]
```

That changed the plan. I didn't need access to the old site at all, only the registrar
login. With that, I could point the domain somewhere new and leave the old site alone.

## Working around it

I didn't want the missing login to block everything. So I pulled the content out first,
built the new site, and deployed it to a temporary address. The login only blocked the very
last step.

## What I'd change for next time

Every account belongs to the club, with at least two owners and auto-renew turned on. That
one rule would have prevented the whole situation.
