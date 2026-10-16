# 1. Nobody could see the site

[← Back](../README.md) · [Next →](02-getting-our-history-out.md)

**Problem.** `www.mcgillxr.ca` led to a Google sign-in page and `mcgillxr.ca` didn't load at
all. Nobody on the team had the domain login.

**What I figured out.** Google Sites didn't control the domain. One DNS record pointed it
there. So I didn't need access to the old site. I needed the registrar login, and then I
could repoint the domain and leave the old site untouched.

```mermaid
flowchart LR
    R[Registrar] --> D[Google DNS] --> G[Google Sites] --> W[Sign-in page]
```

**Decision.** I didn't let the missing login hold everything up. I pulled the content out,
built the new site and deployed it to a temporary address first. The login only blocked the
last step.

**Lesson.** Club accounts belong to the club, with two owners and auto-renew on. That alone
would have prevented all of this.
