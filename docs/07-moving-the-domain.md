# 7. Moving the domain

[← Previous](06-the-menu-flickered-on-3g.md) · [Home](../README.md) · [Next →](08-photos-of-real-people.md)

## The problem

Links shared on Instagram and Discord showed a grey box instead of a preview. The site was
telling those apps to fetch images from a domain that didn't work yet.

## A safe stopgap

I pointed the previews at the temporary address in the meantime, with one rule: don't switch
to the real domain until its preview image actually loads.

## Making the switch

The domain didn't have to be transferred anywhere. I only had to change where it pointed. I
did it in an order that could be undone at every step, and the final switch was a single line
in the config.

## The result

`mcgillxr.ca` is live. `www` shows the same site and tells search engines the main address is
the one to index. The old Google Site was never touched.
