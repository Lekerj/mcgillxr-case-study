# 7. Moving the domain without breaking anything

[← Previous](06-the-menu-flickered-on-3g.md) · [Back](../README.md) · [Next →](08-photos-of-real-people.md)

**Problem.** Shared links showed a grey box. The site was telling apps to fetch preview
images from a domain that didn't work yet.

**What I did.** I pointed previews at the temporary address and set one rule: don't switch
back until the preview image loads on the real domain.

**The move.** I didn't need to transfer the domain anywhere, only repoint its nameservers.
I did it in an order that could be undone at every step, and the final switch was a
one-line config change.

**Result.** `mcgillxr.ca` is live. `www` serves the same pages and points search engines at
the main address, and the old Google Site was never touched.
