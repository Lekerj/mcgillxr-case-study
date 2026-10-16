# 4. The site had to survive me leaving

[← Previous](03-the-old-site-was-wrong.md) · [Home](../README.md) · [Next →](05-posters-broke-the-grid.md)

## The problem

The old site died because it depended on one person. Whoever takes over after me may never
have used the tools I picked.

## How I designed for that

### Static, with nothing to maintain

There's no server or database to keep running. The whole site is plain files.

### Content anyone can edit

Every event, sponsor and team member is a simple text file. Adding an event means adding one
file, without touching any code.

### Mistakes caught before they go live

If a required field is missing or a sponsor's name is misspelled, the build fails and the
broken version never reaches the site.

### Nothing updated by hand

Whether an event is upcoming comes from its date. Which years a sponsor appears under comes
from the events it backed. Nobody has to remember to update either.

## The trade-off

A static site decides what's "upcoming" when it's built. So the site has to be rebuilt every
day, or a finished event keeps showing as upcoming. I put that in the handoff document so the
next person knows.
