# 5. Posters broke every grid

[← Previous](04-a-site-that-outlives-me.md) · [Back](../README.md) · [Next →](06-the-menu-flickered-on-3g.md)

**Problem.** Event photos are wide and posters are tall. Mixed in one row, they wrecked the
layout.

**What I tried.**

- Cropping posters cut off their titles.
- Shrinking them made them unreadable.
- Leaving them alone pushed the text on neighbouring cards 280 px out of line.

**What worked.** Photos get a small crop, and posters are never cropped or scaled. CSS subgrid
makes each row as tall as its tallest picture, so the text on every card in a row lines up.

![Events page](../screenshots/new-events-desktop-full.jpg)
