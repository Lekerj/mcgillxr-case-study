# 6. The menu flickered on 3G

[← Previous](05-posters-broke-the-grid.md) · [Back](../README.md) · [Next →](07-moving-the-domain.md)

**Problem.** On a slow phone, every tap flashed the menu open, flashed the page white and
drew the header without its logo.

**Root cause.** Three symptoms, one cause: the first frame depended on a stylesheet that
hadn't loaded yet.

**Fix.** I put the few rules the first frame needs directly in the page, shipped the menu
closed by default, and made the logo a normal image.

**How I checked.** I recorded frames on throttled 3G and 4G until none of the three showed up.

**Result.** Lighthouse: 99 performance on desktop, 100 accessibility, zero layout shift.
