# 4. The site had to survive me leaving

[← Previous](03-the-old-site-was-wrong.md) · [Home](../README.md) · [Next →](05-posters-broke-the-grid.md)

## The problem

The old site got stuck because the domain login left with one person. Club executives change
every year, and whoever takes over after me may never have used the tools I picked.

## How I designed for that

### Static, with nothing to keep running

The site is built with Astro into plain HTML files, and Cloudflare serves them. There's no
server, no database and no environment variables. Setting it up locally is `npm install`
and `npm run dev`.

### Content anyone can edit

Every event, sponsor, team member and FAQ answer is its own Markdown file. Adding an event
means adding one file and its picture, with no code changes. A guide in the content folder
explains it step by step for people who don't code.

### Mistakes caught before they go live

Every type of content has a schema. If a required field is missing, a date is malformed, or
an event lists a sponsor that doesn't exist (a typo, for example), the build fails and the
broken version never reaches the site.

### Nothing updated by hand

Whether an event is upcoming or past comes from its dates. The years a sponsor appears under
come from the events it backed. The numbers on the homepage are added up from the events.
Nobody has to remember to update any of it.

## The trade-off

Because the site is static, "upcoming" is decided when the site is built, not when someone
visits. Without a rebuild, a finished event keeps showing as upcoming. The handoff document
says the deployment should rebuild at least once a day for this reason.

## Documentation

The repo has a handoff document (accounts, deployment, DNS), an architecture guide with a
short introduction to Astro, and a to-do list ordered by priority.
