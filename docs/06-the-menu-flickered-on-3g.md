# 6. The menu flickered on 3G

[← Previous](05-posters-broke-the-grid.md) · [Back](../README.md) · [Next →](07-moving-the-domain.md)

## The problem

On a slow phone connection, every tap flashed the menu open, flashed the page white and
showed the header without its logo.

## The root cause

These looked like three separate bugs, but they had one cause. The first thing the browser
drew depended on a stylesheet that hadn't finished loading yet.

## The fix

I put the handful of styles the first frame needs directly into the page, made the menu
start closed, and changed the logo to a regular image so it loads right away.

## Testing it

I recorded the page frame by frame on throttled 3G and 4G connections, and kept going until
none of the three problems showed up.

## The result

Lighthouse gives the site 99 for performance on desktop and 100 for accessibility, with no
layout shift at all.
