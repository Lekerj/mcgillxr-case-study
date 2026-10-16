# 4. The site had to survive me leaving

[← Previous](03-the-old-site-was-wrong.md) · [Back](../README.md) · [Next →](05-posters-broke-the-grid.md)

**Problem.** The old site died because it depended on one person. The next VP Technology
might never have used my stack.

**Decisions.**

- **Static site, nothing running.** There's no server, database or secrets to hand over.
- **Content is just files.** Adding an event means adding one Markdown file, with no code
  changes.
- **Mistakes break the build, not the live site.** A missing field, or a typo in a sponsor's
  name, stops the deploy.
- **Store facts, compute the rest.** "Upcoming" comes from dates and sponsor years come from
  events, so nothing has to be updated by hand.

**Trade-off I caught.** On a static site, "upcoming" is decided at build time, so the site
needs a daily rebuild. I wrote that into the handoff doc.
