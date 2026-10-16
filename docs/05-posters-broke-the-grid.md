# 5. Posters broke every grid

[← Previous](04-a-site-that-outlives-me.md) · [Home](../README.md) · [Next →](06-the-menu-flickered-on-3g.md)

## The problem

Event cards sit up to three in a row. The club's photos are wide (between 1.37:1 and 1.84:1),
but several events only have a poster, and posters are tall. A poster in the same row as
photos broke the layout.

## Why the obvious options didn't work

- Cropping a poster to the same shape as the photos would cut off most of it, including the
  title and date.
- Shrinking posters down to fit the photo frame made them too small. I tried it and rejected
  it.
- Showing posters at full size made their card much taller, and the text on the cards next to
  them started up to 280 px higher. The row no longer lined up.

## The solution

I set two rules. Photos get cropped to 16:10, a small trim given their real proportions.
Posters are never cropped or resized, and the build detects them automatically because
they're taller than they are wide.

To keep rows aligned anyway, each card uses CSS subgrid and spans two rows of the grid, one
for the picture and one for the text. Each row becomes as tall as its tallest picture,
shorter pictures sit centred in that space, and the text on every card starts on the same
line. Nothing gets scaled to make it fit.

![Events page](../screenshots/new-events-desktop-full.jpg)

## Other layout fixes from the same work

- There were 288 px gaps between sections, because two sections' padding added up. Section
  spacing now comes from two shared values instead of being set on each page.
- The footer had a 144 px top margin stacked on the last section's padding. I removed it.
- Team photos are square crops anchored near the top, where faces are. Members without a
  photo get their initials on the club's logo, at the same size.
- Layouts are built to work down to 320 px wide and on landscape phones.
